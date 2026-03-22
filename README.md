# University Progression Prediction System

## Overview
This is a simple **Python-based system** that helps universities track student progression based on their **credit scores**. The program prompts users to enter student credits, calculates total credits, and categorises their academic progression outcome. It also provides a **text-based histogram**, stores data in a **text file**, and uses a **dictionary** to map student IDs to their outcomes.


## Features
- **Input Validation** – Accepts only valid credit values (multiples of 20, from 0 to 120)
- **Total Credit Verification** – Ensures pass + defer + fail credits always equal 120
- **Progression Classification** – Categorises each student into one of four outcomes
- **Histogram Display** – Shows a `*`-based count of students per outcome category
- **List Storage** – Maintains separate lists per outcome for structured output
- **File Output** – Saves all student records to `output.txt`
- **Dictionary Mapping** – Maps University of Westminster student IDs to their outcomes (Part 4)


## Progression Outcomes

| Outcome | Condition |
|---|---|
| **Progress** | 120 credits passed |
| **Progress – Module Trailer** | 100 credits passed (1 module trailed) |
| **Do Not Progress – Module Retriever** | Any other valid combination |
| **Exclude** | 80 or more credits failed |

> **Note:** A student progresses with a module trailer when they have passed 100 credits — they move to the next year but must carry forward the trailed module.


## Project Structure

```
University-Progression-Prediction-System/
│
├── part1.py      # Core logic + histogram
├── part2.py      # Adds list storage and structured output
├── part3.py      # Adds file output to output.txt
├── part4.py      # Adds UoW student ID and dictionary mapping
└── output.txt    # Generated at runtime by part3.py / part4.py
```

## How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/University-Progression-Prediction-System.git
   cd University-Progression-Prediction-System
   ```

2. **Run the desired part:**
   ```bash
   python part1.py
   # or
   python part4.py
   ```

3. **Follow the prompts** – enter credits and view results at the end.


## Input Rules

- **Valid credit values:** `0, 20, 40, 60, 80, 100, 120`
- This applies to **pass, defer, and fail credits**
- The three values **must add up to exactly 120**
- Credits must be entered as **whole numbers (integers)**
- Part 4 also prompts for a **UoW student ID** before each set of credits


## Sample Output

```
Enter your credits at pass: 120
Enter your credits at defer: 0
Enter your credits at fail: 0
Progress

Histogram
Exclude   0 :
Progress  1 : *
Trailer   0 :
Retriever 0 :
1 outcomes in total.
```

### Part 3 – output.txt
```
Part 3:
Progress - 120, 0, 0
Module retriever - 80, 40, 0
```

### Part 4 – Dictionary output
```
w123456 : Progress - 120, 0, 0
w789012 : Do not progress (module retriever) - 80, 40, 0
```

## Known Limitations
- Parts 1–4 are written as separate scripts; they do not share state between runs
- `output.txt` is overwritten each time Part 3 or Part 4 is run
- The program does not persist data between separate executions


## Project Info
- **Year:** 2023
- **Level:** First Year Undergraduate Coursework