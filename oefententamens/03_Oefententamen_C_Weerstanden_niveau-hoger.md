# OOP (203049) – Practice exam C: Resistors
**Niveau: één stap hoger dan het voorbeeld van de prof** · Language: C++20 · Tijdsindicatie: ~3 uur

*Zelfde opbouw als het echte tentamen, maar elke stap haalt er een onderwerp uit de cursus bij dat de prof niet expliciet vraagt: output parameters, function overloading, lambdas, meerdere bestanden, virtual/override, concepts.*

---

### Step 1
*Stof: H7 Arrays*
- The theme of this task are electrical resistors.
- Declare two arrays of five elements: one `double` array with resistance values (Ω) and one `int` array with tolerances (%).

### Step 2
*Stof: H5 Flow control (`switch`/logische operatoren), H6 Loops*
- Read five resistors from the keyboard.
- Resistance must be > 0. Tolerance must be one of the standard values **1, 2, 5 or 10**.
  - Invalid input → ask again (use a `do-while` loop).

### Step 3
*Stof: H8 Pointers (`new[]`, `delete[]`, `std::nothrow`), H9 References*
- Allocate the arrays dynamically; the user determines the size.
- Check whether the allocation succeeded using `new (std::nothrow)` and a `nullptr` check.
- Write a function `grow(...)` that **doubles** the capacity of the `double` array while keeping the existing data (allocate new, copy, `delete[]` old).
  - The function must be able to change the caller's pointer. Pass it as a **reference to a pointer** (`double*&`).
  - Explain: why does `grow(double* data, ...)` not work?

### Step 4
*Stof: H4 Operations on data, H6 Loops*
- Calculate and print:
  - the total resistance when all resistors are in **series**,
  - the total resistance when all resistors are in **parallel** (1/R = 1/R1 + 1/R2 + …),
  - for each resistor its minimum and maximum value given its tolerance.

### Step 5
*Stof: H2*
- Comment the code.

### Step 6
*Stof: H11 Functions (pass by value/pointer/reference, `const`), H12 Getting things out of functions, H13 Function overloading*
- Separate functions:
  - `readResistor(double& value, int& tolerance)`.
  - `seriesTotal(const double* values, size_t n)` and `parallelTotal(const double* values, size_t n)`.
  - `minMax(double value, int tolerance, double& min, double& max)` – gives **two** results back via **output parameters**.
- **Overload** `seriesTotal` with a version `seriesTotal(double r1, double r2)` for exactly two resistors.
- Explain: what does `const` add in `const double* values`? How does the compiler choose the right overload?

### Step 7
*Stof: H17 Classes (constructors, initializer list, getters/setters, `this`, multiple files, include guards)*
- Make the class `Resistor` with private members `value` and `tolerance`.
- Provide:
  - a default constructor and a parameterised constructor (use a **member initializer list**),
  - getters and setters (the setters reject invalid values),
  - member functions `minValue()` and `maxValue()`.
- Split the class over **`Resistor.h`** (with include guards) and **`Resistor.cpp`** (use `Resistor::`).
- Change the code to use class `Resistor`.

### Step 8
*Stof: `<<` als `friend` in H18 · ⚠️ `>>` en `+`, `<` niet in cursus*
- Overload `>>` and `<<` (output e.g. `4.7 kOhm +/-5%` – use kOhm/MOhm when appropriate).
- Overload `+` so that `r1 + r2` returns a new `Resistor` for the **series** connection.
- Overload `<` so resistors can be compared by value.

### Step 9
*Stof: H14 Lambda functions · ⚠️ `std::list` niet in cursus*
- Change the container to `std::list<Resistor>`.
- Print all resistors with a range-based `for` loop.
- Use a **lambda** with `remove_if` to remove all resistors with value above a limit the user enters. The lambda must **capture** that limit.
- Explain: what is the difference between capture by value `[limit]` and capture by reference `[&limit]`?

### Step 10
*Stof: H18 Inheritance (base constructor, `protected`), H19 Polymorphism (`virtual`, `override`, virtual destructor, `dynamic_cast`)*
- Make an inherited class `PowerResistor` with an extra member `maxPower` (W).
  - Its constructor passes value and tolerance to the `Resistor` constructor.
  - Add a function `maxCurrent()` = √(P / R).
- Make `print()` a **virtual** function in `Resistor` and **override** it in `PowerResistor` (use the `override` keyword).
- Give `Resistor` a **virtual destructor**.
- Store both kinds in a `std::vector<std::unique_ptr<Resistor>>` (or an array of `Resistor*`) and print all of them in one loop.
- Loop again and use `dynamic_cast` to print `maxCurrent()` **only** for the power resistors.
- Explain: what happens if `print()` is **not** virtual? What is object slicing?

### Step 11
*Stof: H15 Function templates, H16 C++20 concepts*
- Make a function template `Square(x)` that returns x·x and use it with `int` and `double`.
- Make a function template `Largest(a, b)` and use it with two `double`s **and** with two `Resistor`s.
- Constrain `Largest` with a **concept** that requires `a < b` to be valid (`requires`-expression).
- Show that calling it with a type without `<` gives a clear compiler error.

---

*⚠️ = staat niet in de C++-cursus (freeCodeCamp), maar hoort bij wat de prof vraagt.*

**Extra t.o.v. het voorbeeld:** `std::nothrow` · reference-to-pointer · output parameters · function overloading · initializer lists · `.h`/`.cpp` + include guards · binary operators · lambdas met capture · `virtual`/`override`/virtual destructor · `dynamic_cast` · concepts
