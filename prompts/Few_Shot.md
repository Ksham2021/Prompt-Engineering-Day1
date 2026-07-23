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
Sentiment: Positive

The review expresses satisfaction on two fronts — product quality ("amazing") and delivery experience ("arrived on time") — with no negative or mixed language present.

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
Sentiment: Positive

### Why the Improved Prompt is Better
The improved prompt provides examples of positive and negative reviews, helping the AI understand the expected classification format and produce a more reliable response.

---

# Prompt 2 – Grammar Correction

## Objective
Correct grammar while preserving meaning.

### Before Prompt
Correct the grammar:
"He don't likes playing football."

### Before Output
"He doesn't like playing football."

The fix: "don't" → "doesn't" (to agree with the third-person singular subject "he"), and "likes" → "like" (since "doesn't" already carries the -s, the main verb goes back to its base form).

### Improved Prompt
Correct the grammar using the examples.

Example:
Input: "She go to school everyday."
Output: "She goes to school every day."

Now correct:
"He don't likes playing football."

### After Output
"He doesn't like playing football."

### Why the Improved Prompt is Better
The improved prompt includes an example that demonstrates the expected correction style, helping the AI produce a more accurate and consistent grammatical correction.

---

# Prompt 3 – Product Category

## Objective
Classify products into categories.

### Before Prompt
Category: Apple iPhone 16

### Before Output
Weighed ambiguity and opted for clarification or overview
It looks like your message got cut off — just "Category: Apple iPhone 16" came through with no actual question attached.

Could you let me know what you'd like to know? For example:

Specs and pricing
Comparison with another phone
Whether it's still the latest model (there might be newer iPhones out by now)
Something else entirely (like a product listing or review you're writing)
Happy to dig into whichever one you meant.

### Improved Prompt
Classify products using these examples.

Example:
Nike Shoes → Footwear
Samsung TV → Electronics
Wooden Dining Table → Furniture

Now classify:
Apple iPhone 16

### After Output
Apple iPhone 16 → Electronics

### Why the Improved Prompt is Better
The improved prompt provides examples of product categories, making the expected classification format clear and improving the accuracy of the response.

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
{
  "Name": "Rahul",
  "Age": 22,
  "City": "Delhi"
}

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
{
  "name": "Rahul",
  "age": 22,
  "city": "Delhi"
}

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
Machine Learning (ML) is a branch of artificial intelligence where computers learn to make predictions or decisions by finding patterns in data, rather than being explicitly programmed with fixed rules for every situation.

The core idea

In traditional programming, a human writes explicit rules: "if X happens, do Y." In machine learning, you instead give the computer lots of examples (data), and it figures out the rules or patterns on its own.

For example:

Traditional approach to spam filtering: manually write rules like "if the email contains the word 'lottery' and 'free money', mark as spam."
ML approach: show the system thousands of emails labeled "spam" or "not spam," and let it learn which patterns (word combinations, sender behavior, etc.) tend to indicate spam.

Main types of machine learning

Supervised learning — the model learns from labeled examples (input paired with the correct output). Used for tasks like predicting house prices, classifying images, or detecting fraud.
Unsupervised learning — the model finds patterns or structure in data that has no labels, like grouping customers into segments based on purchasing behavior.
Reinforcement learning — an agent learns by trial and error, receiving rewards or penalties for actions, often used in robotics, game-playing AI, and recommendation systems.

How it actually works (simplified)

Collect data
Choose a model (a mathematical structure, like a neural network or decision tree)
Train the model by feeding it data and adjusting its internal parameters to minimize errors
Test the model on new, unseen data to check how well it generalizes
Deploy it to make predictions on real-world data

Common applications

Recommendation systems (Netflix, Spotify suggestions)
Image and speech recognition
Fraud detection
Predictive text and language models (like the one you're talking to right now)
Medical diagnosis assistance
Self-driving car perception systems

Where it fits in AI

Machine learning is a subset of artificial intelligence. Deep learning (using neural networks with many layers) is, in turn, a subset of machine learning that's especially good at handling unstructured data like images, audio, and text — it's the technology behind most modern AI breakthroughs, including large language models.

If you want, I can go deeper into any of these areas — like how neural networks actually work, or the math behind training a model.

### Improved Prompt
Answer the questions in this format.

Example:
Question: What is AI?
Answer: AI is the simulation of human intelligence by machines.

Now answer:
What is Machine Learning?

### After Output
Question: What is Machine Learning?
Answer: Machine Learning is a subset of AI where systems learn patterns from data and improve at tasks without being explicitly programmed for every rule, using algorithms to make predictions or decisions based on that data.

### Why the Improved Prompt is Better
The improved prompt provides an example of the expected question-and-answer format, helping the AI generate a concise and consistent response.

---

## Conclusion

Few-shot prompting improves the quality and consistency of AI responses by providing examples that guide the model toward the expected output format and style.
