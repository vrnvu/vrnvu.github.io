+++
title = "smart questions"
date = 2020-12-20
draft = true
authors = ["arnau"]

[taxonomies]
categories = ["culture"]
tags = ["culture"]

[extra]
lang = "en"
toc = true
show_comment = true
math = false
mermaid = false
+++
---


How To Ask Questions The Smart Way [^1], by ESR.

<!-- more -->
Notes, commentary and personal adaptation.

## Before you ask

Before asking a techincal question:

- Try to find an answer by searching the archives of the forum or mailing list you plan to post to.

- Try to find an answer by searching the Web.

- Try to find an answer by reading the manual.

- Try to find an answer by reading a FAQ.

- Try to find an answer by inspection or experimentation.

- Try to find an answer by asking a skilled friend.
    
- If you're a programmer, try to find an answer by reading the source code.

When you ask your question, **display the fact that you have done these things first**; this will help establish that you're not being a lazy sponge and wasting people's time. Better yet, **display what you have learned from doing these things**. We like answering questions for people who have demonstrated they can learn from the answers.

Take your time. Do not expect to be able to solve a complicated problem with a few seconds of Googling.

Prepare your question. Think it through. The more you do to demonstrate that having put thought and effort into solving your problem before seeking help, the more likely you are to actually get help.

Beware of asking the wrong question. [^2] 

Never assume you are entitled to an answer. 

On the other hand, making it clear that you are able and willing to help in the process of developing the solution is a very good start. **“Would someone provide a pointer?”, “What is my example missing?”, and “What site should I have checked?”** are more likely to get answered than “Please post the exact procedure I should use.” because you're making it clear that you're truly willing to complete the process if someone can just point you in the right direction.

## When you ask

- **Choose your forum carefully**: Don't ask a technical questions in the wrong forum.

- **Don't trust stack overflow**: People post easy to copy and paste code but don't explain the answer. Deprecated answers for frameworks and libraries. Low quality explanations missing the fundamentals. Take all the answers with a grain of salt.

- **Web and IRC forums, Slack**: If you can interact with the main developers of an open source project do it. You can assert their knowladge in the problem.

- **Use meaningful, specific subject headers**: Be SMART, specific in versions and errors. Use key words.

- **Make it easy to reply**

- **Write in clear, grammatical, correctly-spelled language**

- **Send question in accesible, standard formats**: Open source projects usually have templates for issues. Use them. Adopt them in your own projects.

- **Be precise and infromative about your problem**:

    - Describe the symptoms of your problem or bug carefully and clearly.

    - Describe the environment in which it occurs (machine, OS, application, whatever). Provide your vendor's distribution and release level (e.g.: “Fedora Core 7”, “Slackware 9.1”, etc.).

    - Describe the research you did to try and understand the problem before you asked the question.

    - Describe the diagnostic steps you took to try and pin down the problem yourself before you asked the question.

    - Describe any possibly relevant recent changes in your computer or software configuration.

    - If at all possible, provide a way to reproduce the problem in a controlled environment. 

- **Don't rush to claim that you have found a bug**: When you are having problems with a piece of software, don't claim you have found a bug unless you are very, very sure of your ground. 

    - *Hint: unless you can provide a source-code patch that fixes the problem, or a regression test against a previous version that demonstrates incorrect behavior, you are probably not sure enough. This applies to webpages and documentation, too; if you have found a documentation “bug”, you should supply replacement text and which pages it should go on.*

- **Describe the problem's symptoms, not your guesses**: Another example of [^2]. It's not useful to tell hackers what you think is causing your problem. So, make sure you're telling them the raw symptoms of what goes wrong, rather than your interpretations and theories. Let them do the interpretation and diagnosis. If you feel it's important to state your guess, clearly label it as such and describe why that answer isn't working for you.

- **Describe your problem's symptoms in chronological order**: The clues most useful in figuring out something that went wrong often lie in the events immediately prior. So, your account should describe precisely what you did, and what the machine and software did, leading up to the blowup. 

- **Describe the goal, not the step**: If you are trying to find out how to do something (as opposed to reporting a bug), begin by describing the goal. Only then describe the particular step towards it that you are blocked on.

- **Be explicit about your question**: Open-ended questions tend to be perceived as open-ended time sinks. Those people most likely to be able to give you a useful answer are also the busiest people (if only because they take on the most work themselves). 

    You are more likely to get a useful response if you are explicit about what you want respondents to do (provide pointers, send code, check your patch, whatever). This will focus their effort and implicitly put an upper bound on the time and energy a respondent must allocate to helping you. This is good.

