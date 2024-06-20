---
title: "85% Isn’t Good Enough: What it Takes to Get Generative AI into Production"
date: 2024-06-19
author: Tod Famous
avatar: "Tod Famous Pic.png"
ogimage: "/logoblog.png"
description: "The tech only gets you to 85%.  You need a great deal of AI expertise, use case expertise, and process to get to production."
keywords: "Conversational Intelligence, Generative AI, Crescendo, CX, Customer Experience, CX Improvement, Customer Satisfaction" 
---

The tech only gets you to 85%.  You need a great deal of AI expertise, use case expertise, and process to get to production.

---

![Empathy](/logoblog.png)



The recent news about [McDonald's pulling back on its Automated Order Taking](https://www.cxtoday.com/speech-analytics/mcdonalds-stops-using-ai-for-drive-thru-orders-whats-next-for-fast-food-cx/) (AOT) initiative caught my attention. It aligns with several recent conversations I've had with customers who tried implementing Generative AI based on Large Language Models (LLMs) where they’d hit a wall because they can’t reach the accuracy requirements necessary for production.  Some customers have resigned to using it only for back-office use cases with “less risk” such as call summarization.

At Crescendo, we're now in production with many brands doing customer-facing generative AI for CX, potentially more than any other CX company. I'd like to share our insights on the formula required to get this technology into production successfully.


1. **AI Expertise, Specifically LLM Technology**
Hiring talent with experience developing and deploying applications based on Foundational LLM AI technology is essentially impossible in 2024.  You’re going to need to hire smart and agile technical talent and give them the time and space to (re)learn how to build software. 

2. **Domain Expertise**
You need more than AI experts who understand the technology; they must also understand the use case. A common mistake in CX is trying to replicate the people instead of automating the CX work. Automating the CX work requires a deep understanding of CX operations as well as the interactions between the people and the technology.


With these two, you can get to 85%, but to get into production you need the third ingredient:


3. **GenAI Testing and Deployment and Maintenance**

Production quality generative AI applications require a completely different model for testing and deployment than traditional software products.  This article will focus our recommendations for this new process.


## **Shift Right**

During my decade at Cisco, I worked with engineering leaders to eliminate the post-development QA cycle using the "shift left" philosophy, producing test automation for 100% of our code as it was developed. This approach ensured highly reliable and predictable software quality.


At Crescendo, we’ve learned that Generative AI applications require us to learn to "shift right." While we still do test automation to ensure our code quality while in development, LLM performance is inherently non-deterministic, with outcomes uniquely produced based on user interactions with the system. We have yet to find a substitute for real customer interaction to test these systems effectively.


Google's Gemini rollout in early 2024 exemplifies this challenge. Despite their outstanding development practices, Gemini produced wildly unexpected results in the hands of consumers. This release highlights how even a highly competent shift-left development team can miss the mark with Generative AI.


Generative AI development necessitates reintroducing testing as part of the development process, shifting right.  At Crescendo we’ve developed tooling to assist our team with testing from prototype to production and even after deployment to maintain and improve performance..


## **Narrow Scope Lowers Risk**

Those who compare a business service like our Crescendo CX Assistant to a consumer product like ChatGPT may overlook the massive difference in scope. The foundational AI models cover essentially any topic, making them extremely difficult to control. Our CX Assistant engages only in conversations related to a specific business or product. This focused approach reduces risk and prevents hallucinations. We can constrain this even further based on client needs. For example, one of our customers is a B2B SaaS company with a highly complex pricing model. While they had a good amount of content to describe their pricing, the specific pricing scenarios turned out to be context-dependent and therefore quite difficult to test. For this client, we simply ‘took pricing off the table’ to narrow the scope of the discussion to product functionality questions. This approach let us get into production quickly and then incrementally expand the scope of the Assistant as we grew more confident in the performance of the implementation.


## **Observe and Coach**

If you’ve deployed a Legacy AI chatbot in the past few years you likely invested months design and implementation before deployment.  With this type of technology you invest the time to design and develop before you have a working product.  Generative AI based automation technology is completely different as you could build in just hours, but then you invest more time in testing, observing, and then tuning the system with more coaching.
You also need to keep in mind that every conversation, indeed every response, is completely unique and should be monitored for quality assurance.  We developed our own Voice of Customer solution to measure customer satisfaction with every response from our Assistant. This enables us to maintain high quality and quickly correct errors.


![Dashboard](/img/blog/what_it_takes/dashboard.png)



## **Your Knowledge Content Has Errors**

When deploying, we ask customers to provide their current knowledge content, whether documents, presentations, web pages, or a Knowledge Base export. Despite their efforts to clean up this content, we always find errors. These errors are proportional to the amount of content provided and even more common in older content.


Planning for initial accuracy problems and executing a robust testing process to correct these errors is crucial. Our administrative portal shows knowledge article sourcing used by our RAG system, allowing our team to trace and correct errors quickly.


![Transcript](/img/blog/what_it_takes/transcript.png)


Starting with less knowledge content and gradually adding more as needed is a faster path to production. This approach requires flexibility and a willingness to begin with a focused deployment. Our Human in the Loop model gives us the flexibility to deliver CX even if the automation goals are initially modest while our commercial model gives our clients the cost savings benefit up front. Once confident in the knowledge content we have in place, we begin adding content to increase the automation percentages. This isn’t to imply we move slowly; in fact, it's common to see a 20% improvement in automation in the first two weeks.


## **Conclusion**

2023 marked the beginning of Generative AI in CX. The hype is real, and the demos are impressive, but there are still very few production deployments. The last mile of accuracy remains a challenge, but with the right people, expertise, and process, we’ve been able to succeed in deploying CX automation for a wide range of customers. If you've tried and hit the wall at 85%, please reach out at[ www.crescendocx.ai](http://www.crescendocx.ai). We’d love to help you get your Generative AI CX project into production.


[Get in touch with us today.](https://crescendo-cx.com/get-started)


