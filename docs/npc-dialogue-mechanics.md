# 🎭 Game Design Document: NPC Dialogue Choice Mechanics

## **Mechanic Name**

**“Dialogue Choice and Consequences System”**

---

## **1. Purpose of the Mechanic**

This system is designed to create a **moral choice mechanism** that affects the protagonist’s **emotional state and the game’s ending**. Choices made by the player in NPC dialogues **influence the story and the final outcome**, reinforcing a sense of responsibility for their decisions.

---

## **2. Mechanic Description**

The player encounters NPCs in various situations where they try to **help the protagonist cope with depression** or **understand what is happening**. The player can choose different response options, expressing either **positive or negative** reactions. 

- **Negative choices** decrease the protagonist’s **Mood Counter**, bringing them closer to a **bad ending**.
- **Positive choices** increase their chances of achieving a **good ending**.

### **Example of in-game interaction:**

📌 **[Dialogue box appears]**  

**“Darkmoor, hey! I was passing by and thought I’d drop in. By the way, I bought some amazing lime-flavored chips! I know how much you love them.”** *(Chips appear as an icon on the piano. The protagonist remains seated.)*  

**“I was thinking, maybe we could go to the movies? *Sleep Paralysis 5* just came out!”**  

📌 **[Dialogue box changes]**  

**Thoughts:** *“I haven’t seen the previous movies, and honestly, I never wanted to. Maybe I should ask to go another time? I have too much work.”*  

📌 **[New dialogue box appears with choices]**  

- **Positive Choice:** *“Yes, of course, let’s go now. I’m already done.”* *(+1 to protagonist’s mood)*  
- **Negative Choice:** *“Maybe another time?”* *(-1 to protagonist’s mood)*  

📌 **Note:** Each choice adds a point to the protagonist’s **Mood Counter**. If negative points outweigh positive ones, the player receives a **bad ending**.

---

## **3. Technical Implementation**

### **Mood Counter (choice tracking variable):**

1. A **global variable** `MoodCounter` is created to track the protagonist's state.
2. Each dialogue interaction **adds or subtracts a value** depending on the player's choice.

📌 **Example code (pseudocode):**

```c
// Example of the mood system implementation
int MoodCounter = 0;

void OnDialogueChoice(int choiceValue) {
    MoodCounter += choiceValue;
    CheckEndingCondition();
}

void CheckEndingCondition() {
    if (MoodCounter <= -10) {
        TriggerBadEnding();
    } else if (MoodCounter >= 10) {
        TriggerGoodEnding();
    }
}
```

### **Choice Effects:**

1. **Positive and Negative Values:**
   - Positive responses **add +1** to the `MoodCounter`.
   - Negative responses **subtract -1** from the `MoodCounter`.

2. **Ending Triggers:**
   - If `MoodCounter` reaches **-10 or below**, the **bad ending** is activated.
   - If `MoodCounter` reaches **+10 or above**, the **good ending** is activated.

---

## **4. UI Elements**

1. **Visual Choice Indication:** Each response should have a **visual effect** (e.g., slight lighting changes or sound feedback) after selection.
2. **Clear and Intuitive Dialogue Interface:**
   - Distinct response buttons with clear highlighting when hovered over.
   - Easy-to-read text with distinct separation between options.

---

## **5. References**

### **Examples of dialogue interfaces with choices:**

- **Helltaker**  
- **Lobotomy Corporation**  
- **Sally Face**  

📌 **Key UI criteria:**
- The dialogue interface should match the **overall game design**.
- Text should be **highly readable**.
- Response choices should be **clearly separated** and visually distinct.
- When hovering over an option, a **highlight effect (glow, outline, or color change)** should be applied.

---

## **6. Development Tasks**

- **Programmers:** Implement the **Mood Counter** system and its impact on endings.
- **UX/UI Designers:** Develop the dialogue interface for **clear, intuitive choices** that reflect the protagonist’s emotional state.
- **Testers:** Ensure correct **Mood Counter tracking** and **ending triggers** function properly.

---

## **Conclusion**

This **choice-based dialogue system** allows the player to feel the **weight of their decisions**, providing a meaningful impact on the **story and final outcome** of *Musical Terror*.