- **When asking about code**: The most effective way to be precise about a code problem is to **provide a minimal bug-demonstrating test case**. How do you make a minimal test case? If you know what line or section of code is producing the problematic behavior, make a copy of it and add just enough supporting code to produce a complete example. If you can't narrow it down to a particular section, make a copy of the source and start removing chunks that don't affect the problematic behavior. **The smaller your minimal test case is, the better*.

    Generating a really small minimal test case will not always be possible, but trying to is good discipline. It may help you learn what you need to solve the problem on your own — and even when it doesn't, hackers like to see that you have tried. It will make them more cooperative.

    If you simply want a code review, say as much up front, and be sure to mention what areas you think might particularly need review and why.

- **Prune pointless queries**

- **Courtesy never hurts, and sometimes helps**: Please, Thank you.

- **Follow up with a brief note on the solution**: When you already found a valid solution or explored a hint, update your original question to let the people who helped you know what the answer was. Let your research be useful.

## How to interpret answers

- **RTFM**: If you are told to RTFM, then RTFM

- **If you don't understand...**: If you don't understand the answer, do not immediately bounce back a demand for clarification. Use the same tools that you used to try and answer your original question (manuals, FAQs, the Web, skilled friends) to understand the answer. Then, if you still need to ask for clarification, **exhibit what you have learned**.

- **Dealing with rudeness**: Much of what looks like rudeness in hacker circles is not intended to give offense. Rather, it's the product of the direct, cut-through-the-bullshit communications style that is natural to people who are more concerned about solving problems than making others feel warm and fuzzy.

## Questions not to ask

- Q: Where can I find program or resource X?

- Q: How can I use X to do Y?

- Q: How can I configure my shell prompt?

- Q: Can I convert an AcmeCorp document into a TeX file using the Bass-o-matic file converter?

- Q: My {program, configuration, SQL statement} doesn't work

- Q: I'm having problems with my Windows machine. Can you help?

- Q: My program doesn't work. I think system facility X is broken.

- Q: I'm having problems installing Linux or X. Can you help?

- Q: How can I crack root/steal channel-ops privileges/read someone's e-mail?

## How to answer questions in a helpful way

- **Be gentle**. Problem-related stress can make people seem rude or stupid even when they're not.

- Reply to a first offender off-line. There is no need of public humiliation for someone who may have made an honest mistake. A real newbie may not know how to search archives or where the FAQ is stored or posted.

- **If you don't know for sure, say so!** A wrong but authoritative-sounding answer is worse than none at all. Don't point anyone down a wrong path simply because it's fun to sound like an expert. Be humble and honest; set a good example for both the querent and your peers.

- **If you can't help, don't hinder.** Don't make jokes about procedures that could trash the user's setup — the poor sap might interpret these as instructions.

- **Ask probing questions to elicit more details**. If you're good at this, the querent will learn something — and so might you. Try to turn the bad question into a good one; remember we were all newbies once.

- While muttering RTFM is sometimes justified when replying to someone who is just a lazy slob, a pointer to documentation (even if it's just a suggestion to google for a key phrase) is better.

- **If you're going to answer the question at all, give good value**. Don't suggest kludgy workarounds when somebody is using the wrong tool or approach. Suggest good tools. Reframe the question.

- **Answer the actual question!** If the querent has been so thorough as to do his or her research and has included in the query that X, Y, Z, A, B, and C have already been tried without good result, it is supremely unhelpful to respond with “Try A or B,” or with a link to something that only says, “Try X, Y, Z, A, B, or C.”.

- **Help your community learn from the question**. When you field a good question, ask yourself “How would the relevant documentation or FAQ have to change so that nobody has to answer this again?” Then send a patch to the document maintainer.

- **If you did research to answer the question, demonstrate your skills rather than writing as though you pulled the answer out of your butt**. Answering one good question is like feeding a hungry person one meal, but teaching them research skills by example is showing them how to grow food for a lifetime.

---
# Footnotes

[^1]: *How To Ask Questions The Smart Way by Eric Steven Raymond* [questions](http://www.catb.org/esr/faqs/smart-questions.html) 
[^2]: *The XY Problem* [xy-problem](https://xyproblem.info/#)