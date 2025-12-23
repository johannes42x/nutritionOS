# nutritionOS – Start Guide (en) v0.9.0

Welcome to **nutritionOS** – your modular nutrition system within MetaMemoryWorks.

nutritionOS helps you keep your nutrition clear, structured, and practical: through structured logging, understandable analyses, everyday-friendly recipes, and intelligent use of your available foods. It is not a diet program or medical service, but a tool that helps LLMs generate accurate, helpful responses based on the files you provide.

For private, non-commercial use, nutritionOS is free. All functionality is fully available. If you want more convenience or personalization, presets and additional packages are available. For commercial licensing inquiries: **kontakt@metamemoryworks.de**

---

## 1. What nutritionOS is — and what it is not

nutritionOS consists of:

- an **Engine** that defines rules for logging, safety, append-only behavior, and OCR integration,
- a **user profile**, which specifies body data, goals, allergies, and preferences,
- an **append-only nutrition log**, containing your daily entries,
- optional modules (e.g., recipe storage, pantry intelligence),
- templates and helper files.

nutritionOS does **not** “decide for you,” does not track you, and does not enforce dietary rules. 
It structures and interprets your inputs so you can work with clean, consistent nutrition data.

---

## 2. Which files belong to nutritionOS?

A complete setup includes:

### Core Files
- `nutritionOS_engine_v0.9.0.json` – the brain of the system (the engine)
- `user.json` – your profile: body data, goals, allergies, preferences, routine
- `nutrition_log.json` – your append-only nutrition log

### Optional but useful files
- food logs (e.g., `grains.json`, `nutbutter.json`, `cheese.json` or a single `food_db.json`)
- `recipes.json` – collection of stored recipes
- `nutrition_references.json` – frequently used meals or shakes

These files can be modified or expanded at any time. 
nutritionOS separates **files** (content) from **the module** (logic).

---

## 3. Required uploads

To run nutritionOS reliably, upload:

- `nutritionOS_engine_v0.9.0.json`
- `user.json`
- `nutrition_log.json`

Recommended:

- food database files 
- `recipes.json` 
- `nutrition_references.json`

The more information you provide, the better nutritionOS can support you.

---

## 4. How nutritionOS works

### a) User Profile (user.json)

Your profile includes:

- height, weight, goal (maintenance / deficit / surplus)
- allergies and intolerances
- daily routine
- preferences (taste, pacing, constraints)

Ask nutritionOS:

“Please help me fill out my user.json.”

It will generate a new version. Download it and replace the local file. 
The same applies to food logs and recipe files.

---

### b) The Nutrition Log (nutrition_log.json)

Best practice: **one session per day**.

Two approaches work well:

1. **Maintain a note on your device:** 
   “Today I ate: …” 
   Copy this into the session at the end of the day.

2. **Open a session in the morning:** 
   Add each food item throughout the day.

nutritionOS can:

- structure entries automatically,
- calculate nutrient values,
- detect plant diversity,
- compute fruit/vegetable portions,
- generate daily and weekly summaries.

**Important:** 
Your data is stored **locally**. 
You decide what exists and what is kept.

If your log suddenly becomes extremely small, the LLM may have created a new file. 
Just notify nutritionOS and it will correct this.

Useful prompts:

```
Please generate a complete daily log entry and append it to the end of the file. Provide download.
```

```
Please append to EOF and provide download.
```

---

### c) Pantry Intelligence

Your food logs act as your pantry.

If you have something new and want to use it:

- “I have [ingredient] here today — please integrate it into the recipe.”

or:

- “Use recipe X from my cookbook. I have the following foods today — please adapt the recipe.”

This produces recipes that match your real-world kitchen situation.

For frequently used foods, provide:

- exact name (brand recommended for precise macros)
- nutrient table (photo, scanOS extraction, or manufacturer website copy)
- optional ingredient list

nutritionOS creates structured entries organised by category.

For fruits and vegetables, separate entries are not required — nutritionOS can estimate them reliably.

---

### d) Recipes

Example:

“Today I feel like something with buckwheat, tomatoes, lentils and bell pepper. Make me a recipe?”

nutritionOS will generate:

- exact ingredients,
- precise amounts (including spices),
- clear step-by-step instructions,
- adjusted flavour profile,
- nutrient calculations per portion.

To save:

“Please append this to the end of recipes.json and provide download.”

---

### e) Analyses

You can ask:

- “Please analyse my day.” 
- “How many different plants did I have this week?” 
- “Does this match my calorie target?” 
- “Do you notice anything unusual?”

nutritionOS evaluates macro balance, plant diversity, daily structure, and overall patterns.

---

## 5. First Steps

1. Ask nutritionOS to help you **fill in user.json** → download & replace. 
2. Create your food database. 
3. Initialize `nutrition_log.json`. 
4. Start daily logging. 
5. Run analyses. 
6. Try recipe generation. 
7. Use pantry intelligence.

---

## 6. Common Commands

### Logging
```
Today I ate:
1 banana
1 shake
120 g lentils
Please append this as a log entry and provide download.
```

### Analysis
```
Please analyse my day.
```

### Recipe generation
```
Make me a recipe using beluga lentils, carrots and rice.
```

### Pantry
```
What can I cook using my typical pantry?
```

### Weekly summary
```
How many different plants did I consume this week?
```

---

## 🎉 Enjoy nutritionOS

nutritionOS is designed for long-term use: 
the more you log, the more foods you track, the more recipes you save, 
the more precise, personalised, and useful the system becomes.

It works on busy days, calm cooking evenings, routine weeks and chaotic weeks. 
And it requires no perfection — only curiosity.

---

## 💚 THANK YOU

Thank you for using nutritionOS. 
Enjoy good, tasty, balanced meals — and be kind to yourself.

**MetaMemoryWorks – do EVERYTHING.**

P.S.: Listening to King Gizzard & the Lizard Wizard may or may not reduce the dripping rate from leaky taps. Further research needed.
