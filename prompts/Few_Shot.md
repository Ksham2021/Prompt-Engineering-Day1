# Few-Shot Prompting

## Learning Objective

Few-shot prompting improves AI responses by providing one or more examples before asking the actual task. This helps the model understand the expected format and style.

---

# Prompt 1 – Sentiment Analysis

## Objective
Classify customer reviews as Positive, Negative, or Neutral.

### Before Prompt
Classify the sentiment of this review:
"The product is amazing and arrived on time."

### Before Output
(To be added after testing in Claude.)

### Improved Prompt
Classify the sentiment using the examples below.

Example 1:
Review: "Excellent quality and fast delivery."
Sentiment: Positive

Example 2:
Review: "The product stopped working after one day."
Sentiment: Negative

Now classify:
Review: "The product is amazing and arrived on time."

### After Output
(To be added after testing in Claude.)

### Why the Improved Prompt is Better
- Demonstrates the expected format.
- Improves classification accuracy.

---

# Prompt 2 – Grammar Correction

## Objective
Correct grammar while preserving meaning.

### Before Prompt
Correct the grammar:
"He don't likes playing football."

### Before Output
(To be added after testing in Claude.)

### Improved Prompt
Correct the grammar using the examples.

Example:
Input: "She go to school everyday."
Output: "She goes to school every day."

Now correct:
"He don't likes playing football."

### After Output
(To be added after testing in Claude.)

### Why the Improved Prompt is Better
- Shows the expected correction style.
- Produces more consistent output.

---

# Prompt 3 – Product Category

## Objective
Classify products into categories.

### Before Prompt
Category: Apple iPhone 16

### Before Output
(To be added after testing in Claude.)

### Improved Prompt
Classify products using these examples.

Example:
Nike Shoes → Footwear
Samsung TV → Electronics
Wooden Dining Table → Furniture

Now classify:
Apple iPhone 16

### After Output
(To be added after testing in Claude.)

### Why the Improved Prompt is Better
- Uses examples for guidance.
- Makes the expected output clear.

---

# Prompt 4 – JSON Formatting

## Objective
Convert information into JSON.

### Before Prompt
Convert this into JSON:
Name: Rahul
Age: 22
City: Delhi

### Before Output
(To be added after testing in Claude.)

### Improved Prompt
Convert the information into JSON.

Example:

Input:
Name: Amit
Age: 20
City: Mumbai

Output:
{
  "name": "Amit",
  "age": 20,
  "city": "Mumbai"
}

Now convert:

Name: Rahul
Age: 22
City: Delhi

### After Output
(To be added after testing in Claude.)

### Why the Improved Prompt is Better
- Shows the desired JSON structure.
- Reduces formatting errors.

---

# Prompt 5 – Question Answering

## Objective
Answer factual questions briefly.

### Before Prompt
What is Machine Learning?

### Before Output
(To be added after testing in Claude.)

### Improved Prompt
Answer the questions in this format.

Example:
Question: What is AI?
Answer: AI is the simulation of human intelligence by machines.

Now answer:
What is Machine Learning?

### After Output
(To be added after testing in Claude.)

### Why the Improved Prompt is Better
- Demonstrates the response style.
- Produces concise and consistent answers.

---

## Conclusion

Few-shot prompting improves the quality and consistency of AI responses by providing examples that guide the model toward the expected output format and style.
