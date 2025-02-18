# 🎹 Game Design Document: Piano Rhythm Mechanics

## 1. Purpose of the Mechanic

The goal of this mechanic is to create an **intense rhythm-based gameplay** where the player must press the correct keys in sync with falling notes, avoiding mistakes to complete the level.

## 2. General Description

On-screen notes **fall from the top to the activation zone at the bottom**. The player must press the corresponding keyboard key when the note reaches the activation area.

## 3. Functionality

**Gameplay Loop:** Notes descend towards the activation zone, and the player must press the correct key at the right moment.

Each note corresponds to a specific keyboard key:

| Key | Note |
|----|----|
| A  | C (Do) |
| S  | D (Re) |
| D  | E (Mi) |
| F  | F (Fa) |
| -  | - |
| J  | G (Sol) |
| K  | A (La) |
| L  | B (Si) |
| ;  | C (High Do) |

**Mistakes:** If the player misses a note or presses the wrong key, the game **immediately ends**. Mistakes are not forgiven, increasing tension and requiring high precision.

## 4. Interface

- **Note Field:** The central part of the screen where notes fall from top to bottom.
- **Activation Zone:** The bottom area where the player must press the correct key.
- **Missed Notes:** Notes disappear when they move past the activation zone without being hit.

## 5. Balancing

The **falling speed of notes** increases with each level, requiring quicker reflexes.

| Level | Note Speed |
|------|------------|
| 1    | 1.0        |
| 2    | 1.5        |
| 3    | 2.0        |
| 4    | 2.5        |
| 5    | 3.0        |

### **Adjustment Parameters**

1. **Initial Note Speed (`initial_note_speed`)**  
   - Description: The base speed of falling notes at level 1.  
   - Value: `1.0` (arbitrary units).  

2. **Speed Increment (`note_speed_increment`)**  
   - Description: How much faster the notes fall per level.  
   - Value: `0.5`.  

3. **Max Level (`max_level`)**  
   - Description: The highest level where note speed is defined.  
   - Value: `5`.  

4. **Max Note Speed (`max_note_speed`)**  
   - Description: The upper limit of note speed (to prevent excessive difficulty).  
   - Value: `3.0` (at level 5).  

5. **Activation Zone Y Position (`activation_zone_y`)**  
   - Description: Y-coordinate for the activation zone where players must hit notes.  
   - Value: `90%` of the screen height (adjustable).  

6. **Difficulty Increase Rate (`difficulty_increase_rate`)**  
   - Description: Percentage-based or coefficient-based increase in difficulty (e.g., note frequency or distractions) per level.  
   - Value: `1.2` (20% increase per level).  

7. **Key Bindings (`key_binding_type`)**  
   - Description: The keyboard layout assigned to piano notes.  
   - Value: Standard set (A, S, D, F, J, K, L, ;).  

## 6. Analytics

To track player behavior and collect data for improving the mechanics, the following events should be logged:

1. **Level Start (`level_start`)**  
   - Logs the start of a level to track attempts and restarts.  

2. **Level Completion (`level_complete`)**  
   - Logs successful completion of a level, measuring completion rates.  

3. **Missed Note (`note_miss`)**  
   - Logs missed or incorrect key presses, helping identify difficult parts of a level.  

4. **Active Play Time (`active_play_time`)**  
   - Tracks time spent on a level, including pauses.  

5. **Screamer Trigger (`screamer_triggered`)**  
   - Logs when the screamer is activated, tracking player mistakes.  

6. **Level Restarts (`level_restart_count`)**  
   - Tracks how often players restart after failing, indicating difficulty balance.  

7. **Game Over (`game_over`)**  
   - Logs when and where the player fails to complete the game.  

## 7. Systems Affected

Implementing the **piano rhythm mechanic** impacts several game systems:

1. **Rhythm Game UI**  
   - Adding the note field, activation zone, and timer.  
   - Updating UI to reflect current level and remaining time.  

2. **Audio System**  
   - Integrating piano sounds and distracting noises from monsters.  
   - Adjusting volume and sound frequency to increase/decrease tension.  

3. **Error & Punishment System**  
   - Implementing consequences for mistakes (screamer activation and game over).  
   - Adding "one fatal mistake" logic affecting the level outcome.  

4. **Analytics**  
   - Logging key events like level starts, mistakes, restarts, and more.  

5. **Level Progression System**  
   - Adjusting game parameters like note speed and level duration.  
   - Ensuring automatic difficulty scaling as the player progresses.  

---

This document provides a **detailed breakdown of the piano rhythm mechanic**, ensuring **precise gameplay balance and immersive horror elements** in *Musical Terror*.
