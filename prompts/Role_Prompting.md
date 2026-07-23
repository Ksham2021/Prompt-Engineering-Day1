# Role Prompting

## Learning Objective

Role Prompting is a technique where the AI is assigned a specific role or persona before answering. This helps generate responses that are more relevant, accurate, and suited to the context.

---

# Prompt 1 – Teacher

## Objective
Explain a technical concept.

### Before Prompt
Explain recursion.

### Before Output
Recursion is when a function solves a problem by calling itself on a smaller version of the same problem, until it reaches a case simple enough to answer directly.

The two essential parts

Base case — the simplest version of the problem, answered directly without further recursion. This is what stops the function from calling itself forever.
Recursive case — the function calls itself with a smaller or simpler input, moving it closer to the base case.

A classic example: factorial

5! = 5 × 4 × 3 × 2 × 1

Notice that 5! = 5 × 4!, and 4! = 4 × 3!, and so on. So:

python
def factorial(n):
    if n == 0:          # base case
        return 1
    return n * factorial(n - 1)   # recursive case

Tracing factorial(3):

factorial(3) = 3 * factorial(2)
             = 3 * (2 * factorial(1))
             = 3 * (2 * (1 * factorial(0)))
             = 3 * (2 * (1 * 1))
             = 6

Each call waits on the one below it, and once factorial(0) hits the base case, the answers unwind back up the chain.

Why it's useful

Recursion shines for problems that are naturally self-similar or nested:

Tree and graph traversal (folders inside folders, nodes with children)
Divide-and-conquer algorithms (merge sort, quicksort, binary search)
Mathematical sequences (Fibonacci, factorials)
Parsing nested structures (JSON, expressions with parentheses)

A mental model

Think of Russian nesting dolls. To find out how many dolls there are, you don't need to know the whole count upfront — you just open one doll and ask "how many are inside this one?" That question is identical in form to the original, just smaller. Eventually you hit the smallest doll (base case), which has nothing inside — and you count back up as you close each doll.

A common pitfall

