# Prompt Engineering Learning Portfolio

**Anishka Singh** | B.Tech AI/ML | Gurugram  
[LinkedIn]https://www.linkedin.com/in/anishka-singh2004/ |
[GitHub]https://github.com/Anishhka

---

## 👋 About This Portfolio

This is a **learning portfolio** I created to demonstrate my understanding of prompt engineering fundamentals. As a final-year AI/ML student, I've been studying how to optimize LLM outputs through systematic prompt design.

**What's Inside:**
- Prompt designs for common enterprise scenarios
- Application of techniques like Chain-of-Thought, Few-Shot Learning, and output formatting
- Testing methodology for measuring prompt effectiveness
- Documentation of best practices I've learned

**Status:** This is a demonstration/learning project showing my grasp of prompt engineering concepts. I'm eager to apply these skills in a professional setting.

---

## 🎯 Featured Prompt Designs

### 1. **Data Extraction from Invoices**
**Scenario:** Extract structured supplier data from unstructured invoices  
**Techniques:** Few-shot learning, explicit output formatting, temperature control  
**Goal:** Show understanding of master data management scenarios  
📁 [View Prompt](./prompts/data-extraction.json)

### 2. **JSON Output Enforcer**
**Scenario:** Ensure LLMs output 100% valid, parseable JSON  
**Techniques:** Delimiter system, strict instructions, temperature 0.0  
**Goal:** Demonstrate output reliability techniques  
📁 [View Prompt](./prompts/json-enforcer.json)

### 3. **Compliance Document Checker**
**Scenario:** Validate documents against regulatory standards (ISO 55001)  
**Techniques:** Structured validation, boolean logic, tag filtering  
**Goal:** Show understanding of enterprise compliance use cases  
📁 [View Prompt](./prompts/compliance-check.json)

### 4. **Customer-Facing Explanations**
**Scenario:** Generate clear, friendly explanations for technical concepts  
**Techniques:** Few-shot learning, tone control, example-based guidance  
**Goal:** Demonstrate customer experience optimization  
📁 [View Prompt](./prompts/customer-explanation.json)

### 5. **Material Code Extraction**
**Scenario:** Extract specific codes from energy sector documents  
**Techniques:** Pattern matching instructions, format validation  
**Goal:** Show domain-specific data extraction  
📁 [View Prompt](./prompts/material-code-extractor.json)

---

## 🧪 Testing Methodology

I designed a framework to compare prompt approaches:

**Testing Approach:**
- Compare baseline (simple) vs optimized (technique-enhanced) prompts
- Measure output consistency and token efficiency
- Document which techniques provide the best improvements

**Sample Comparison:**

| Approach | Techniques Used           | Ex. Consistency|Token Efficiency|
|----------|-------------------------- |-----------|---------------------|
| Baseline |Simple instruction         |      ~70% |    Baseline         |
| Improved | + Examples, + CoT         |      ~90% |   ~30% reduction    |
| Optimized| + Delimiters, temp tuning |     ~95%+ |   ~40% reduction    |

*Note: These targets are based on prompt engineering best practices literature. Real production validation would require extensive testing on actual business data.*

---

## 📚 Key Concepts I've Studied

### **Chain-of-Thought (CoT) Prompting**
Breaking down complex tasks into step-by-step reasoning improves accuracy for multi-step problems.

### **Few-Shot Learning**
Providing 2-5 examples helps models understand desired output format and handling of edge cases.

### **Temperature Control**
- **0.0-0.2:** Deterministic outputs for production systems
- **0.3-0.5:** Balanced creativity and consistency
- **0.7-1.0:** Creative/diverse outputs

### **Output Formatting**
Using explicit delimiters and strict format instructions ensures parseable, consistent outputs.

### **Token Optimization**
Removing verbose instructions and redundant examples reduces API costs without sacrificing quality.

---

## 🛠️ Technical Stack

**Models I've Studied:**
- OpenAI GPT-4o
- Anthropic Claude 3.5 Sonnet
- Meta Llama 3

**Tools & Languages:**
- Python for testing scripts
- JSON for prompt design
- Markdown for documentation

---

## 📖 Learning Resources

Resources that helped me understand prompt engineering:

- [Anthropic's Prompt Engineering Guide](https://docs.anthropic.com/claude/docs/prompt-engineering)
- [OpenAI Best Practices](https://platform.openai.com/docs/guides/prompt-engineering)
- Academic papers on few-shot learning and prompt optimization
- Hands-on experimentation with various LLM APIs

---

## 🎯 What I'm Looking For

I'm seeking an **entry-level prompt engineering role** where I can:
- Apply these foundational concepts to real production systems
- Learn from experienced practitioners
- Contribute to solving actual business problems
- Grow my technical skills through mentorship and hands-on work

**Availability:** Immediate  
**Location:** Gurugram, India (open to remote)

---

## 🚀 Next Steps in My Learning Journey

**Skills I want to develop:**
- RAG (Retrieval Augmented Generation) systems
- Prompt security and adversarial testing
- Multi-agent prompt architectures
- Cost optimization at scale
- A/B testing in production environments

---

## 📬 Let's Connect

I'm actively seeking opportunities to start my career in prompt engineering!


💼 LinkedIn:https://www.linkedin.com/in/anishka-singh2004/
🐙 GitHub: https://github.com/Anishhka

---

*This portfolio represents my self-directed learning in prompt engineering. I'm eager to validate and expand these concepts through real-world experience.*
