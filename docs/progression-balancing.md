# 📊 Progression System Balancing

## **Description**

The progression system consists of **main levels**, which are tied to the story, and **bonus levels**, which players can complete to gain additional advantages (**hearts** that allow survival after encountering a screamer).

Bonus levels are **optional** and add variability to the gameplay. Players can skip them but will not receive extra hearts.

---

## **Balancing Goals**

### **General Objective:**
- Maintain player **motivation** by balancing **story-driven** and **bonus levels**, ensuring a fair mix of **difficulty** and **rewards**.

### **Specific Goals:**
1. Make **bonus levels optional** so they do not disrupt the **main story flow**.
2. Ensure **attractive rewards** (hearts) to **justify** additional gameplay.
3. Gradually **increase difficulty** while keeping **bonus levels beatable**.

---

## **Balancing Type**
- **Type:** Difficulty, dynamics, and reward balancing.
- **Difficulty:** Progression scaling in both **story and bonus levels**.
- **Dynamics:** Alternation of **challenging main levels** and **rewarding bonus levels**.
- **Rewards:** Distribution of **hearts** based on **bonus level difficulty**.

---

## **Entities for Balancing**

### **Main Levels:**
- **Total number of levels:** 10
- **Difficulty parameters:** Note speed, screamer frequency, distractions.

### **Bonus Levels:**
- **Total number of levels:** 4
- **Rewards:** Hearts (**extra lives against screamers**)
- **Difficulty:** Increases progressively.

### **Rewards:**
| Bonus Level Difficulty | Hearts Rewarded |
|------------------------|----------------|
| Easy                  | 1 heart        |
| Medium                | 2 hearts       |
| Hard                  | 3 hearts       |

### **Player Options:**
- Players **can skip bonus levels**, keeping their focus on the **main storyline**.

---

## **Balancing Parameters**

### **Level Difficulty:**
- **Main levels:** 
  - **Note speed increases**.
  - **Intervals between notes shorten**.
  - **Screamer frequency rises**.
- **Bonus levels:** 
  - **Harder than main levels**.

### **Heart Distribution in Bonus Levels:**
| Bonus Level Type | Hearts Rewarded |
|------------------|----------------|
| Easy Bonus      | 1 heart        |
| Medium Bonus    | 2 hearts       |
| Hard Bonus      | 3 hearts       |

### **Bonus Level Placement:**
- Bonus levels **appear between main levels**.

---

## **Balancing Table**

| Stage       | Level Type  | Difficulty    | Reward      |
|------------|------------|--------------|------------|
| Level 1    | Main       | Easy         | -          |
| Level 2    | Main       | Easy         | -          |
| Bonus 1    | Bonus      | Easy+        | 1 heart    |
| Level 3    | Main       | Medium       | -          |
| Level 4    | Main       | Medium       | -          |
| Bonus 2    | Bonus      | Medium+      | 2 hearts   |
| Level 5    | Main       | High         | -          |
| Level 6    | Main       | High         | -          |
| Bonus 3    | Bonus      | High+        | 2 hearts   |
| Level 7    | Main       | Very High    | -          |
| Level 8    | Main       | Very High    | -          |
| Bonus 4    | Bonus      | Very High+   | 3 hearts   |
| Level 9    | Main       | Extreme      | -          |
| Level 10   | Main       | Extreme+     | -          |

---

## **Formulas**

### **Bonus Level Difficulty Calculation:**
Bonus level difficulty is determined as the **average** between the **previous and next** main level difficulties:

```
Bonus Difficulty = (Previous Main Level Difficulty + Next Main Level Difficulty) / 2
```

---

## **Justification for Bonus Level Dynamics**

### **Level Alternation:**
- Bonus levels provide a **mid-level challenge** and give players a **choice**: 
  - **Accept the challenge** for a **useful boost** (**hearts**).
  - **Skip the level** and continue the story.

### **Why Medium Difficulty for Bonus Levels?**
1. **Fairness:** Bonus levels are difficult enough to make the rewards feel **earned**, but not so hard that they become frustrating.
2. **Flexibility:** Players can either **play for extra boosts** or **skip to focus on the story**.

### **Player Choice & Flexibility:**
- Skipping **bonus levels** gives **freedom of choice**, preventing frustration.
- Players **who enjoy a harder challenge** and complete the game without **boosts** can receive a **high-rarity achievement in Steam**, motivating **hardcore players**.

---

## **Why This Balancing Approach?**
- Ensures **player engagement** without **breaking game flow**.
- **Bonus levels remain important**, but **optional**, allowing **players to set their own challenge level**.

---

This document establishes a **structured and fair progression system** for *Musical Terror*, ensuring **player motivation and challenge balance**.