If there's no base case, or the recursive case doesn't actually move toward it, the function calls itself indefinitely — until it hits a stack overflow (each call takes up memory, and that memory isn't freed until the call returns).

One more example: Fibonacci

python
def fib(n):
    if n <= 1:              # base case
        return n
    return fib(n-1) + fib(n-2)   # recursive case

This one is elegant but inefficient as written — it recomputes the same values many times. That's a good segue into a related idea called memoization, where you cache results to avoid redundant work. Want me to go into that, or into how recursion compares to iteration (loops)?

### Improved Prompt
You are an experienced Computer Science teacher.

Explain recursion to a first-year B.Tech student using simple language, a real-life analogy, and one Python example.

### After Output
Recursion — Explained Simply

Recursion is when a function solves a problem by calling itself with a smaller version of the same problem, until it reaches a case simple enough to answer directly (called the base case).

Every recursive function needs two things:

Base case — the stopping condition (so it doesn't run forever)
Recursive case — where the function calls itself with a smaller/simpler input, moving closer to the base case
Real-Life Analogy: Russian Nesting Dolls (Matryoshka)

Imagine you want to find the smallest doll inside a set of nesting dolls.

You open the biggest doll → find a smaller doll inside → open that one too → and so on.
You keep repeating the same action (open the doll) on a smaller version of the problem (a smaller doll) each time.
You stop when you reach the smallest doll that doesn't open — that's your base case.
Once you find it, you're done — no more opening needed.

Another familiar one: standing between two mirrors facing each other — you see your reflection, inside a reflection, inside a reflection... it keeps repeating the same pattern on a smaller scale, until it becomes too small to see (the "base case" of human vision).

Python Example: Factorial

The factorial of n (written n!) is defined as:

n! = n × (n-1) × (n-2) × ... × 1
Base case: 0! = 1
Recursive case: n! = n × (n-1)!
python
def factorial(n):
    # Base case: stop recursion here
    if n == 0:
        return 1
    # Recursive case: function calls itself with a smaller problem
    else:
        return n * factorial(n - 1)

print(factorial(5))  # Output: 120
How it unfolds (trace):
factorial(5)
= 5 * factorial(4)
= 5 * (4 * factorial(3))
= 5 * (4 * (3 * factorial(2)))
= 5 * (4 * (3 * (2 * factorial(1))))
= 5 * (4 * (3 * (2 * (1 * factorial(0)))))
= 5 * (4 * (3 * (2 * (1 * 1))))
= 120

Notice the pattern: the function keeps calling a smaller version of itself (n-1, n-2, ...) until it hits factorial(0) — the base case — and then all the pending multiplications "unwind" back up to give the final answer.

Key Takeaway

Think of recursion as: "To solve this problem, solve a smaller version of the same problem, and trust that it works — until the problem is small enough to solve directly." This trust is often called the "recursive leap of faith."

A quick word of caution: always make sure your base case is reachable — otherwise you get infinite recursion, which crashes your program with a RecursionError in Python!

### Why the Improved Prompt is Better
- Defines the AI's role.
- Adapts the explanation to the student's level.
- Includes an example for better understanding.

---

# Prompt 2 – Career Coach

## Objective
Improve a resume.

### Before Prompt
Review my resume.

### Before Output
I don't see a resume attached yet — could you upload the file (PDF, Word doc, or similar), or paste the text here? Once I have it, I'll give you a thorough review covering content, structure, and formatting.
### Improved Prompt
You are a professional career coach with experience helping software engineering students.

Review my resume and suggest improvements in:
- Skills
- Projects
- Formatting
- ATS compatibility

Provide actionable recommendations.

### After Output
I don't see a resume attached to this conversation — could you upload your resume file (PDF, DOCX, or even plain text) so I can review it? Once I have it, I'll go through it as a career coach would and give you specific, actionable feedback on:

Skills – what's missing, outdated, or poorly presented for ATS/recruiter scanning
Projects – how to frame them with impact (metrics, tech stack clarity, outcomes)
Formatting – layout, consistency, readability
ATS compatibility – keyword matching, parsing issues, file structure problems

A couple of things that'll help me tailor the feedback:

Are you targeting a specific type of role (e.g., backend, full-stack, ML/AI, SDE internship vs. full-time)?
Do you have a specific job posting or company in mind, or is this a general-purpose resume?

Go ahead and upload the file whenever you're ready.

### Why the Improved Prompt is Better
- Assigns an expert role.
- Clearly specifies the review criteria.
- Produces structured feedback.

---

# Prompt 3 – Software Engineer

## Objective
Improve Python code.

### Before Prompt
Improve this Python code.

### Before Output
I don't see any code attached to your message — could you paste the Python code you'd like me to improve, or upload the file?
### Improved Prompt
You are a Senior Python Software Engineer.

Review the following code and:
- Improve readability.
- Optimize performance.
- Follow Python best practices.
- Explain each improvement.

### After Output
It looks like the code snippet itself didn't come through in your message — could you paste the code you'd like reviewed? Once I have it, I'll go through it and cover:

Readability (naming, structure, clarity)
Performance (algorithmic complexity, unnecessary work, better data structures/idioms)
Best practices (PEP 8, idiomatic Python, error handling, type hints where useful)
Explanations for each change, with a before/after comparison

Feel free to paste it directly in the chat, or upload the file if it's long.

### Why the Improved Prompt is Better
- Uses domain expertise.
- Requests optimization and explanation.
- Produces higher-quality code review.

---

# Prompt 4 – Marketing Expert

## Objective
Write an Instagram caption.

### Before Prompt
Write a caption for handmade paintings.

### Before Output
Write an Instagram caption.

Happy to help! What's the post about — a photo, an achievement, a trip, something else? Give me a quick sense of the vibe (fun, reflective, professional) and I'll draft a caption for it.

### Improved Prompt
You are a social media marketing expert.

Write an Instagram caption for a handmade Madhubani painting brand.

Requirements:
- Target young art lovers.
- Use an emotional tone.
- Include a call-to-action.
- Add five relevant hashtags.

### After Output
Here's an Instagram caption for a handmade Madhubani painting brand:

Every stroke carries centuries of stories 🎨✨

Long before Instagram, women in the villages of Mithila were painting their truths on mud walls — their joys, their prayers, their myths. Today, that same soul lives on canvas, waiting in your hands.

This isn't just art. It's a piece of Bihar's heart, painted by hands that learned this craft from their mothers, and theirs before them.

When you bring home a Madhubani piece, you're not just decorating a wall — you're keeping a 2500-year-old tradition breathing for one more generation. 💛

Which story will you carry home? 🖼️
Tap the link in bio to explore our latest collection, or DM us "ART" to get styling tips for your space.

#MadhubaniArt #HandmadeWithLove #TraditionalIndianArt #SupportLocalArtisans #ArtThatSpeaks

Want me to create a few variations — maybe one shorter/punchier for Reels captions, or one more festival/gifting-focused for a seasonal push?

### Why the Improved Prompt is Better
- Assigns a marketing role.
- Defines audience and tone.
- Generates engaging content.

---

# Prompt 5 – Travel Planner

## Objective
Plan a trip.

### Before Prompt
Plan a trip to Jaipur.

### Before Output
I'd love to help you put together a solid Jaipur itinerary! A couple of quick things will help me tailor it well.

### Improved Prompt
You are an experienced travel planner.

Create a 3-day itinerary for Jaipur for a college student.

Requirements:
- Budget-friendly.
- Include major tourist attractions.
- Recommend local food.
- Suggest transportation options.
- Provide an estimated budget.

### After Output
3-Day Budget Jaipur Itinerary (College Student Edition)
Day 1: Old City & History

Morning

Amer Fort (opens 8 AM) – go early to beat crowds and heat. Entry ~₹50 (Indian students, with ID) / ₹100 (general Indian). Skip the elephant ride; it's pricey and not great for the animals.
Jal Mahal – quick 15-min photo stop nearby, no entry fee (viewed from outside).

Afternoon

City Palace – ₹75 (student concession available with ID). Budget 1.5–2 hours.
Jantar Mantar – ₹50 (student rate), right next to City Palace, worth 30-40 mins.

Evening

Hawa Mahal – see it lit up from the street-side cafes opposite (like Wind View Café) over chai instead of paying entry — great photo spot, costs almost nothing.
Walk around Johari Bazaar / Bapu Bazaar for shopping (bargain hard).

Food

Breakfast: Pyaaz Kachori at Rawat Mishthan Bhandar (~₹40)
Lunch: Laxmi Misthan Bhandar (LMB) thali (~₹250) or cheaper local dhaba near City Palace (~₹100-150)
Evening snack: Lassi at Lassiwala (~₹40-60)
Dinner: Street food at Masala Chowk (curated food court, ₹150-200 for a full meal)
Day 2: Forts & Views

Morning

Nahargarh Fort – ₹50 (student rate). Great city views; go by early morning or save for sunset instead (your call).
Jaigarh Fort – ₹35-40, combined ticket often available with Nahargarh. Home to the world's largest cannon on wheels.

Afternoon

Albert Hall Museum – ₹40 (student), nice architecture and artifacts, 1 hour is enough.
Relax at Central Park nearby if you want a break.

Evening

Chokhi Dhani (optional splurge) – Rajasthani village-theme experience with dinner, folk dance, camel rides. Entry + dinner ~₹700-900. Skip if tight on budget; do a bazaar walk instead.
Alternative budget evening: Nahargarh at sunset (if not done in morning) — free-feeling views over the Pink City.

Food

Breakfast: Bedmi Poori + Sabzi from a street stall (~₹40)
Lunch: Rawat Mishthan Bhandar or a simple thali at a local dhaba (~₹120-150)
Dinner: Chokhi Dhani (if doing it) or street food at Chandpole Bazaar area (~₹100-150)
Day 3: Local Culture & Leisure

Morning

Patrika Gate – stunning, colorful, and free! Great for photos.
Birla Mandir (Laxmi Narayan Temple) – free entry, peaceful white marble temple.

Afternoon

Bapu Bazaar / Tripolia Bazaar – buy Jaipuri jutis, block-print textiles, and lac bangles (bargain, bargain, bargain).
Try a puppet show or local craft workshop if there's a cultural center nearby (often free or nominal fee).

Evening

Chill at a rooftop café with Old City views — Anokhi Café or Tapri Central (~₹150-250 for snacks/drinks).
Wrap up with last-minute shopping or a walk around Jal Mahal at sunset.

Food

Breakfast: Mirchi Bada + tea (~₹30)
Lunch: Local dhaba thali (~₹100-120)
Dinner: Rooftop café or street food (~₹150-200)
Transportation
Mode	Best For	Approx Cost
Jaipur Metro	City Palace/Chandpole area to certain points	₹10-25/ride
App-based auto (Ola/Uber Auto)	Point-to-point, most convenient	₹50-150/trip
Shared autos/tempo	Cheapest, common routes	₹10-20/ride
Rented scooty (if you have a license)	Full-day flexibility, best value if with friends	₹300-500/day + fuel
Cycle rickshaw	Short distances in Old City	₹30-50

Tip: If splitting a scooty rental among 2-3 friends, it's often the cheapest and most flexible way to hit multiple forts in one day.

Estimated 3-Day Budget (Per Person)
Category	Cost (₹)
Accommodation (budget hostel/guesthouse, 2 nights)	1,200 - 1,800
Entry fees (forts, palaces, museum)	500 - 600
Food (all meals, 3 days)	1,200 - 1,500
Local transport	600 - 900
Shopping/souvenirs (optional)	500 - 1,000
Total	₹4,000 - 5,800

(Doesn't include travel to/from Jaipur — add that separately depending on your starting point.)

Quick tips:

Always carry your student ID — many monuments offer discounted "Indian student" rates.
Buy a composite ticket for Amer Fort + Nahargarh + Jaigarh + City Palace + Hawa Mahal + Albert Hall (~₹300 for Indians) — saves money if you're hitting most of these.
Start sightseeing early (7-8 AM) to avoid Jaipur's heat, especially outside winter months.
Stay near MI Road or Bani Park for good hostel options and easy access to Old City.

Want me to turn this into a downloadable one-page PDF/itinerary card you can carry on your phone?

### Why the Improved Prompt is Better
- Defines the planner's role.
- Includes user constraints.
- Produces a practical itinerary.

---

## Conclusion

Role Prompting improves AI responses by assigning a specific role, allowing the model to provide more focused, context-aware, and expert-level answers.
