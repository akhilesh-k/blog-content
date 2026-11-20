---
title: "Before search begins..."
description: "How search engines process raw text before retrieval: a practical introduction to tokenization, stop word removal, and stemming in full-text search analysis."
category: "Search Engineering"
tags: "Search Engineering, Text Analysis, Tokenization, Stemming, Stop Words, Full-Text Search"
date: "2026-11-06"
---

When you type something into a search box, you expect results. Relevant ones, and that goes without saying. 

The search engine should somehow know understand what you meant, your intent and hand back the most relevant documents, ranked in the right order.

That expectation has a lot of background work involved. Before any document gets retrieved or any relevance score is calculated, the search engine has to figure out what the text actually says. If we talk about full text search, both the search query and the documents it searches through start out as raw text, and raw text is messy.

Take a query like _**"Running shoes for men"**_. To you and me, that's a simple phrase with a clear intent. To a search engine, it's nothing more than a sequence of characters. There is no concept of "shoes" or "running" yet, just bytes sitting in memory.

So how does that string become something a machine can search through? That's the job of text analysis[^1], and it rests on three ideas that come up constantly in traditional search systems:

1. Tokenization
2. Stop word removal
3. Stemming

Let's go through them one by one.

## 1. Tokenization: Breaking Text into Smaller Units

Tokenization breaks a piece of text into smaller units, called *tokens*. Depending on the strategy, a token might be a word, a subword, or a single character.

For a query like `"Running shoes for men"`, a word-level tokenizer produces:

**Input:** `Running shoes for men`

**Output:** `["Running", "shoes", "for", "men"]`

Why bother? Because a search engine's inverted index is built out of terms, and terms have to come from somewhere. Once both the documents and the query are broken into tokens, matching becomes possible. Two documents like "Best running shoes for men" and "Men's shoes for running" share enough tokens after this step that a lexical matcher can tell they're related.

The catch is that splitting on spaces doesn't always work. Real text is full of cases where the "right" answer isn't obvious:

- `don't`: one token or two?
- `iPhone 16`: is the model number part of the token, or separate from it?
- `New York`: two tokens, or one phrase?
- `state-of-the-art`: what do we do with hyphens?

There's no universal answer here. The best tokenization strategy depends on the language you're working with, the domain, and what your users actually search for.

## 2. Stop Words: Removing Common Words

Some words show up everywhere and tell you almost nothing. Words like _the, is, a, an, for, of, and_ appear in nearly every English sentence, which means they do very little to distinguish one document from another. In information retrieval, these are called **stop words**[^2].

Look what happens to `"Best running shoes for men"` once they're stripped out:

`["Best", "running", "shoes", "men"]`

Nothing important was lost here, and the query got smaller. That's the appeal. In traditional retrieval systems, dropping stop words shrinks the index, cuts down the number of postings lists that have to be processed at query time, and removes noise from terms that match half the corpus anyway.

But it can go wrong. Try removing stop words from these queries:

- "The Who": a famous music band[^5].
- "To be or not to be": a meaningful phrase.
- "Flights from Bangalore to Delhi": here "from" and "to" carry the entire meaning of the query.

In the first two cases the query gets damaged or destroyed. In the third, removing "from" and "to" leaves you with flights between Bangalore and Delhi in every direction, plus everything going to Bangalore from anywhere.

Blind stop word removal changes what a query means. That's a big part of why modern systems tend to keep stop words, or handle them through smarter query processing instead of deleting them outright.

## 3. Stemming: Reducing Words to Their Root Form

Stemming reduces different forms of a word down to a common stem. Take *connect*, *connected*, *connecting*, and *connection*. A stemming algorithm tries to collapse all of them into one representation.

A few examples:

| Original word | Stem |
|---|---|
| playing | play |
| played | play |
| plays | play |
| studies | studi |
| running | run |

One thing that jumps out: stems are not always real words. `studies` turns into `studi`. That's because most stemmers are just rule-based suffix strippers. They chop off endings according to fixed patterns, without caring whether the result means anything. The **Porter Stemmer**, still one of the most widely used algorithms for English, works by applying a long sequence of these rules[^3].

