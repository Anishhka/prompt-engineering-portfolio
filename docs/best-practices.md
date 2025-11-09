# Prompt Engineering Best Practices

*My learnings from studying prompt optimization*

---

## 1. Always Use Explicit Output Formatting

**Why:** Models often add conversational fluff that breaks parsing

**Example:**
```
❌ "Output JSON"
✅ "Output ONLY valid JSON between ###START### and ###END### markers"
```

---

## 2. Few-Shot Learning: 2-5 Examples is the Sweet Spot

**Research shows:**
- 0 examples (zero-shot): Works for common tasks, unpredictable for specialized ones
- 2-3 examples: Good baseline
- 5 examples: Optimal for most tasks
- 10+ examples: Diminishing returns, wastes tokens

---

## 3. Temperature Settings by Use Case

| Use Case | Temperature | Reasoning |
|----------|-------------|-----------|
| Data extraction | 0.0 - 0.2 | Need deterministic, consistent outputs |
| Creative writing | 0.7 - 0.9 | Want variety and originality |
| Customer support | 0.3 - 0.5 | Balance consistency with natural variation |
| Code generation | 0.2 - 0.3 | Need reliability with some flexibility |

---

## 4. Chain-of-Thought for Complex Tasks

**When to use:**
- Multi-step reasoning required
- Validation logic needed
- Accuracy is critical

**Approach:**
```
"Before outputting your answer:
1. Identify all relevant information
2. Validate against criteria
3. Format according to requirements"
```

---

## 5. Token Optimization Techniques

**Strategies I've learned:**
- Remove verbose explanations → use directive language
- Prune redundant examples
- Use abbreviations for repeated terms
- Test if fewer examples maintain accuracy

**Example optimization:**
```
❌ "Please carefully extract the supplier name from the document. 
    Make sure to get the exact name as it appears." (15 tokens)

✅ "Extract supplier_name exactly as written." (5 tokens)
```

---
## 6. Always Handle Edge Cases

**Common issues to address:**
- Missing data (return null vs empty string?)
- Multiple matches (return array vs first match?)
- Malformed input (error handling)
- Unexpected formats

---
## 7. Delimiter Technique for Parsing

**Problem:** Models add preambles like "Sure! Here's the JSON:"

**Solution:**
```
Output between these exact markers:
###START###
{your output}
###END###
```
**Result:** 100% parseable outputs

*These practices are compiled from Anthropic docs, OpenAI guides, and my own experiments. Looking forward to testing them in production environments!*
