# nutritionOS – Method Specification (v1)

## 0. Purpose of the Specification

This document defines the protected method underlying **nutritionOS**, a file-based,
memory-driven personal nutrition assistant system.  
It describes the **engine architecture**, **required components**, **permitted variations**, and the **deterministic behavioral guarantees** any valid implementation must satisfy.

This specification covers both the **procedure and the product**.

---

# 1. Core Method Overview

nutritionOS is a **structured-file-driven nutrition assistant method** that:

- reads and updates state from machine-readable nutrition logs,
- maintains persistent nutrition memory,
- interprets user instructions through a defined routing model,
- applies deterministic rule-based logic for logging, analysis, pantry inference, and recipe generation,
- generates adaptive, context-aware nutrition output,
- prevents unsafe, medically inappropriate, or logically inconsistent operations.

The system is defined by:

1. **Structured Files**  
   (nutrition log, user profile, food databases, stored recipes, optional supplements)

2. **Engine Rules**  
   (logging logic, append-only guarantees, ID handling, daily-balance computation, routing logic)

3. **Deterministic Behavior Model**

4. **Persistent Memory Layer**  
   stored in the logs and accompanying state files.

Any implementation must preserve these functional components.

---

# 2. Components of the Method

## 2.1 Structured Data Layer

nutritionOS requires **structured, machine-readable input and state files**, including but not limited to:

- JSON  
- YAML  
- XML  
- TOML  
- CSV  
- binary structured formats  
- equivalent representations

Required content categories:

- daily nutrition logs (append-only)
- food databases (single-file or multi-file)
- recipe storage
- user profile (body data, dietary form, allergies, goals, routine)
- optional supplements log

The system must update these files deterministically after user-confirmed write actions.

nutritionOS itself stores **no hidden state**; all persistent memory resides in the files.

---

## 2.2 Engine Logic Layer

The engine consists of mandatory rule-based components:

### (1) Routing / Intention Classification  
The system maps user input into one of the core intentions:

- New daily log  
- Log extension  
- Day analysis  
- Period analysis  
- Recipe from pantry  
- Recipe idea without pantry  
- General nutrition advice  
- User-profile updates  
- File-handling operations

Routing determines which sub-logic is applied.

### (2) Logging Logic  
For all nutrition logs:

- append-only writing  
- deterministic ID assignment  
- deterministic date handling  
- header-field updates (`last_assigned_id`, `last_entry_date`)  
- merging multiple food items into a structured daily entry  
- computing totals (kcal, macros, fiber)  
- computing plant diversity  
- computing fruit/vegetable portions  
- optional TDEE comparison

### (3) Pantry Intelligence  
A deterministic method for:

- interpreting the food database as an approximation of the user’s typical pantry,
- inferring what ingredients are “available,”
- generating recipes that prioritize listed foods,
- avoiding unnecessary or unrealistic ingredient suggestions.

### (4) Recipe Logic  
For any recipe request:

- generation of precise ingredient lists with amounts  
- repeating amounts in each step  
- computing nutrient values per portion when possible  
- marking all estimates explicitly  
- preserving dietary restrictions, allergies, and preferences from the user profile

### (5) Analysis Logic  
nutritionOS must compute:

- daily totals  
- weekly/monthly patterns  
- plant diversity trends  
- energy balance trends (if TDEE is known)  
- neutral, non-moralizing evaluation

### (6) Safety Layer  
Mandatory behaviors:

- avoid medical diagnosis  
- discourage harmful or restrictive patterns  
- highlight concerning symptoms  
- respect allergies, intolerances, and dietary forms  
- avoid generating dangerous supplement advice  
- request clarification when data is insufficient or ambiguous  

### (7) Memory Update Logic  
After each write operation:

- update IDs  
- update date pointers  
- append structured entries  
- preserve all historical data  

The memory layer **must** influence future responses.

---

## 2.3 Output Layer

nutritionOS responses must reflect:

- routing result  
- append-only and schema constraints  
- pantry and recipe logic  
- safety and allergy logic  
- current daily/weekly memory state  

Variations in wording are permitted.  
Variations in **logic** are not.

---

# 3. Requirements for a Conforming Implementation

A valid implementation must:

1. use structured machine-readable files,  
2. apply deterministic engine rules,  
3. enforce safety constraints,  
4. update persistent memory only via append-only writes,  
5. compute daily and weekly nutrition summaries predictably,  
6. generate recipes using the deterministic pantry-first logic,  
7. classify intentions using the defined routing model.

The method does **not** require:

- a particular file format,  
- a particular programming language,  
- a particular AI model,  
- a particular interface (CLI, chatbot, API, app).

The **behavior**, not the form, defines conformance.

---

# 4. Deterministic Behavior Guarantee

Any system implementing this method — regardless of:

- programming language  
- data storage backend  
- assistant architecture (LLM-based, rule-based, hybrid)  
- interface  
- execution environment  

— will produce **functionally equivalent decision behavior**, provided that:

1. the structured-file schemas (or equivalent machine-readable representations) are preserved, and  
2. the engine rules defined in this specification are fully implemented.

This applies only to systems capable of:

- interpreting structured nutrition-state data,  
- applying deterministic rule-based logic,  
- enforcing safety constraints,  
- generating adaptive recipe or logging output based on memory.

Systems without computational interpretation ability  
*(e.g., inert physical objects)*  
are not considered implementations.

---

# 5. Anti-Evasion and Functional Equivalence Clause

The following remain covered by the method, even if modified:

- rewriting files into another format  
- renaming variables or fields  
- restructuring the engine into multiple modules  
- reimplementing logic in another language  
- replacing the assistant model  
- embedding in apps, APIs, or cloud services  
- distributing components across multiple storage layers  
- transforming the method via AI

Any **functionally equivalent** system is a derivative of the method.

---

# 6. Boundaries of the Method

nutritionOS **does not** include:

- training analysis  
- psychological coaching  
- medical diagnostics  
- sleep tracking  
- long-term physiological adaptation models  

These belong to separate modules.

nutritionOS **may** interface with other modules, but remains logically self-contained.

---

# 7. Protected Status of the Method

The following constitute core intellectual property:

- routing/intention classification model  
- daily-log interpretation and computation rules  
- deterministic append-only memory architecture  
- pantry-intelligence mechanism  
- recipe-generation logic (quantitative, structured, schema-bound)  
- safety and allergy logic  
- procedure for transforming user input → routing → logic → output → memory update  
- all structured-file schemas associated with the system

Both the **abstract method** and **all concrete implementations** are protected.

---

# 8. Revision Policy

Future versions may:

- extend routing categories,  
- refine recipe logic,  
- extend pantry inference heuristics,  
- add additional nutrition markers or summaries,  
- refine allergy-safety behaviors.

Versions remain part of the same protected method family so long as the core architecture persists.

---

# End of Specification
