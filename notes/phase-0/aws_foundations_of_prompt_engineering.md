# Intro
- prompts are instuctions
- quality and structure impact output

# Basics of foundation models
- Like all other AI, generative AI uses machine learning (ML) models. However, generative AI uses very large models, commonly called foundation models. 
- FMs use deep neural networks to emulate human brain functionality and handle complex tasks.
- text generation, text summarization, information extraction, image generation, chatbots, and question answering
- They take unlabeled data > Pretrain > Foundation model > Adapt > use cases above
- FMs are typically pretrained through self-supervised learning. With self-supervised learning, you don't need labeled examples.

## Training
- during training foundation models use self supervised learning or reinforced learning from human feedback
- FM can learn the meaning context and relationship of words in datasets
- **example** : model will learn difference between drink the beverage, the noun or swallowing liquid
-  reinforcement is used to to better align the model with feedback to change behavior
## Fine Tuning
- Fine-tuning the FM base model can improve performance. Fine-tuning is a supervised learning process that involves taking a pretrained model and adding specific, smaller datasets.
- 2 Ways to fine tune the model
1. **Instruction fine-tuning** uses examples of how the model should respond to a specific instruction. Prompt tuning is a type of instruction fine-tuning.
2. **RLHF** provides human feedback data, resulting in a model that is better aligned with human preferences.
**If you are working on a task that requires industry knowledge, you can take a pretrained model and fine-tune the model with industry data. If the task involves medical research, for example, the pretrained model can be fine-tuned with articles from medical journals to achieve more contextualized results.**
##Prompt Engineering
- Prompts act as instructions for foundation models.
- You use various prompt techniques to achieve better performance.

## Types of FMs
- **text to text**
-  pretrained to process vast quantities of textual data and human language.
-  NLP Natural language processing: enables machines to interpret and respond to human language through techniques like tokenization and sentiment analysis, though modern LLMs have largely bypassed the need for those intermediate steps.
- Recurrent neural network (RNN): use a memory mechanism to store and apply data from previous inputs. effective for sequential data and tasks, such as natural language processing, speech recognition, or machine translation.
  - **slow and complex to train**
- Transformer: Transformers are a deep-learning architecture that processes text in parallel (unlike older RNNs), making training faster but more compute-intensive, and their encoder-decoder design became the foundation for modern LLMs.

- **Text to image**
- Text-to-image models take natural language input and produce a high-quality image that matches the input text description.
- Diffusion architecture: Diffusion models generate images by learning to add noise to an image and then reverse that process, guided by text input, to produce new images.

- LLMS: LLMs are massive foundation models trained on vast text data that can generate human-like text, hold conversations, and perform a wide range of language tasks across industries.

## neural net layers
- Embedding layer — converts text to vector representations to capture context and relationships
- Feedforward layer — transforms embeddings into weighted versions to better understand intent
- Attention mechanism — focuses on the most relevant parts of the input for more accurate output

## Generative AI Use Cases

- **Chatbots & virtual assistants** — automate customer service responses
- **Call analytics** — extract insights from contact center calls
- **Agent assist** — AI support for human agents in service and decision-making
- **Conversational search** — find and summarize information via chat interface
- **Code generation** — suggest code based on developer comments and context
- **Automated reporting** — generate financial reports and summaries
- **Marketing** — create blog posts, social content, and email campaigns
- **Sales** — personalized outreach and scripts based on prospect profiles
- **Product development** — generate and optimize design prototypes
- **Media & entertainment** — write scripts, dialogues, and story completions
- **News generation** — produce articles or summaries from raw data
- **Document processing** — extract and summarize data from documents
- **Fraud detection** — learn fraud patterns and generate synthetic training data
- **Supply chain** — evaluate and optimize logistics scenarios

# Fundamentals of Prompt Engineering
- Prompt engineering is an emerging field that focuses on developing, designing, and optimizing prompts to improve the output of LLMs
- Prompt engineering is an emerging field that focuses on developing, designing, and optimizing prompts to improve the output of LLMs
- Prompt engineering guides a pre-trained model to produce better outputs, while fine-tuning actually modifies the model's weights using training data — making prompt engineering far cheaper and faster than fine-tuning.
- Prompt engineering is the fastest way to leverage LLMs — by crafting effective inputs you can improve output quality, boost safety, add domain knowledge, and unlock model capabilities without touching model parameters.

