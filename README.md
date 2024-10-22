# EcoQuery

https://yhack24.vercel.app/
<img width="1707" alt="Screenshot 2024-10-22 at 12 24 25 PM" src="https://github.com/user-attachments/assets/a8c61014-4bd1-49e9-9e72-dfa0f8dfbd5a">

The project aims to enhance sustainability by reducing the computational load of large language models (LLMs) through vector-based similarity searches, optimizing efficiency without compromising user customization.


This is a Next.js project bootstrapped with create-next-app.

Getting Started
First, run the development server:

npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev


Open http://localhost:3000 with your browser to see the result.

You can start editing the page by modifying app/page.tsx. The page auto-updates as you edit the file.

This project uses next/font to automatically optimize and load Geist, a new font family for Vercel.

Learn More
To learn more about Next.js, take a look at the following resources:

Next.js Documentation - learn about Next.js features and API.
Learn Next.js - an interactive Next.js tutorial.
You can check out the Next.js GitHub repository - your feedback and contributions are welcome!


Inspiration:

Sustainability is one of the core pillars of modern progress. We wanted to address this challenge by thinking about how we could allow for substantial improvement in sustainability by optimizing an existing system. That's why we landed on LLMs: their meteoric rise in popularity has changed the way millions of people search for and learn information. That being said, LLMs are extremely inefficientwhen it comes to the compute required for inference. With hundreds of millions of people relying on them for day-to-day searches, it is evident that we have reached a scale where sustainability needs to be carefully considered. We asked ourselves, how can we make LLMs more sustainable? Can we quantify that cost so users can understand how many resources they use/save? The key to the idea is the fact that we wanted to propose a way to dramatically improve sustainability with almost zero-effort required from the user's side. These are the principles that make our proposal both practical and most impactful.

What it does:

In essence, we leverage vector embeddings to make LLMs more sustainable. Everyday, just on chatGPT, there are over 10 million queries made. Even over a small period of time, query overlap is inevitable. Currently, LLMs run inference on every single query. This is unnecessary, especially when it comes to objective queries that are similar to one another. Instead of relying on inference by default, we rely on vector-based similarity search first. This approximately takes 1/15 of the compute that normal compute would take per query on chatGPT. Now, what makes LLMs desirable is their customization of responses. We didn’t want to lose this vital component by solely relying on embedded vector search. Thus, we give the user an option if they would like more information, and this defaults to a traditional LLM query. Thus, our approach allows for sustainability that is orders of magnitude higher than before, without compromising what people like most about LLMs.

How we built it:

For embeddings and our vector database, we used Pinecone. Our app is created with NextJS (ReactJS, TailwindCSS, NodeJS). We utilize the OpenAI api for traditional query requests. For our similarity search, we used cosine-similarity, and given that a query crosses our significance threshold, we return top 0-3 such queries for any given user input.

Challenges we ran into:

This was our first time working with embeddings and a vector database. Thus, we had some issues with setup and adding a new embedding to the overall vector space. We wanted the space to be dynamic so that answers generated for users can be shared by all users if someone were to ask a similar query in the future. Other than that, integrating all the required APIs was a challenge as some functions were async while others weren’t which caused state-update issues. Luckily, with some debugging, we were able to sort it out.

Accomplishments that we're proud of:

Our final version is a fully-functional prototype of our idea. We are also astonished by the real statistics behind the resources our system can potentially save. Additionally, we took UI extremely seriously because we wanted a system that was intuitive and appealing for users to use. We also wanted a clear way for them to see the benefit of using our platform. We believe we have accomplished this in a simple, yet capable UI experience.

What we learned:

We learned about how to use vector embeddings for similarity search. We also learned how to tweak the confidence threshold such that the relevant responses actually match the queries we are looking for. Above all else, we learned just how many resources are used in day-to-day usage of ChatGPT. When starting this project, we had a prediction about LLM resource consumption, but we completely underestimated just how large it would be. These learnings made us realize that our project can have even more impact than we had anticipated.

What's next for SustainLLM:

We want to take the same processes and apply them to other modalities like audio and image generation. These modalities require significantly more compute than text generation, and if we could save even a small percentage of that compute, it could lead to drastic results. We are aware that creativity is a pivotal part of audio and image generation, and so we would use embeddings for lower-level things such as different pixel patterns or phonetics. That way, each generation can still be unique while consuming fewer resources.

Let’s save the environment, one LLM query at a time :)


