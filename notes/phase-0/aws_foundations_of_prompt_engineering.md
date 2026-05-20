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


