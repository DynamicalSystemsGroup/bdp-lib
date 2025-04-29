# AI for BDP

## Executive Summary

This research note is on the idea of using AI to translate information into block diagram protocol objects automatically.

## TestGen-LLM Review

- Literature review with the [paper on TestGen-LLM](https://arxiv.org/abs/2402.09171) provided a starting point for how to build out the apparatus for building and testing this idea

### Offline LLMSE

- "That is, unlike other LLM-based code and test generation techniques, TestGen-LLM uses Assured Offline LLMSE to embed the language models, as a service, in a larger Software Engineering workflow that ultimately recommends fully formed software improvements rather than smaller code snippets. These fully-formed code improvements are backed by verifiable guarantees for improvement and non-regression of existing behavior. A filtration process discards any test case that cannot be guaranteed to meet the assurances."
- The paper points to the benefits of crafting an offline LLM for use in this flow
- This paper was focused on a similar but slightly different goal of increasing test case coverage: "As part of our overall mission to automate Unit Test generation for Android code, we have developed an automated test class improver, TestGen-LLM. TestGen-LLM uses two of Meta's ${ }^{1}$ Large Language Models (LLMs) to extend existing, human-written, Kotlin test classes by generating additional test cases that cover previously missed corner cases, and that increase overall test coverage. TestGen-LLM is an example of Assured Offline LLM-Based Software Engineering (Assured Offline LLMSE) [6]."

### Infrastructure Use Cases

- "However, the same infrastructure can also be used as a kind of ensemble learning approach to find test class improvement recommendations. TestGenLLM thus has two use cases:
(1) Evaluation: To evaluate the effects of different LLMs, prompting strategies, and hyper-parameters on the automatically measurable and verifiable improvements they make to existing code.
(2) Deployment: To fully automate human-independent test class improvement, using a collection of LLMs, prompting strategies, and hyper-parameters to automatically produce code improvement recommendations that are backed by"
- **We also likely want to think about the problem in the same way - both improving our methodology (point 1) and also deploying for use (point 2)**
- "The evaluation mode was used as a prelude to deployment, allowing us to investigate and tune such choices of LLM, prompt strategy and temperature. It was also used after initial deployment to tune parameters for the subsequent, more widespread, release of the tool to engineers at Meta."