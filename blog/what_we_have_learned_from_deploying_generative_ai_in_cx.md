---
title: "What we’ve learned from deploying Generative AI in CX"
date: 2024-04-23
author: Crescendo
avatar: logo.jpg
description: "Impressive AI demos aren't the whole story – we've learned a ton about making generative AI actually work for customer experience.We're seeing the potential of generative AI in the real world, but the key is learning from experience and putting smart limits in place."
keywords: "Conversational Intelligence, Generative AI, Crescendo, CX, Customer Experience, CX Improvement, Customer Satisfaction" 
---

Impressive AI demos aren't the whole story – we've learned a ton about making generative AI actually work for customer experience.
We're seeing the potential of generative AI in the real world, but the key is learning from experience and putting smart limits in place.

---

![RethinkingBPO](/img/blog/whatwehavelearned.png)

**Spoiler: We’re more confident than ever that generative AI is about to transform the CX industry. We’ve deployed over a dozen implementations of our customer experience (CX) assistant. The Crescendo CX Assistant is the generative AI frontline of our service, handling inquiries and escalating to skilled agents (our humans-in-the-loop) when needed.**

**To be clear, these implementations aren’t demos – these are live production deployments handling real customer conversations.  We’ve had some pretty amazing results, and I’d like to share some of what we’ve learned.**


## Don’t let prototypes lead you on

You may have seen compelling generative AI demos or even built a prototype yourself. Prototypes showcase the technology's potential, and we build prototypes for all interested clients as part of our onboarding—at no charge. That said, moving from prototype to production deployment requires careful consideration. Here are a few factors to keep in mind.


## Hallucination: Do you see an elephant in the room?

If you do, you’re right – hallucinations are a frequent concern we hear about using generative AI in customer service. So, let's get on the same page about what I mean by that.  For our purposes, a hallucination is a wrong answer that the AI just makes up on the spot, with no basis in the provided knowledge base. Big language models trained on massive internet data tend to do this, since figuring out the source of their answers isn't always possible.

### Why Crescendo AI doesn’t hallucinate

At Crescendo, we take a different approach with our CX Assistant. We put guardrails in place to keep the AI focused on the specific knowledge our clients provide. We tap into the language skills and logic of the big models, but we don't rely on their general knowledge. That means, with our deployments, we haven't had any hallucinations yet.

Now, this means our CX Assistant won't be winning any trivia contests. It's not going to tell you the capital of France. But honestly, would you want your customer service AI spouting off random, potentially incorrect, information? It’s a nice party trick…but not a risk worth taking.

## We can fix a wrong answer

Of course our AI isn’t perfect. Sometimes it’s wrong — but when it’s wrong, in every case, we’ve been able to trace the issue back to knowledge content or behavioral programming that we control. We can always fix the problem. That's the key. We fine-tune extensively in the first week, and eventually, so those errors happen less and less. That’s why we're so confident about deploying production-ready solutions quickly.

We don't just launch and forget it, though. We test and tune even after it's live, because real-world customer interactions teach us new things. We are extra cautious in the first couple of weeks, triggering escalations to our humans-in-the-loop. That human feedback means we ramp up the automation smartly, with everyone staying happy.



## Testing helps your brilliant (but literal) AI

Generative AI is powerful and learns quickly, which is awesome. But, it's easy to forget that it's not a mind-reader. Overlooking testing and assuming it will "just figure it out" can lead to... interesting results. You'll still see instances where the AI takes instructions a bit too literally, leading to unexpectedly silly mistakes. Here’s an example that we saw in the field.

One of our clients had a "$50 off today only" promotion. They wrote it up as a knowledge article, exactly as stated.  Turns out, customers buying lower-priced accessories got the full $50 discount. Technically correct... but not the intended outcome. A quick patch was to have the CX Assistant always add "discount doesn't apply to accessories".

Problem solved? Not quite. Our super-obedient AI now included that disclaimer on every promotion mention, even for the main product meant for the discount.  A more refined fix ("Offer discount on [core product]") did the trick.

### “Trust, but verify” your AI
"Trust but verify" is our motto. We expect to fine-tune the AI before and after launch. That back-and-forth is key with generative AI. Plus, we believe in continuous improvement, which is why our solution includes human-in-the-loop support. That way, you reap the most benefits.

Even when our AI isn't wrong, the way it communicates matters.

## Brevity vs. thoroughness

There's one dead giveaway that you're chatting with generative AI, not a real person: Ask something complex. That instant, detailed response is the tell. It's impressive, even startling.  So much so, that clients often ask us to shorten the AI's answers. While we can easily adjust that, we always say, “let’s test it first.”

Is the goal to spark a customer's interest, maybe get them to book with the sales team? Then shorter is better. But for customer support, a thorough explanation might be exactly what they need.

We've even had setups where the AI gives a partial answer with a link for more info.  But honestly, we see that as temporary. Long-term, customers will adapt and learn how to ask for what they need: "That didn't fix it, can you go into more detail?"

Imagine an AI that adjusts its responses automatically, based on who's asking and the situation at hand. That's the kind of innovation we're always working towards.

## Why CX-specific context is critical
Those big language models are amazing, but they're clueless about context.  That's why it's crucial to give your CX conversations the right focus.

The first layer of context is the conversation's purpose. In business, that means your goal – support, lead generation, etc.

Sure, there’s the old saying that "the customer is always right," but your business has objectives. CX interactions need to be seen through that lens.  Not all customer conversations are created equal – you have your ideal customer, after all.  Wasting time on someone who's a bad fit (like that too-small prospect for your B2B SaaS) is actually a bad customer experience for everyone.

## Knowledge: Start small, grow smart

The Crescendo CX assistant is flexible—it can deliver great results with surprisingly little information. See for yourself on our homepage — that assistant only has a few pages to work with.

We've also seen it shine with huge knowledge bases or websites. These deployments are remarkable in terms of how much knowledge the system can remember. Imagine an AI that juggles massive amounts of info better than any person could.

But here's the thing: more content doesn't always mean better content. Think of those frustrating internet searches where you find tons of outdated help articles.

Our sweet spot is working with around a hundred well-maintained knowledge articles. Again, it’s not a technology constraint. It’s more of an observation based on working with customers that have well-maintained knowledge repositories. Of course the number will likely grow as generative AI makes it even easier to maintain clean and accurate knowledge repositories.

We encourage most clients to start small, with carefully curated knowledge, then grow organically. Forget guessing what you'll need. We can launch, learn, and add the right content as we go.  Our CX experts aren't just there to help customers, they're fine-tuning your knowledge base as they work.

## What’s next
This is just a taste of what we've learned from our early deployments. We've got even bolder ideas in the pipeline, and the lessons keep coming as we push the boundaries of generative AI in customer experience. Our exploration is far from over.
We're hungry for your insights. Have your own experiences deploying AI? See a possibility we haven't explored?

[Let's talk.](https://crescendo-cx.com/get-started)