**Key benefits:**
- Boost model abilities and improve safety
- Augment with domain knowledge and external tools without fine-tuning
- Better understand model capabilities through interaction
- Better inputs produce better outputs

## Elements of a Prompt

- **Instructions** — describes the task or how to perform it
- **Context** — background information to guide the model
- **Input data** — the specific input you want a response for
- **Output indicator** — specifies the desired output type or format

## Prompt Elements — Worked Example

Input: Write a summary of a service review using two sentences.

Store: Online, Service: Shipping.

Review: Amazon Prime Student is a great option for students looking to save money. Not paying for shipping is the biggest save in my opinion. As a working mom of three who is also a student, it saves me tons of time with free 2-day shipping, and I get things I need quickly and sometimes as early as the next day, while enjoying all the free streaming services, and books that a regular prime membership has to offer for half the price. Amazon Prime Student is only available for college students, and it offers so many things to help make college life easier. This is why Amazon Prime is the no-brainer that I use to order my school supplies, my clothes, and even to watch movies in between classes. I think Amazon Prime Student is a great investment for all college students.

output:Amazon Prime Student is a fantastic option for college students, offering free 2-day shipping, streaming services, books, and other benefits for half the price of a regular Prime membership. It saves time and money, making college life easier.

| Element | Example |
|---|---|
| **Instruction** | "Write a summary of a service review..." |
| **Context** | "Store: Online, Service: Shipping" |
| **Input data** | The full Amazon Prime Student review |
| **Output indicator** | "...using two sentences" |

**Output:**
> Amazon Prime Student is a fantastic option for college students, offering free 2-day shipping, streaming services, books, and other benefits for half the price of a regular Prime membership. It saves time and money, making college life easier.

## Tips for Designing Effective Prompts

- **Be clear and concise** — use natural language, avoid jargon and ambiguity
  - ❌ "Compute the sum total of the subsequent sequence of numerals: 4, 8, 12, 16"
  - ✅ "What is the sum of these numbers: 4, 8, 12, 16?"

- **Include context if needed** — tell the model what the output is for
  - ❌ "Summarize this article: [text]"
  - ✅ "Provide a summary of this article to be used in a blog post: [text]"

- **Use directives for response type** — specify format, length, inclusions, exclusions
  - ❌ "What is the capital?"
  - ✅ "What is the capital of New York? Provide the answer in a full sentence."

- **Consider the output in the prompt** — state the desired output at the end to keep the model focused
  - ❌ "Calculate the area of a circle."
  - ✅ "Calculate the area of a circle with a radius of 3 inches. Round to the nearest integer."

- **Start with an interrogation** — use who, what, where, when, why, how
  - ❌ "Summarize this event."
  - ✅ "Why did this event happen? Explain in three sentences."

- **Provide an example response** — show the expected format in brackets
  - ❌ "Determine the sentiment of this post: [post]"
  - ✅ Include labeled examples: `post: "great pen" => Positive`

- **Break up complex tasks** — split into subtasks, ask the model to think step by step, or ask it to divide the task itself

- **Experiment and be creative** — test different prompts, note what works, adjust accordingly
- **You can even ask one copy of the model to improve or check output from another copy of the model.**

# Basic Prompt Techniques
## Zero-Shot Prompting

A technique where you give the model a task with **no examples** — the model performs it based on its training alone. Modern LLMs handle this well, especially larger models.

**Tips:**
- Larger LLMs produce better zero-shot results
- Instruction tuning (e.g. RLHF) improves zero-shot performance

**Example:**

| Prompt | Output |
|---|---|
| "Tell me the sentiment of the following social media post and categorize it as positive, negative, or neutral: *Don't miss the electric vehicle revolution! AnyCompany is ditching muscle cars for EVs, creating a huge opportunity for investors.*" | Positive |

> No examples were provided — the model inferred the task from the instruction alone.

## Few-Shot Prompting

A technique where you provide the model with **example input/output pairs** in the prompt to guide its behavior. More context = closer alignment to your desired output.

**Tips:**
- Labels in examples don't need to be perfectly correct — even random labels outperform no labels at all
- The **label space and input distribution** in your examples matter more than label accuracy
- For large example sets, use an **example selector based on semantic similarity** to stay within token limits and dynamically populate prompt templates

