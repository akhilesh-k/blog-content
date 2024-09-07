# Back to learning deeply

![Richard Feynman was a master of learning and the patience that deep understanding requires. His depth of knowledge was exactly what made him such a brilliant teacher.](https://media.springernature.com/full/springer-static/image/art%3A10.1038%2F504030a/MediaObjects/41586_2013_BF504030a_Figa_HTML.jpg)


It was the late summer of 2013, and I was attending the Physics class focusing on Gravitation. I got introduced to the concept of escape velocity. My idea was to memorise the formula as soon as possible and solve as many as possible problems on it.

![
ve: This represents the escape velocity. G represents the gravitational constant. M is the mass of the celestial body. R is the distance from the center of the celestial body to the point where the escape velocity is measured. It can be a bit daunting at first.](https://raw.githubusercontent.com/akhilesh-k/blog-content/main/markdown/back-to-learning-deeply/escape-velocity.png)

I was still in awe of the foriegn formula which I had just seen for the first time. I was just perplexed by the sheer notations and understanding its meaning.

Upon reflecting back on how flawed my motivation was, especially when the intuition for the notation is so easy to understand after a bit of back of the envelope exploration. I want to pen down a few takes on how and why understanding something deeply should be the aim.

## Why is it important to develop deep understanding?

Most thoughtful people I have worked with can explain complex ideas. As the systems around us are getting exponentially complicated, albeit they have started coming with even simpler interfaces. To grow one's knowledge and understanding, one must be able to interpret the chaos behind the facade of this simplicity. In the software engineering this skill of being able to dive deep and understand in depth becomes even more critical because there is no software written for one fit all kind of thing.

Now we have no code deployment, No code backend, No Code  Frontend. 

![Niels Bohr (L) and Albert Einstein (R), debated the nature of quantum physics in a series of public debates. Most of Einstein’s arguments, involve some ‘Gedankenexperiment’, or thought experiment. One of Einstein’s hallmarks was his ability to imagine complex thought experiments to disprove or prove theories — requiring a great amount of understanding.
](https://miro.medium.com/v2/resize:fit:640/format:webp/1*uv8F-EwFyCSqHk4-__rx3Q.jpeg)

In software industry, we often say, do not reinvent the wheel. It comes solely from the perspective of the cost attached with it in terms of developer hour. However, it should be noted that innovation and progress cannot coexist with a memorization-style of learning. 


## Changing the metric of success

As a workaholic, I find it harder than most to understand subjects deeply. Ironically, my drive to learn fast and efficiently goes against the fundamental requirements for deep understanding — patience, and time to work it out yourself.

The hardest challenge of deep understanding is changing your metric of success from amount of subjects covered to the depth of understanding achieved.

Learning to crave the satisfaction that comes from following your intuition and solving a question slowly, but understanding every step, is the key to deep understanding. This is tough to do considering that nearly every institution that has raised us has valued quantity over quality, warping our minds to feel the most satisfaction after finishing a booklet of questions, each solved with some black-box formula.

This craving can best be achieved through hours of exploration, but most importantly, by finding something you are interested in. Having a goal to better understand a topic can make all the steps in between, the countless nights of feeling understanding slip in and out of grasp, worth it.

## Deliberate learning; picking your battles, and prioritization

![One of the derivations I’m aiming to understand — the derivation for gradient descent, one of the main optimization algorithms present in machine learning. Via Chris McCormick.](https://miro.medium.com/v2/resize:fit:720/format:webp/1*1BjKAb9eQchTmrK0YleVoQ.png)

You can’t understand everything, and that’s a critical thing to come to terms with. This is where planning and picking your battles comes into play. Deep understanding takes considerably longer than ankle-deep learning, and you don’t have an infinite amount of time.

Aim to understand what you think will be the most integral to your greater goal, and expand downwards from that.

My current and ongoing goal is to understand, or at least comprehend, the mathematics behind machine learning concepts such as gradient descent and neural network backpropagation.

These ideas require a knowledge of linear algebra, for example.

![Take the ordering with a grain of salt. Much of this ordering doesn’t even really make sense — linear transformations define ALL of these, for example. This is meant more to illustrate the process of “downward understanding”.](https://miro.medium.com/v2/resize:fit:720/format:webp/1*g4J_c4MSfukL7NWh9DgcNg.png)
For machine learning, I have several of these mental prioritization trees (differential calculus, multivariable calculus) connected to the final goal of comprehensive understanding. They help keep you on track on what you are training to learn now, and why it matters in the bigger picture.

Start from what you do know, and before you move on to what you wish to learn next, make sure you understand the prerequisites.

More importantly, be conscious of where you wish to stop “deep learning” — at what point you’re okay with making assumptions. For me, this was integral calculus. The concepts I’m aiming to understand, for now, don’t involve too much integral calculus, so I’ll leave that for later me to figure out.

## Pre-learning

Before diving into understanding, gain a high-level view of the subject — watch a few YouTube videos, learn about why the subject matters, what prerequisites it requires, and make sure understanding the subject serves your pre-defined goal.

Spend time on this, but not too much. Be wary of spending too much time at too high of a level, especially if you are aiming to understand — it can get you distracted and leave you without knowing anything deep enough to be valuable.

Continue passively consuming this content while you go through your studies. If you’re learning about linear algebra, for example, listen to this interview between Gilbert Strang and Lex Fridman. Submerge yourself into the sea of content available on the internet, and you’ll find yourself slowly becoming comfortable talking and understanding the concept.

## What you’re striving for, learning to understand

In the context of mathematics, learning to understand means knowing what notation represents — often visually or graphically, over numerically. This is arguably the most important part of the entire deep learning process.

Learning to understand is a steep learning curve. This will always be tough, and different for every formula, idea or notation you discover.

In the realm of mathematics, you know that you have achieved understanding if you can summarize what you are learning in a short paragraph — why it’s important, what it represents graphically, and what it is. You should be able to walk through why a formula works, and understand every part of it. You should explain the formula, but your description shouldn’t rely on it.

For a simple example, let’s view two different explanations of the distance formula, an elementary equation introduced in around the 8th grade (used for finding the distance between two points in a cartesian, 2D plane)

## Explanation without deep understanding

The equation for distance is as follows:


![](https://miro.medium.com/v2/format:webp/1*4w-KBgqlJpUh3fTPm2DcIQ.png)

Given the x and y coordinates of two points, we can find the line that connects them. This is also the shortest distance between the two points. This result will always be positive, as we are measuring distance, not direction, which is always a positive value because there is no such thing as negative distance.



## Explanation with deep understanding:

The equation for the straight line distance between two points is:

![](https://miro.medium.com/v2/format:webp/1*4w-KBgqlJpUh3fTPm2DcIQ.png)

By leveraging the Pythagorean theorem for right triangles, we can calculate the distance between two points. This works because we can draw a right triangle for which the distance between the two points is the hypotenuse.

![](https://miro.medium.com/v2/resize:fit:720/format:webp/1*fuxVKvNz8cZPHgCvtV8HSg.png)

The right arm of the triangle is the difference in the heights (thus, the y’s) of the two points. The base arm is the difference in the two x coordinates.

Recall the Pythagorean theorem:

![](https://miro.medium.com/v2/resize:fit:720/format:webp/1*MbN1jqNlcr9y5C4sR3a-TA.pngs)

Since our triangle with the distance as the hypotenuse, is a right triangle, we can substitute the values of a and b for our side lengths (the differences in x’s and y’s) to solve for c, the distance.

![*edit* — I made a dumb mistake and I’m too lazy to fix it. Ignore the b² in the second line, that’s not supposed to be there.
](https://miro.medium.com/v2/resize:fit:720/format:webp/1*4sXdyI66KxX2FersiF0sIw.png)

The resulting distance, because of the exponents, will never be negative, which is in line with the definition, since a distance between two points can never be negative (what would -5 meters mean?).

You don’t necessarily have to have this all written out neatly, but for any theorem, most leagues more complicated than this, this should be how your mind works through the definition of a formula. This is what it means to gain deep understanding of a specific idea.

You should be able to easily communicate this idea to others, and feel confident on the intuition.

Resources that teach you how to think like this, and to be able to think through proofs and reason through your head, include my two favorites: 3blue1brown, and Khan Academy. After learning how they work through formulas and proofs, it will aid you in figuring out your own intuition or using less user-friendly resources, such as textbooks.

## On notetaking

Notetaking, either while watching lectures or while reading text, is integral. Gaining understanding is near-impossible without notetaking — not necessarily because having notes to refer back to is helpful (although that is a part of it), but because notetaking requires you to work through the problem with the lecturer/article and gives you a valuable opportunity to think.

Not all notes are created equal — there are ways to make notetaking more valuable.


![The aesthetic quality of your notes doesn’t judge the importance of its content. This messy sketch, dubbed ‘The Tree of Life’, represented the early ideas of common ancestors and evolution, and was sketched by none other than Charles Darwin on the deck of the HMS Beagle in 1837, some 22 years before the publication of On The Origin of Species.
](https://miro.medium.com/v2/resize:fit:720/format:webp/1*d_Ae5UWKR35qJ_J9ztZIkA.png)

Don’t focus on making your notes too pretty. I’m flawed when it comes to this, although I try to restrain myself. Never use pen or fancy markers — it’ll prompt you to retry and retry until it looks just right, leaving you an hour later with a beautiful artwork of a notebook but nearly no learning.

Use good old fashioned pencil and paper, but keep it organized. The ruler is your friend, it allows you to make borders, underline the important. Draw graphs and visualize often.

But the most important part of notetaking is the thinking while taking them. Don’t just mimic the graphs and drawings of the lecturer, but work through the same logic yourself and see if it matches up. Pause and think: Does it make sense?

Something I find that helps me is to write all my notes as if I am explaining the subject to someone else, in the style of the lecturer. This can add an extra time burden as writing in paragraphs can be slow — but it delivers a much greater depth of understanding, and as an added bonus, makes your notes accessible after you might have forgotten the base concepts.

Writing notes should not just be an exercise of penmanship but a thought experiment.

## Finding and filling in gaps of understanding

### Teach it to someone else

> “Those that know, do. Those that understand, teach.”- Aristotle

One of the most powerful ways to find and fill gaps in your understanding of a subject is to teach it to someone else, preferably someone who has little or no experience in the topic.

It forces you to build them up from nothing, walk them through every proof, every intuition, alongside them. It doesn’t take a genius to see how helpful this can be. If you find yourself stumbling often during your explanation, or hesitating to make a statement, it means you need more understanding. Clear teaching is a direct consequence of full confidence in your understanding.

### Play, ponder, and work through it yourself.

The most powerful technique to understanding is to work through problems on paper by yourself and making sure you understand each step.

Play. See what happens when you use a negative instead of a positive. How about a fraction? Does it work the way you expected it to? Can you stumble upon preexisting proofs and laws with your own manipulation? Doing things yourself gives you a depth of understanding that is unachievable by watching others do it. This understanding isn’t easily expressed in words, but it fosters a feeling of comfortability with the concept.

If you run across a scenario that perplexes you, fill that gap of knowledge with more content consumption, or try and figure it out yourself.

The late physicist Richard Feynman, the man in the title image, was famous for his ability to do this. Often when reading a scientific paper, he would stop reading once he got the gist of what they were doing and would get some pen and paper to work through the rest himself.

![The first (out of five) pages of Lee & Yang’s 1956 paper on parity violations in quantum physics (go figure). Now in his mid-life, Richard Feynman has become anxious that he was falling behind on current advances in quantum physics. Picking up this paper from a conference in Rochester, NY, piqued his anxiety — he found it too hard to understand. Feynman was staying with his sister at the time. When he confronted her with his worries, she simply said: “No. What you mean is not that you can’t understand it, but that you didn’t invent it…. What you should do is imagine you’re a student again, and take this paper upstairs, read every line of it, and check the equations. Then you’ll understand it very easily.” Taking her advice, in a short amount of time Feynman had not just understood the entire paper but had found a few errors in Lee’s reasoning.
](https://miro.medium.com/v2/resize:fit:640/format:webp/1*JVDNOhbM4kouAm42U0ZEdA.png)

This sort of play takes time and patience, but is rarely ever not worth the commitment.

## Drills and textbook questions still have their place

Now, after you have gained a good understanding of the topics you’re covering, the application becomes trivial.

Repetition will always be an irreplaceable part of learning and understanding; although, I believe there is an overemphasis on this part of the process. Do enough repetition for it to be in your head, and to be comfortable with practical application — but never lose sight of what’s actually happening under the hood. Self-check yourself periodically and remind yourself of the intuition. Never let a formula just become a formula.

---

Returning to my acceleration conundrum.

![Where s = displacement (a vectorized unit of distance) and a = acceleration. Δt is some measure of time. What does this even mean? Why is the Δt squared? It can be a bit daunting at first.
](https://miro.medium.com/v2/resize:fit:720/format:webp/1*T16hmYndDgR2KkY8Z0aQRw.png)

If only I could have earlier seen how easy it was to gain a simple understanding for such a problem.

The definition of acceleration is how fast a speed is increasing. Essentially, for every time t, how much more distance s is covered than the last time t.

Concretely, if a car has an acceleration of 10m/s², in the first second, it is going at velocity 10m/s. In the next second, it is going at 20m/s. In the third, it is going at 30m/s. And so on.

But why the t² ? It makes sense if we write out the definitions of each in the equation.

Acceleration, to repeat myself, is how fast a speed increases for some unit of time. So, we can express this as

![The reasoning, if you think a bit, is actually pretty intuitive.
](https://miro.medium.com/v2/resize:fit:720/format:webp/1*ki6adwyRghbq4sIN6XdBDQ.png)

Since speed is measured as s/Δt, we can express speed/time as s/Δt/Δt. We can express this as a multiple of two rational expressions, which we can then multiply together to get the definition of acceleration.

---

Deep understanding of any subject is the only path to innovation, application, success, and perhaps most significantly, fulfillment. The comfort achieved through understanding is a wonderful feeling, and with a great deal of determination and perseverance, one can achieve it in nearly any field. ★

