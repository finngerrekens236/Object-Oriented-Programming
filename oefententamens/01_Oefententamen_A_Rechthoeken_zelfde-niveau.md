# OOP (203049) – Practice exam A: Rectangles
**Niveau: gelijk aan het voorbeeld van de prof** · Language: C++ · Tijdsindicatie: ~2–2,5 uur

*Bouw één programma stap voor stap op. Bewaar na elke stap een werkende versie (bv. `step03.cpp`), zodat je altijd iets kunt laten zien.*

---

### Step 1
*Stof: H7 Arrays*
- The theme of this task are rectangles.
- Declare two arrays of type `double`, each containing five variables.
- These arrays will contain the widths and heights of rectangles.

### Step 2
*Stof: H5 Flow control, H6 Loops*
- Read five rectangles from the keyboard.
- When reading, make sure that width and height are **greater than zero**.
  - If the user enters a value ≤ 0, ask him to enter that value again.

### Step 3
*Stof: H8 Pointers (dynamische arrays, `delete[]`)*
- Change the program so that:
  - it allocates the arrays dynamically (`new[]`),
  - the user determines the array size,
  - the memory is released correctly at the end of the program.

### Step 4
*Stof: H6 Loops*
- For each rectangle:
  - calculate its area and its perimeter,
  - write both values to the screen.
- After the loop, write which rectangle has the **largest area** (its index and its area).

### Step 5
*Stof: H2 (commentaar)*
- Comment the code.

### Step 6
*Stof: H11 Functions (pass by value/reference), H9 References*
- Move the code for reading one rectangle (with the > 0 check) to a separate function.
  - Function arguments should be width and height, passed as **references**.
- Move the code for calculating the area into a separate function.
  - Function arguments should be width and height, passed as **values**.
  - The area should be returned as the function value.
- Explain: why are the arguments passed in different ways?

### Step 7
*Stof: H17 Classes (constructors, getters/setters)*
- Make the class `Rectangle` that contains width and height.
- Make **both** members `private`.
- Add a constructor (default values 1 and 1), getters, and setters that refuse values ≤ 0.
- Add member functions `area()` and `perimeter()`.
- Change the code to use class `Rectangle`.

### Step 8
*Stof: ⚠️ `>>` niet in cursus; `<<` als `friend` in H18*
- Overload the operator of reading (`>>`) and use it instead of the function for reading.
- Overload the operator for writing (`<<`), so it prints e.g. `Rectangle 4 x 2.5 (area 10)`.

### Step 9
*Stof: ⚠️ `std::list` niet in cursus*
- Change the container, from array to a `std::list<Rectangle>`.
- The user keeps entering rectangles until he enters width `0` (no fixed size anymore).

### Step 10
*Stof: H18 Inheritance (base constructor aanroepen)*
- Make the inherited class `Square` (derived from `Rectangle`) in which width and height are always equal.
  - Its constructor takes only one side length.
  - Make sure a `Square` can still be written with `<<`.

### Step 11
*Stof: H15 Function templates*
- Make a function template `Larger(a, b)` that returns the larger of two values.
- Use it with two `double`s and with two `int`s.

---

*⚠️ = staat niet in de C++-cursus (freeCodeCamp), maar de prof vraagt het wel. Zoek het apart op (bv. cppreference) of vraag uitleg.*

**Wordt getoetst:** arrays · input validation · `new[]`/`delete[]` · pass-by-value vs pass-by-reference · class / encapsulation / constructor · operator overloading (`>>`, `<<`) · `std::list` · inheritance · function template