**Example structure:**
```
post: "great pen" => Positive
post: "I hate when my phone battery dies" => Negative
post: "I got a package today" => Neutral
post: [insert new post] =>
```

> The model uses the provided examples to infer the pattern and apply it to new input.

## Chain-of-Thought (CoT) Prompting

A technique that breaks complex reasoning into **intermediary steps**, improving accuracy on multi-step problems. Works with both zero-shot and few-shot approaches. Invoke it with the phrase **"Think step by step."**

> **When to use:** Tasks involving several steps or a series of reasoning.

---

### CoT Zero-Shot Example

| Prompt | Output |
|---|---|
| "Which vehicle requires a larger down payment? Vehicle A: $40,000 at 30%. Vehicle B: $50,000 at 20%. (Think step by step)" | Model calculates A = $12,000, B = $10,000 → Vehicle A requires the larger down payment |

---

### CoT Few-Shot Example

Combines a worked example (few-shot) with "Think step by step" (CoT):

```
Q: Monday 6,500 / Tuesday 6,400 / Wednesday 6,300 — how many viewers on Friday?
A: Daily decrease of 100 → Thursday 6,200 → Friday 6,100.

Q: How many viewers on Saturday? (Think step by step)
A: [model continues the pattern]
```

---

### Summary

| Technique | Examples Provided | Step-by-Step Reasoning |
|---|---|---|
| Zero-shot CoT | ❌ | ✅ |
| Few-shot CoT | ✅ | ✅ |

## Self-Consistency Prompting

Similar to CoT, but instead of one reasoning path, the model **samples multiple reasoning paths** and aggregates them into a final answer. More robust than standard CoT for arithmetic and common-sense reasoning.

---

### Why It Matters

Single CoT can follow a plausible but incorrect path. Self-consistency cross-checks multiple approaches to arrive at the right answer.

**Single CoT (incorrect):**
| Prompt | Output |
|---|---|
| "When I was 10, my sister was half my age. Now I'm 30. How old is my sister?" | 25 ❌ |

**Self-Consistency (correct):**
| Prompt | Output |
|---|---|
| Same question, but primed with a worked example using similar reasoning structure | 35 ✅ |

---

### How It Works

1. Model samples **multiple reasoning paths** for the same problem
2. Each path may reach the answer differently
3. Model **aggregates** across paths → most consistent answer wins

> Think of it like asking several people to solve a problem independently, then going with the majority answer.

## Tree of Thoughts (ToT) Prompting

Builds on CoT by exploring **multiple reasoning branches simultaneously** rather than one sequential path. The model self-evaluates each branch and pursues the most promising ones.

> **When to use:** Tasks involving planning, important initial decisions, or exploration of multiple solutions.

---

### CoT vs. ToT

| | CoT | ToT |
|---|---|---|
| Reasoning path | Single, sequential | Multiple, branching |
| Self-evaluation | ❌ | ✅ |
| Best for | Step-by-step arithmetic | Planning, strategy, exploration |

---

### Performance Example — Game of 24

| Method | GPT-4 Success Rate |
|---|---|
| CoT prompting | 4% |
| ToT prompting | 74% |

---

### How It Works

1. Model generates **multiple candidate thoughts** at each step
2. Each branch is evaluated for viability
3. Promising branches are explored further; dead ends are pruned
4. Final answer is drawn from the best-performing path

> Think of it like a decision tree — instead of committing to one path immediately, the model explores options before going deep.

## Retrieval Augmented Generation (RAG)

A prompting technique that **pulls relevant documents from an external knowledge base** and supplies them as context to the model at inference time — no model retraining required.

---

### RAG vs. Fine-Tuning

| | RAG | Fine-Tuning |
|---|---|---|
| Changes model weights | ❌ | ✅ |
| Cost | Lower | Higher |
| Handles data updates | ✅ (retrieves live data) | ❌ (requires retraining) |
| Needs labeled examples | ❌ | ✅ |

---

### How It Works

1. **Prepare knowledge base** — ingest documents from repos, databases, or APIs
2. **Retrieve** — relevant documents are fetched based on the user's query
3. **Augment** — retrieved docs are injected into the prompt as context
4. **Generate** — model produces a response grounded in the retrieved data

---

### Key Benefits

