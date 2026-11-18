# OOP (203049) – Practice exam B: Time durations
**Niveau: gelijk aan het voorbeeld van de prof** · Language: C++ · Tijdsindicatie: ~2–2,5 uur

*Bouw één programma stap voor stap op. Bewaar na elke stap een werkende versie.*

---

### Step 1
*Stof: H7 Arrays*
- The theme of this task are time durations (e.g. *2 h 45 min*).
- Declare two arrays of type `int`, each containing five variables.
- These arrays will contain the hours and the minutes of the durations.

### Step 2
*Stof: H5 Flow control, H6 Loops*
- Read five durations from the keyboard.
- When reading, make sure that:
  - hours are not negative,
  - minutes are in the range 0–59.
  - If the user enters an invalid value, ask him to enter that value again.

### Step 3
*Stof: H8 Pointers*
- Change the program so that:
  - it allocates the arrays dynamically,
  - the user determines the array size.

### Step 4
*Stof: H4 Operations on data (`/` en `%`), H6 Loops*
- For each duration:
  - calculate the total number of minutes,
  - write it to the screen.
- Also write the **sum** of all durations in the format `H h M min`.

### Step 5
*Stof: H2*
- Comment the code.

### Step 6
*Stof: H11 Functions, H9 References*
- Move the code for reading one duration (with checking) to a separate function.
  - Function arguments should be hours and minutes, passed as **references**.
- Move the code for calculating the total minutes into a separate function.
  - Function arguments should be hours and minutes, passed as **values**.
  - The total minutes should be returned as the function value.
- Explain: why are the arguments passed in different ways?

### Step 7
*Stof: H17 Classes*
- Make the class `Duration` that contains hours and minutes.
- Make minutes `private`, with a setter that only accepts 0–59.
- Change the code to use class `Duration`.

### Step 8
*Stof: ⚠️ `>>` niet in cursus; `<<` als `friend` in H18*
- Overload the operator of reading (`>>`) and use it instead of the function for reading.
- Overload the operator for writing (`<<`), output format: `2h45m`.

### Step 9
*Stof: ⚠️ `std::list` niet in cursus*
- Change the container, from array to a `std::list<Duration>`.

### Step 10
*Stof: H18 Inheritance (protected, base constructor)*
- Make the inherited class `LimitedDuration` that has a **maximum** total duration (in minutes).
  - When reading, a `LimitedDuration` that exceeds its maximum must be entered again.

### Step 11
*Stof: H15 Function templates (array + grootte als parameter)*
- Make a template of a `Sum` function that adds all elements of an array of any type and returns the result.
- Use it on an `int` array and on a `double` array.

---

*⚠️ = staat niet in de C++-cursus (freeCodeCamp), maar de prof vraagt het wel. Zoek het apart op (bv. cppreference) of vraag uitleg.*

**Wordt getoetst:** arrays · range checking · dynamic allocation · pass-by-value vs pass-by-reference · class / `private` / setter · operator overloading · `std::list` · inheritance · function template
