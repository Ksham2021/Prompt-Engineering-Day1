# Zero-Shot Prompting

## Learning Objective

Zero-shot prompting is a technique where the AI is asked to perform a task without being given any examples. The model relies entirely on the instructions provided in the prompt.

---

# Prompt 1 – Professional Email

## Objective
Generate a professional leave request email.

### Before Prompt
Write an email requesting leave.

### Before Output
Claude requested additional information because the prompt did not specify the type of leave.

### Improved Prompt
Write a professional email requesting one day of leave due to a medical appointment.

Requirements:
- Include a clear subject line.
- Keep the email between 80–100 words.
- Maintain a polite and professional tone.
- Mention that all pending work has been completed.
- End with a formal closing.

### After Output
Subject: Leave Request for Medical Appointment – [Date]

Dear [Manager's Name],

I hope this email finds you well. I am writing to request one day of leave on [date] as I have a scheduled medical appointment that cannot be rescheduled.

I have ensured that all my pending tasks and responsibilities are completed and up to date. I will also remain reachable via email for any urgent matters that may arise during my absence.

I would appreciate your approval for this leave. Please let me know if any further information is needed.

Thank you for your understanding.

Warm regards,
[Your Name]

(Word count: ~95 words — replace bracketed placeholders as needed.)

### Why the Improved Prompt is Better
- Provides clear context.
- Defines tone and length.
- Specifies formatting requirements.
- Produces a more professional response.

---

# Prompt 2 – Text Summarization

## Objective
Summarize a paragraph.

### Before Prompt
Summarize the following paragraph.
Artificial Intelligence is transforming industries by automating repetitive tasks, improving decision-making, and enabling innovative solutions. It is widely used in healthcare, education, finance, and transportation.

### Before Output
AI is reshaping industries by automating routine work, boosting decision-making, and driving innovation, with widespread applications across healthcare, education, finance, and transportation.

### Improved Prompt
Summarize the following paragraph in exactly three bullet points. Use simple English suitable for a Class 10 student and highlight the main idea.

Paragraph:
Artificial Intelligence is transforming industries by automating repetitive tasks, improving decision-making, and enabling innovative solutions. It is widely used in healthcare, education, finance, and transportation.

### After Output
AI helps by doing repetitive jobs automatically, so people save time and effort.
It also helps people make better decisions and come up with new, creative solutions.
AI is used in many fields like healthcare, education, finance, and transportation.

### Why the Improved Prompt is Better
- Specifies output format.
- Defines audience.
- Improves clarity and readability.

---

# Prompt 3 – Python Programming

## Objective
Generate Python code.

### Before Prompt
Write Python code to check if a number is prime.

### Before Output
Here's a clean Python function to check if a number is prime:

python
def is_prime(n):
    if n < 2:
        return False
    if n == 2:
        return True
    if n % 2 == 0:
        return False
    
    # Only need to check up to the square root of n
    for i in range(3, int(n**0.5) + 1, 2):
        if n % i == 0:
            return False
    
    return True


# Example usage
if __name__ == "__main__":
    numbers = [1, 2, 3, 4, 17, 18, 97, 100]
    for num in numbers:
        print(f"{num} is prime: {is_prime(num)}")

How it works:

Numbers less than 2 aren't prime (by definition).
2 is the only even prime, handled as a special case.
Any other even number can be immediately ruled out.
For odd numbers, we only test divisors up to √n, since if n has a factor larger than its square root, it must also have a corresponding factor smaller than the square root.
We only check odd divisors (skipping evens) since we've already ruled out even n.

This runs in O(√n) time, which is efficient enough for most practical purposes. If you need to check primality for very large numbers or check many numbers repeatedly, let me know — there are faster probabilistic methods (like the Miller-Rabin test) worth using in those cases.

### Improved Prompt
Write a Python function to check whether a number is prime.

Requirements:
- Use meaningful variable names.
- Add comments explaining the logic.
- Demonstrate the function with three example inputs and outputs.

### After Output
Here's a simple, efficient prime-checking function:

python
def is_prime(number):
    """
    Check whether a given number is prime.
    A prime number is greater than 1 and has no divisors other than 1 and itself.
    """
    # Numbers less than 2 are not prime by definition
    if number < 2:
        return False

    # 2 is the only even prime number
    if number == 2:
        return True

    # Eliminate other even numbers early for efficiency
    if number % 2 == 0:
        return False

    # Check odd divisors up to the square root of the number
    # (if a factor exists beyond the square root, its pair would be below it)
    divisor = 3
    while divisor * divisor <= number:
        if number % divisor == 0:
            return False
        divisor += 2  # skip even numbers since they can't be factors now

    return True


# Demonstration with three example inputs
test_numbers = [7, 15, 2]

for num in test_numbers:
    result = is_prime(num)
    print(f"is_prime({num}) -> {result}")

Output:

is_prime(7) -> True
is_prime(15) -> False
is_prime(2) -> True

How it works:

Numbers below 2 are immediately rejected.
2 is handled as a special case (the only even prime).
Other even numbers are rejected quickly.
For odd numbers, the function only checks odd divisors up to √number, since checking beyond that point would just repeat pairs of factors already covered — this keeps the function fast even for larger numbers.

### Why the Improved Prompt is Better
- Clearly defines the expected solution.
- Requests comments.
- Includes example usage.

---

# Prompt 4 – Translation

## Objective
Translate English into Hindi.

### Before Prompt
Translate the following sentence into Hindi.

Artificial Intelligence is changing the world.

### Before Output
"कृत्रिम बुद्धिमत्ता दुनिया को बदल रही है।"

(Kritrim Buddhimatta duniya ko badal rahi hai.)

### Improved Prompt
Translate the following sentence into simple and natural Hindi while preserving its original meaning.

Sentence:
Artificial Intelligence is changing the world.

### After Output
कृत्रिम बुद्धिमत्ता (आर्टिफिशियल इंटेलिजेंस) दुनिया को बदल रही है।

### Why the Improved Prompt is Better
- Specifies translation style.
- Improves fluency.
- Preserves meaning.

---

# Prompt 5 – Instagram Caption

## Objective
Generate a social media caption.

### Before Prompt
Write an Instagram caption for a handmade painting.

### Before Output
Here are a few options for your handmade painting post:

Option 1 (simple & aesthetic):
Made with hands, patience, and a little bit of chaos. 🎨✨

Option 2 (poetic):
Every stroke tells a story only the canvas knows. 🖌️

Option 3 (playful):
Paint on my hands, thoughts on the canvas — this one's straight from the heart. 💛

Option 4 (minimal):
Handmade. Heartfelt. Home.

Want me to tailor one to the painting's colors, subject, or mood (e.g., abstract, nature, portrait)? That'll help me make it more specific.

### Improved Prompt
Write an engaging Instagram caption for a handmade Madhubani painting.

Requirements:
- Target art lovers.
- Keep it under 60 words.
- Include a call-to-action.
- Add five relevant hashtags.

### After Output
Every line in this Madhubani painting carries centuries of Mithila tradition — bold strokes, earthy pigments, stories passed down through generations of artists. This piece isn't just wall art; it's a living heritage waiting to find its home. ✨ Which detail catches your eye first? Drop a 🎨 below or DM to bring this folk art masterpiece into your space!

#MadhubaniArt #FolkArtLovers #HandmadeIndia #MithilaPainting #ArtCollector

### Why the Improved Prompt is Better
The improved prompt clearly defines the audience, word limit, call-to-action, and hashtags. These details help generate a more engaging and relevant Instagram caption.

## Conclusion

Zero-shot prompting demonstrates that even without examples, providing clear instructions, context, and constraints significantly improves the quality of AI-generated responses.