- More cost-efficient than fine-tuning
- Keeps responses current without retraining
- Works with multiple data sources (documents, databases, APIs)

> RAG is essentially giving the model a reference library to look things up in, rather than expecting it to have memorized everything during training.

## Automatic Reasoning and Tool-use (ART)

Builds on CoT by combining **multi-step reasoning with external tool use** — automating the process of selecting examples and calling tools to complete complex tasks.

---

### How It Works

1. Selects relevant **few-shot examples** from a task library
2. Breaks the task into **multi-step reasoning** steps (like CoT)
3. Calls **predefined external tools** (e.g. search, code generation) where needed
4. Aggregates results into a final output

---

### ART vs. Other Techniques

| | Few-Shot | Auto CoT | ART |
|---|---|---|---|
| Uses external tools | ❌ | ❌ | ✅ |
| Multi-step reasoning | ❌ | ✅ | ✅ |
| Auto example selection | ❌ | ✅ | ✅ |
| Updatable task library | ❌ | ❌ | ✅ |

---

### Key Benefits

- Outperforms few-shot and automatic CoT on unseen tasks
- Matches handcrafted CoT prompts on many tasks
- Task libraries can be updated to correct errors and improve over time

> Think of ART as CoT with a toolbelt — instead of just reasoning through a problem, it can reach out to external tools mid-task to get what it needs.

## ReAct Prompting

A framework that combines **reasoning + action** in a loop — the model thinks through a problem, takes an action using an external tool, observes the result, and reasons again until it reaches a final answer.

> Solves a key CoT limitation: CoT can reason but can't reach out for current or accurate external data, leading to hallucinations.

---

### ReAct Loop

```
Thought → Action → Observation → Thought → ... → Final Answer
```

---

### Example 1 — Calculator Tool

| | Output |
|---|---|
| Claude without calculator | 2.8337... ❌ |
| Claude with calculator (ReAct) | 1.1517... ✅ |

The model recognized it needed math, called the calculator tool, and used the result.

---

### Example 2 — SQL + Calculator Tools

**Query:** Price ratio for stock 'ABC' between 2023-01-03 and 2023-01-04

```
Thought: I need historical prices
Action: Stock DB → SELECT price WHERE ticker = 'ABC' AND date BETWEEN ...
Observation: 232.0 (Jan 3), 225.0 (Jan 4)
Thought: Now I can compute the ratio
Final Answer: 232.0 / 225.0 = 1.0311
```

---

### ReAct vs. CoT

| | CoT | ReAct |
|---|---|---|
| Reasoning | ✅ | ✅ |
| External tool access | ❌ | ✅ |
| Real-time / accurate data | ❌ | ✅ |
| Hallucination risk | Higher | Lower |

> **ReAct is essentially the foundation of how modern AI agents work — reason, act, observe, repeat.**

# Multimodal Prompt Engineering
## Multimodal Prompt Engineering

Crafting prompts for AI models that can process and generate **multiple media types** — text, images, audio, and video — rather than text alone.

---

### What Makes It Different

Traditional LLMs process text only. Multimodal models understand **relationships between media types**, mimicking how humans naturally combine visual and language understanding.

> When you look at a photo, you don't just identify objects — you infer context, emotion, and relationships. Multimodal models attempt to replicate this.

---

### How It Works

- Different media types are encoded into a **shared representation space**
- Specialized neural networks handle each input type
- Those networks communicate to produce integrated understanding
- Models are trained on large datasets of **paired text-image examples**

---

### Strengths

- Image description and captioning
- Visual question answering
- Cross-modal content analysis
- Context-rich, natural interactions

---

### Limitations

- Struggles with **fine-grained detail** and spatial reasoning
- Difficulty with **abstract visual concepts**
- Sensitive to image quality and lighting
- Output quality depends heavily on **how the prompt is structured**

> Thoughtful prompt design matters even more with multimodal models — the same image can produce very different results depending on how you ask about it.

## Text & Image Prompting Techniques

---

### 1. Clear, Specific Instructions
Reference both the image content and the desired output format explicitly.

- ❌ "What's in this image?"
- ✅ "Analyze this product photograph and create a detailed marketing description highlighting the key features visible in the image."

---

### 2. Contextual Framing
Provide background information to help the model interpret the image more accurately.

> "This image was taken during the 1960s civil rights movement. Describe the scene and explain its historical significance based on the visual elements you observe."

