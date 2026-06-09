# Google Cloud: Prompt Engineering Guide — Summary

---

## What is Prompt Engineering?
The art and science of designing prompts to guide AI models toward generating desired responses. Provides the model with context, instructions, and examples to understand intent and respond meaningfully.

---

## Key Elements of Effective Prompts

- **Prompt format** — structure and style matter; different models prefer different formats
- **Context and examples** — helps the AI understand the task and generate more accurate output
- **Fine-tuning and adapting** — adjust prompts based on feedback and outputs over time
- **Multi-turn conversations** — design prompts for continuous, context-aware interactions

---

## Types of Prompts

| Type | Description |
|---|---|
| **Zero-shot (Direct)** | No examples — direct instruction or question only |
| **One/Few/Multi-shot** | Provide example input-output pairs before the actual prompt |
| **Chain of Thought (CoT)** | Break reasoning into intermediate steps for better output |
| **Zero-shot CoT** | CoT reasoning without examples — ask model to show its work |

---

## Use Cases

### Language & Text
- Creative writing — specify genre, tone, style, plot
- Summarization — provide text, request concise summary
- Translation — specify source and target language
- Dialogue — simulate conversations with role context

### Question Answering
- Open-ended, specific, multiple choice, hypothetical, opinion-based questions

### Code Generation
- Code completion, translation, optimization, debugging

### Image Generation
- Photorealistic, artistic, abstract images, and image editing

---

## Strategies for Better Prompts

**1. Set Clear Goals**
- Use action verbs ("Write", "Summarize", "Analyze")
- Define output length and format
- Specify target audience

**2. Provide Context**
- Include relevant facts and data
- Reference specific sources or documents
- Define key terms for the intended audience

**3. Use Few-Shot Prompting**
- Provide example input-output pairs
- Demonstrate desired style, tone, and level of detail

**4. Be Specific**
- Use precise language, avoid ambiguity
- Quantify requests where possible
- Break complex tasks into numbered steps

**5. Iterate and Experiment**
- Try different phrasings and keywords
- Adjust level of detail
- Test different prompt lengths

**6. Use Chain of Thought**
- Encourage step-by-step reasoning
- Ask the model to explain its reasoning process
- Guide through a logical sequence of thought

---

## Benefits of Prompt Engineering

- **Improved model performance** — clearer prompts produce more accurate, relevant outputs
- **Reduced bias** — careful prompt design helps mitigate harmful or biased responses
- **Increased control** — consistent, predictable outputs aligned with desired outcomes
- **Enhanced user experience** — intuitive interactions with AI models