Why should a search engineer care? Say a user searches for `"running shoes"`, and the best document in your corpus contains the phrase `"best shoes to run a marathon"`. Without any normalization, `running` and `run` are two unrelated tokens as far as the index is concerned, and that document never matches. With stemming, both reduce to the same form:

| Term | Stem |
|---|---|
| running | run |
| run | run |

The match goes through. This is what stemming buys you: **recall**, the ability to pull in relevant documents even when they phrase things differently from the query.

It cuts the other way, though. Stemmers know nothing about meaning, so sometimes unrelated words collapse into the same stem[^4]:

| Original word | Stem |
|---|---|
| university | univers |
| universe | univers |

After stemming, a query for `universe` and a query for `university` are identical to the engine. Someone looking up one of these probably does not want the other, but the index can't tell the difference.

So treat stemming as a trade. You get more recall, and you pay for it in precision. Most engines let you tune stemming per field, and some cases are better served by lemmatization, which is slower and more complex but always produces a real dictionary word.

## 4. Putting It All Together

Here's the full pipeline applied to one sentence:

**Original text:** `"The runners are running towards the best running shoes"`

**Step 1: Tokenization**

`["The", "runners", "are", "running", "towards", "the", "best", "running", "shoes"]`

**Step 2: Stop word removal**

`["runners", "running", "towards", "best", "running", "shoes"]`

**Step 3: Stemming**

`["runner", "run", "toward", "best", "run", "shoe"]`

What's left is a normalized, stripped-down version of the original text, and that's what actually gets written into the index.

## 5. Why Search Engineers Should Care

These ideas get taught as intro NLP material, which makes them easy to dismiss. They shouldn't be. Every one of them shows up as a knob that affects search quality:

| Technique | Primary benefit | Potential drawback |
|---|---|---|
| Tokenization | Enables term-level matching | Incorrect boundaries can hurt retrieval |
| Stop word removal | Reduces index noise and size | Can remove meaningful context |
| Stemming | Improves matching across word variations | Can introduce false matches |

The real lesson is that preprocessing isn't housekeeping. Every step in the analysis pipeline is a decision about what information to keep, what to normalize, and what to throw away, and those decisions shape indexing, matching, recall, and ultimately how relevant your results feel. If you want to keep going, I've written about [how to quantify the quality of search results](/essays/how-to-quantify-the-search-results-quality) and [how the HNSW algorithm powers vector search](/essays/how-does-the-hnsw-algorithm-work), both of which sit a layer above the text processing covered here.

**Before a search engine can understand what a user wants, it has to understand the words they're using.** That work happens quietly, before search begins.

[^1]: Read more about it on elastic docs, [Text analysis during search](https://www.elastic.co/docs/solutions/search/full-text/text-analysis-during-search)

[^2]: The best-known English stop list traces back to Cornell's SMART retrieval system from the mid 1960s, containing 571 words. Variants of it still ship inside Lucene-based engines today.

[^3]: M.F. Porter, "An algorithm for suffix stripping", Program, 14(3), 1980. The paper, reference implementations, and a test vocabulary of over 23,000 words are hosted by the author at [tartarus.org/martin/PorterStemmer](https://tartarus.org/martin/PorterStemmer/)

[^4]: The university/universe conflation example follows the classic treatment in Introduction to Information Retrieval by Manning, Raghavan, and Schütze (Cambridge University Press, 2008), freely available online at [nlp.stanford.edu/IR-book/html/htmledition/irbookprint.html](https://nlp.stanford.edu/IR-book/html/htmledition/irbookprint.html)

[^5]: The band The The is the folklore example of stop word removal gone wrong. In the 1990s, engines that dropped "the" made the band practically unsearchable, and fans resorted to searching for album names or Matt Johnson instead. Search lore keeps it alive as a warning that stop lists can erase the very thing someone is looking for.
