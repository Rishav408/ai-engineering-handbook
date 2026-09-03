# 1.5 Common Terminology (Glossary)

Terms used throughout this repository, defined once here so every other note can link back instead of re-explaining them.

| Term | Definition |
|---|---|
| **AI vs AGI** | AI = narrow, task-specific intelligence — what every LLM today actually is. AGI = hypothetical general intelligence matching or exceeding human cognitive ability across all domains. No AGI exists yet; "AI" in this repo always means the narrow kind. |
| **LLM (Large Language Model)** | A neural network, almost always Transformer-based, trained on massive text corpora to predict and generate text one token at a time. |
| **Embeddings** | Dense vector representations of text or other data that capture semantic meaning — lets you compare "meaning similarity" between two pieces of content mathematically instead of just matching keywords. |
| **Training** | Updating a model's weights on data. Pre-training builds a model from scratch on a huge dataset; fine-tuning adapts an already-trained model to a narrower task. |
| **Inference** | Running an already-trained model to generate an output. This is what happens every time you send a prompt to an LLM API — no training happens at inference time. |
| **Vector DBs** | Databases built to store and query high-dimensional embedding vectors efficiently, usually via similarity search (finding the closest vectors to a query vector). |
| **AI Agents** | Systems that use an LLM to reason, plan, and autonomously call tools or APIs to complete multi-step tasks, rather than just answering a single question. |
| **RAG (Retrieval-Augmented Generation)** | Retrieve relevant external data and inject it into the prompt before the model generates a response — grounds the answer in real, current information instead of only what the model learned during training. |
| **Context Window** | The maximum number of tokens (input + output combined) a model can process in a single call. System instructions, retrieved documents, conversation history — everything has to fit inside this limit. |
| **Fine-tuning** | Further training a pre-trained model on a smaller, task-specific dataset to specialize its behavior for a narrower use case than the base model was designed for. |
| **Prompt Engineering** | Crafting inputs — instructions, examples, structure — to reliably get the output you want from a model. |
| **Context Engineering** | The broader discipline prompt engineering sits inside: deciding what information *beyond* the prompt gets fed to the model — memory, retrieved documents, tool outputs, conversation state. |

## Using this glossary

Every note in this repository links back here on first use of a term instead of re-defining it inline. Contributing a new note that relies on a term not listed above? Add it here first.

---
**Next:** [2. Working With LLMs →](../02-working-with-llms/)