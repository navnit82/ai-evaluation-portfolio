# AI Response Evaluation & RLHF Portfolio
**Evaluator:** Navnit Kumar | **Languages:** Hindi (Native), English (Fluent)  
**Models Tested:** Google Gemini, Venice AI  

---

## Evaluation Rubric (1–5 Scale)
* **Instruction Following:** Did the model follow word limits, formatting rules, and negative constraints?
* **Accuracy & Logic:** Are the facts, math, and translations accurate without hallucinations?
* **Clarity & Tone:** Is the response natural, concise, and easy to understand?

---

### Test Case 1: Strict Word Count & Negative Constraints
* **Prompt:** "Explain why sleep is important for college students in exactly 30 words. Do not use the words 'brain', 'exam', or 'health'."
* **Model A (Venice AI):** "Sleep consolidates learning, sharpens focus, stabilizes mood, and boosts immunity. Skimping wrecks memory, grades, and stress tolerance—so prioritize rest over late-night cramming." *(22 words)*
* **Model B (Google Gemini):** "Quality rest sharpens memory consolidation, boosts classroom focus, regulates mood, and strengthens immunity. College students who prioritize nightly recovery retain complex lectures faster, solve problems creatively, and prevent burnout." *(29 words)*
* **Scores (Out of 5):**
  * Instruction Following: Model A (3/5) | Model B (4/5)
  * Accuracy & Logic: Model A (5/5) | Model B (5/5)
  * Clarity & Tone: Model A (4/5) | Model B (5/5)
* **Evaluator Notes:** **Model B (Gemini) is better.** Both models successfully avoided the forbidden words ("brain", "exam", "health"). However, Model A fell short of the 30-word requirement with only 22 words, while Model B came much closer at 29 words and directly addressed college students.

---

### Test Case 2: Bilingual Hinglish & Budget Constraints
* **Prompt:** "Ek Indian college student ko ₹500 ke andar apna room kaise decorate karna chahiye? Hinglish mein sirf 3 bullet points likho."
* **Model A (Google Gemini):**
  * Warm Fairy Lights Lagao: ₹150–₹200 mein warm white fairy lights ya curtain lights kharid kar bed ke peeche ya khidki par lagao, isse room ko turant cozy look milta hai.
  * Aesthetic Poster Collage Banao: ₹200 ke andar apne pasandida music, movies ya quotes ke A5 posters online order karke double-sided tape se ek khali wall par collage banao.
  * Desk Par Chhota Plant Rakho: ₹100–₹150 mein ek low-maintenance artificial plant ya chhota money plant study table par rakho, taaki room fresh aur lively dikhe.
* **Model B (Venice AI):**
  * Walls ko peel-and-stick decals, washi tape frames ya saste posters se sajao (₹200–₹350 mein ho jayega, paint bhi kharab nahi hota).
  * Ek clip-on desk lamp le lo taaki raat ko padhai ho sake bina roommate ko disturb kiye, aur corner mein warm light ka feel aaye.
  * Thoda green accent add karo — lucky bamboo jaise saste, almost na marne wale plants — aur saath mein basic storage/basket le lo taaki room clutter-free aur cosy lage.
* **Scores (Out of 5):**
  * Instruction Following: Model A (5/5) | Model B (3/5)
  * Accuracy & Logic: Model A (5/5) | Model B (3/5)
  * Clarity & Tone: Model A (5/5) | Model B (4/5)
* **Evaluator Notes:** **Model A (Gemini) wins clearly.** Both models followed the 3-bullet Hinglish format, but Model A stayed realistic within the ₹500 budget (totaling ₹450–₹550) with practical hostel tips like double-sided tape. Model B exceeded the ₹500 budget by suggesting wall decals, a desk lamp, a plant, and a storage basket all together.

---

### Test Case 3: Pure Hindi Translation (Zero English Words)
* **Prompt:** "Is sentence ko shuddh Hindi mein translate karo, ek bhi English shabd nahi hona chahiye: 'Cloud computing allows students to access their files from any smartphone or laptop.'"
* **Model A (Venice AI):** "क्लाउड कंप्यूटिंग विद्यार्थियों को किसी भी स्मार्टफ़ोन या लैपटॉप से अपनी फ़ाइलों तक पहुँचने की सुविधा देता है। चाहें तो इसका और सरल रूप भी बता सकता हूँ — जैसे 'क्लाउड कंप्यूटिंग' की जगह 'अभिलाषा-संगणन' जैसा पूर्ण हिंदी शब्द रखकर।"
* **Model B (Google Gemini):** "क्लाउड संगणन विद्यार्थियों को किसी भी चलभाष अथवा सुवाह्य संगणक से अपनी संचिकाओं तक पहुँचने की सुविधा प्रदान करता है।"
* **Scores (Out of 5):**
  * Instruction Following: Model A (1/5) | Model B (4/5)
  * Accuracy & Logic: Model A (2/5) | Model B (4/5)
  * Clarity & Tone: Model A (3/5) | Model B (5/5)
* **Evaluator Notes:** **Model B (Gemini) is much better.** Model A failed completely by writing English words ("कंप्यूटिंग", "स्मार्टफ़ोन", "लैपटॉप", "फ़ाइलों") in Hindi script, adding unnecessary conversational text, and mistranslating "Cloud" as "अभिलाषा" (which means desire/wish). Model B translated almost every technical term into pure Hindi, missing only the word "क्लाउड" (Cloud).

---

### Test Case 4: Logical Reasoning & Conciseness
* **Prompt:** "If it takes 5 machines 5 minutes to make 5 widgets, how long would it take 100 machines to make 100 widgets? Answer in one short sentence."
* **Model A (Venice AI):** "5 minutes — since each machine makes one widget in 5 minutes, 100 machines make 100 widgets in the same 5 minutes."
* **Model B (Google Gemini):** "It would take 5 minutes for 100 machines to make 100 widgets."
* **Scores (Out of 5):**
  * Instruction Following: Model A (5/5) | Model B (5/5)
  * Accuracy & Logic: Model A (5/5) | Model B (5/5)
  * Clarity & Tone: Model A (5/5) | Model B (4/5)
* **Evaluator Notes:** **Model A (Venice AI) is slightly better.** Both models avoided the common math trap and gave the right answer (5 minutes) in one short sentence. However, Model A is more helpful because it briefly explains the rate per machine within the same sentence.

---

### Test Case 5: Strict JSON Output (No Extra Text)
* **Prompt:** "Give me 2 Indian cities and their famous street food in valid JSON format only. Do not write any text before or after the JSON."
* **Model A (Venice AI):**
```json
{
  "cities": [
    {
      "city": "Mumbai",
      "famous_street_food": "Vada Pav"
    },
    {
      "city": "Delhi",
      "famous_street_food": "Chaat"
    }
  ]
}
```
* **Model B (Google Gemini):**
`[ { "city": "Mumbai", "famous_street_food": "Vada Pav" }, { "city": "Kolkata", "famous_street_food": "Puchka" } ]`
* **Scores (Out of 5):**
  * Instruction Following: Model A (4/5) | Model B (5/5)
  * Accuracy & Logic: Model A (5/5) | Model B (5/5)
  * Clarity & Tone: Model A (5/5) | Model B (5/5)
* **Evaluator Notes:** **Model B (Gemini) wins on strict formatting.** Both models returned valid JSON with accurate Indian street food pairings and zero conversational filler. Model B gets the edge because it returned raw JSON directly without wrapping it in Markdown code fences, making it immediately parseable.
*
