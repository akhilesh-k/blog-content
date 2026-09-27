---
title: "Writing code with LLMs as a staff engineer in 2026"
description: "How I write code with LLMs and Coding agents as a staff engineer in 2026"
category: "Engineering"
date: "2026-09-27"
---

December 2022 feels like ages ago with all the advancements LLMs have made since the launch of ChatGPT. 

![Who knew this thread would be so relevant years later](https://raw.githubusercontent.com/akhilesh-k/blog-content/refs/heads/main/markdown/writing-code-with-LLMs-as-a-staff-engineer-in-2026/chatgpt-launch-thread.png)

It was 2023 February, when I actually signed up to ChatGPT. I started using LLMs to interact with code by mid 2023 and it was definetly not good to be used directly. So I joined the band wagon of people who would not use LLMs for writing code. 

While LLMs were yet not good to write a whole PR, there were a few things where it was good to use LLMs for code generation. For example,

- Writing scripts for quick testing or generating complex shell commands.
- Generating DB queries for day to day use cases.
- Code Autocomplete in IDEs beyond simple text completion: 
- Proofreading my large forum slack messages for grammar and tone. 
- Writing well known code in the language I don't know well.

### It's the Coding Agents Era

I used to select a snippet, ask AI to make some changes, review the output, and copy-paste it back. This was the real friction and aceept rate used to be so low. And all of this was just a year ago. **Now I mostly start by writing specs, Agent generates the code in a single edit pass and with little review, changes are good to go as a PR.**

In 2024, I was using ChatGPT to ask it to write some code for me, and it was good to get the code, but it was not that good to be used directly. In 2025, I was asking for changes inside my IDE with Copilot Chat. Early 2026, I started using [Github Copilot](https://github.blog/changelog/2026-05-14-github-copilot-app-is-now-available-in-technical-preview/) and [Antigravity](https://antigravity.google/blog/introducing-google-antigravity-2). Mid 2026, I started using terminal based agents like OpenCode

Earlier agents often failed after making a bad edit and struggled with large contexts. With new frontier models, longer context and memory have made them much better at recovering from mistakes. The workflow has consequently shifted from generating a few lines at a time to having agents implement entire PRs.

### Testing

Agentic coding has changed my view of TDD. The biggest obstacle to writing tests first was often the cost of writing them. When that cost becomes negligible, writing the tests first becomes a much more attractive way to keep the agent constrained.

Even today, if you just ask Agents to write test cases, they will write test slops which will give you coverage without real meaning. Now given how writing tests code is so cheap with agents, I think it makes sense to start writing test cases first and then ask Agents to write the implementation code. The tests become the specification you give the agent.

- Integration tests are important with Agentic coding. Starting with integration tests will give agents a good sense how services interact with each other. 

- Review tests code first before reviewing implementation. Coding agents will sometimes write tests to just pass the tests which might not lead to a good behaviour or implementation. For example, agents might introduce flags to control behaviour instead of handling different scenarios in different code paths. 

### Bug fixes

Compared to 2025, where LLMs could write code and miserably fail at figuring out bugs, it has gotten so much better at debugging. I now use coding agents as my default starting point when debugging. I usually pair my coding Agent with observability MCPs to get the observability data and try to find out root cause of production issues.

Writing RCA doc is something I still do myself without involving LLMs into it. But these are the stuffs I where I use Agents within the lifecycle of bug hunting:

- Reproducing the production issue by writing tests
- Setting up the environment and tools for debugging

As a tool I believe coding agents are really great at triaging and patching.

### Writing Specs, RFCs, ADRs and Docs

Writing design specs and RFCs is something I still do myself without involving LLMs into it. I belive LLM is a bad choice to design something of significance. In general, LLMs are over expressive and if it is asked to write docs, it will write more than required. This will make it harder for people to consume the docs and just add to slop debt. 

Few things where I consider using LLMs for writing

- PR description with custom Agent Skill. 
- Summarizing process steps for onboarding or learning.
- Correct Grammar, tone and conciseness for Slack messages meant for bigger forums.
- Running my drafted RFCs / ADRs by an Agent to get a second person's perspective as comments.


### Code Review

I will also never use LLMs to generate Code reviews unless there is something really tricky which becomes hard to mentally process. (Such PRs end up getting requested for changes, anyway).
Actively reviewing code myself and understanding the changes deeply helps me keep my thought process in sync with what is being built in the team.

## Summary
Past 3 years, I have seen LLMs evolve significantly. It has evolved from being a simple text generation tool to a full-fledged coding agent which can write code, debug, review and much more. 

Sitting at the other end of Coding Agents using it, I still remain an Individual contributor with much wider control over things I can understand quickly. I can now implement simple features end to end with agents including writing and running tests myself. But exercising my own judgement, writing my thoughts and decisions, reviewing code are still my responsibility which can't be outsourced to LLMs and even when the time comes, I mustn't outsource it.

