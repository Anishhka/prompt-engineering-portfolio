# My Testing Approach

## How I Would Test Prompts in Production

### 1. **Define Success Metrics**
- Accuracy/correctness
- Consistency (same input → same output)
- Token efficiency
- Latency
- Cost per request

### 2. **Create Test Cases**

**Example for JSON Enforcer:**
```python
test_cases = [
    {
        "input": "Extract data: John Smith, age 30, NYC",
        "expected_format": "valid JSON",
        "edge_case": "simple case"
    },
    {
        "input": "Extract: Name: Sarah O'Brien (note: apostrophe)",
        "expected_format": "valid JSON with escaped quote",
        "edge_case": "special characters"
    },
    {
        "input": "Extract: [empty document]",
        "expected_format": "valid JSON with null values",
        "edge_case": "missing data"
    }
]
```

### 3. **Compare Approaches**

| Test Case | Baseline Prompt | Optimized Prompt | Winner |
|-----------|----------------|------------------|---------|
| Simple extraction | ✅ Works | ✅ Works | Tie |
| Special chars | ❌ Breaks parsing | ✅ Handles correctly | Optimized |
| Missing data | ❌ Returns error text | ✅ Returns null in JSON | Optimized |

### 4. **Measure Token Usage**
```python
def count_tokens(prompt, response):
    # Use tiktoken or similar
    return prompt_tokens + response_tokens

baseline_avg = 312 tokens
optimized_avg = 206 tokens
savings = 34%
```

### 5. **Iterate Based on Failures**

**Example iteration:**
- v1: Basic instruction → 70% success
- v2: Added examples → 90% success
- v3: Added delimiters → 98% success
- v4: Tuned temperature → 99% success

---

## Testing Framework Structure
```python
# Pseudocode for how I'd structure testing

class PromptTester:
    def __init__(self, prompt, test_cases):
        self.prompt = prompt
        self.test_cases = test_cases
        
    def run_tests(self):
        results = []
        for case in self.test_cases:
            response = call_llm(self.prompt, case['input'])
            results.append({
                'success': validate(response, case['expected']),
                'tokens': count_tokens(response),
                'latency': measure_time()
            })
        return self.analyze_results(results)
        
    def analyze_results(self, results):
        return {
            'success_rate': sum(r['success']) / len(results),
            'avg_tokens': mean([r['tokens'] for r in results]),
            'avg_latency': mean([r['latency'] for r in results])
        }
```

---

*This is my conceptual testing framework. In a professional role, I'd expand this with proper CI/CD integration, automated regression testing, and production monitoring.*
