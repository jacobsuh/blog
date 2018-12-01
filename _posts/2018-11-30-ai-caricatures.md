---
layout: post
title:  "AI Caricatures"
date:   2018-11-20
excerpt: "If you want your features really highlighted to you, consider AI."
---

In my last post, I wrote about technology marching forward without reflection, albeit with a benign example. Since then, Google revealed they had noticed an issue where its AI-based suggested email responses [displayed some gender bias](https://www.reuters.com/article/us-alphabet-google-ai-gender/fearful-of-bias-google-blocks-gender-based-pronouns-from-new-ai-tool-idUSKCN1NW0EF): 

>Gmail product manager Paul Lambert said a company research scientist discovered the problem in January when he typed “I am meeting an investor next week,” and Smart Compose suggested a possible follow-up question: “Do you want to meet him?” instead of “her.”

Ignoring the issue itself for a second, I think we can all agree: bugs are a natural part of the development lifecycle. Accidentally releasing bugs into production is natural. Programmers and their PMs are all human — they're not omnipotent and mistakes are bound to happen. They're also expected, however, [to fix these bugs](http://nymag.com/intelligencer/2018/11/unable-to-stop-bias-gmail-avoids-gender-in-ai-replies.html):

> The team tried various workarounds, but nothing worked. In the end, the only solution was to prevent Smart Compose from suggesting any gendered pronoun (e.g., “he/him/his” or “she/her/hers”) at all. With Smart Compose currently being used in about 11 percent of all sent Gmail messages, Google saw a hard ban as the best option.

This... Uh... doesn't really seem like a solution? It could be a temporary fix, sure, while they work in the background trying to stamp out the issues. Unfortunately, I'm not convinced that's the case here... Mainly because [this feels awfully familiar](https://www.wired.com/story/when-it-comes-to-gorillas-google-photos-remains-blind/):

> In 2015, a black software developer embarrassed Google by tweeting that the company’s Photos service had labeled photos of him with a black friend as “gorillas.” Google declared itself “appalled and genuinely sorry.” An engineer who became the public face of the clean-up operation said the label gorilla would no longer be applied to groups of images, and that Google was “working on longer-term fixes.”
>
> More than two years later, one of those fixes is erasing gorillas, and some other primates, from the service’s lexicon.

Yep, gorillas don't exist anymore in the Google Photo jungle. Neither do chimps, chimpanzees, nor monkeys. All a complete figment of your imagination. On the bright side, baboons, marmosets, and orangutans get to continue inhabiting Google's rainforest[^1]. I really don't think I need to opine here about how scorched earth *definitely* isn't the right solution. 

If an engineer is tasked with building an AI bot to automate some process, she could go about it in two ways. Either she can train the AI using some desired end-results, supply some starting examples, and then allow the AI to work backwards to come up with a method of reaching said end-results; or she can give the AI training data containing examples of how humans used to do it before. The assumption in the latter example is that the humans used to do a good job and the AI can simply learn to mimic the human's behavior. 

Unfortunately, natural language processing doesn't naturally result in any easily quantifiable end-results, i.e. there's really no way to quantify what the best responses to emails are. In a similar vein, neither do hiring practices, like in the case of [Amazon's AI recruiting tool that was recently scrapped](https://www.reuters.com/article/us-amazon-com-jobs-automation-insight/amazon-scraps-secret-ai-recruiting-tool-that-showed-bias-against-women-idUSKCN1MK08G) for  dinging female applicants. Ergo, the latter training method was necessary for both cases. If there was a way to easily quantify coders in order to suss out who the best are[^2], that aforementioned builder could simply take all the 10-rated coders, take their corresponding job applications, feed them into the AI along with all the other submitted applications, and let it learn what characteristics resulted in the best coders. Unfortunately... There isn't. All we have right now are the best human approximations of that, which is evidently pretty flawed.

It's a little ironic that we need robots to highlight our human flaws, but things tend to get easier to notice when they're exaggerated and reflected back at us. Matt Levine, one of my favorite finance newsletter writers, [wraps it up pretty nicely](https://www.bloomberg.com/opinion/articles/2018-10-11/the-robots-learn-by-watching-us):

> If you build a machine-learning robot and ask it “who are the best employees” and it goes out and examines the world and comes back and says “men, it’s men, men are the best,” then that tells you something surprising and complicated about either the world or your robot. But if you build a machine-learning robot and ask it “who are the candidates we like to hire” and it goes out and examines your hiring decisions and comes back and says “men, it’s men, you hire men,” then that tells you something quite straightforward about your hiring decisions.

[^1]: I really wish this specific story was about Amazon so I could've made a pun about the Amazon Rainforest.

[^2]: There isn't, but the only thing I could think of is... a ratio of number of lines committed to the number of syntax errors committed? That's just dumb for a number of reasons, but it's a fun thought experiment.
