# Hacking with NVIDIA NIM

I recently got a chance to hack around with NVIDIA's NIM API (that's a lot of capital letters in a row), and I gotta say...it's actually pretty dope.

NIM, short for NVIDIA Inference Microservices, basically helps you run models how you want to without relying on third parties. And it does this by making it easy to:

1. Deploy models on your own infrastructure.

2. Serve these models for multi-user inference.

3. Run models efficiently by making your NVIDIA GPUs go brrrrr.

4. Maintain control over your model deployment and customization without relying on third-party APIs.

5. Integrate into existing applications (this is beacuse it has an OpenAI API-compatible server).

### Alright, so what is a NIM?

<img src="https://developer-blogs.nvidia.com/wp-content/uploads/2024/04/NVIDIA-NIM-is-a-containerized-inference-microservice-including-industry-standard-APIs-domain-specific-code-optimized-inference-engines-and-enterprise-runtime.png">

It's basically a Docker container with three main components:

1. A server layer that provides an API for external interactions

2. A runtime layer that manages model execution

3. A model "engine" that contains the model weights and execution information

We're not going to get our hands dirty with an actual NIM container or Docker in this tutorial, instead I'll show you how to use the NIM API for tasks like text generation, video generation, and visual question answering.

I won't get into the technical details of the models that I'm using, as my main goal with this post is to help you get started using the NIM API as quickly as possible. To get started you'll need to sign up for a NIM API key, which you can do [here](https://nvda.ws/4bcJs0j). It's absolutely free to sign up for the API, there's no credit card required, and you get 1000 credits right off the bat.

**Full disclosure:** I'm part of NVIDIA's "influencer" program. I don't get paid any cash money from them, but they hook me up with credits to their API, plus send GPU hardware my way in exchange for reviewing their products and spreading the word about it to the community. By signing up [using my link](https://nvda.ws/4bcJs0j), all you're doing is signaling to them that they should continue to send me GPUs. Which, honestly, isn't too bad of a deal considering you'll also get 1000 credits to use towards the API!

Once you've signed up for an [API key](https://nvda.ws/4bcJs0j), go ahead run the code below so you can start hacking with me in this tutorial.