---

### 3. Sequential Questioning
Start broad, then drill into specifics.

> "First, provide an overall description of this medical scan. Then, identify any abnormalities you notice and describe their location and characteristics."

---

### 4. Role-Based Prompting
Ask the model to adopt a professional perspective when analyzing the image.

- "As a professional interior designer, evaluate this room layout and suggest improvements."
- "From a cybersecurity expert's perspective, identify potential vulnerabilities in this network diagram."

---

### 5. Iterative Refinement
Start general, then refine based on the model's response.

```
Prompt 1: "What is happening in this image?"
→ Model gives general answer
Prompt 2: "Can you describe the emotions of the people involved?"
→ Deeper, more targeted insight
```

---

> The common thread: the more precisely you guide the model on **what to look at** and **how to respond**, the more useful the output.

# Domain Specific Prompt Engineering

## Domain Adaptation Principles

Tailoring prompts to match the **specific language, terminology, and conventions** of a professional field — moving beyond generic prompts to industry-aware instructions.

---

### 1. Contextual Specificity
Provide enough domain background so the model can respond accurately.

- Medical: specify human medicine vs. veterinary vs. research — protocols differ
- Financial: clarify personal finance vs. corporate vs. investment banking vs. compliance — each has distinct requirements

---

### 2. Terminology Precision
Use the correct technical terms, acronyms, and field-specific language consistently. Define ambiguous terms that may mean different things across contexts.

> Precise language = responses that match professional expectations, not generic outputs.

---

### 3. Regulatory & Ethical Awareness
In regulated fields (healthcare, finance, law), prompts should encourage responses that:

- Acknowledge relevant regulations and compliance requirements
- Flag ethical considerations and professional standards
- Note limitations and the need for professional oversight

---

### 4. Output Formatting & Structure
Specify not just **what** you need, but **how** it should be presented to meet domain standards.

| Domain | Convention |
|---|---|
| Legal | Specific document formatting standards |
| Medical | Standardized record structures |
| Financial | Established report templates |

---

> Domain adaptation is essentially giving the model enough professional context to respond like a knowledgeable practitioner, not a generalist.

## Domain-Specific Prompt Engineering: Healthcare, Finance & Legal

---

## Healthcare

**Key requirements:**
- Maintain patient confidentiality (HIPAA compliance)
- Use accurate medical terminology
- Follow structured medical documentation formats
- Support clinicians — never replace clinical judgment

**Common applications:**
- Patient care summaries
- Medical report analysis
- Treatment plan recommendations
- Patient education materials

**Best practices:**
- Include disclaimers about AI limitations
- Specify target audience (patient, provider, researcher)
- Flag that all AI-generated content requires verification by qualified practitioners
- Account for reading level and cultural considerations in patient-facing content

---

## Finance

**Key requirements:**
- Precise handling of numerical data
- Regulatory compliance (SEC, Basel standards, jurisdiction-specific rules)
- Risk assessment frameworks
- Time-sensitive information handling

**Common applications:**
- Financial analysis and reporting
- Customer service
- Fraud detection (pattern and anomaly recognition in transaction data)
- Investment advisory support

**Best practices:**
- Specify jurisdiction and applicable regulations
- Distinguish between general information and personalized financial advice
- Include disclaimers about past performance and market risk
- Account for market volatility, regulatory changes, and individual risk tolerance

---

## Legal

**Key requirements:**
- Precise legal terminology and citation formats
- Jurisdiction-specific requirements
- Handling of complex legal documents and case law
- Clarity about the preliminary nature of AI-generated drafts

**Common applications:**
- Legal research
- Contract and document drafting support
- Case analysis
- Regulatory compliance checks

**Best practices:**
- Always specify jurisdiction and area of law
- State the intended use (research, drafting, client communication)
- Emphasize that all output requires review by a qualified attorney
- Account for industry standards and specific transaction circumstances

---

## Cross-Domain Rules

| Principle | Healthcare | Finance | Legal |
|---|---|---|---|
| Use domain terminology | ✅ | ✅ | ✅ |
| Regulatory awareness | HIPAA | SEC / Basel | Jurisdiction-specific |
| AI replaces professionals | ❌ | ❌ | ❌ |
| Disclaimers required | ✅ | ✅ | ✅ |
