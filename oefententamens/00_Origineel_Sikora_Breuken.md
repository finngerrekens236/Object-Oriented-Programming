# OOP (203049) – Midterm/Final exam example (Prof. Marjan Sikora)

*Origineel, ontvangen per mail op 29-10-2026. Het tentamen maak je op de computer in het lab: je bouwt één programma stap voor stap op. Je cijfer hangt af van hoeveel stappen je haalt en hoeveel hulp je nodig hebt.*

Language: C++

---

### Step 1
- The theme of this task are fraction numbers.
- Declare two arrays of type `double`, each containing five variables.
- These arrays will contain the numerators and denominators of fraction numbers.

### Step 2
- Read five fraction numbers from the keyboard.
- When reading, make sure that the denominators are not zero.
  - If the user enters zero as denominator, ask him to enter the denominator again.

### Step 3
- Change the program so that:
  - it allocates the arrays dynamically,
  - the user determines the array size.

### Step 4
- For each fraction number:
  - calculate its decimal value,
  - write the decimal value to the screen.

### Step 5
- Comment the code.

### Step 6
- Move the code for reading of one fraction number with zero checking to a separate function.
  - Function arguments should be numerator and denominator, passed as **references**.
- Move the code for calculating the decimal value into a separate function.
  - Function arguments should be numerator and denominator, passed as **values**.
  - The decimal value should be returned as the function value.
- Why are the arguments passed in different ways?

### Step 7
- Make the class `Fraction` that contains numerator and denominator.
- Make the denominator `private`.
- Change the code to use class `Fraction`.

### Step 8
- Overload the operator of reading (`>>`) and use it instead of the function for reading.
- Overload the operator for writing (`<<`).

### Step 9
- Change the container, from array to a list.

### Step 10
- Make the inherited class that has an upper and lower limit of the decimal value.

### Step 11
- Make a template of a `Square` function.

---

> "When taking a midterm you will do as many steps as you have watched videos and prepared yourselves. The rest you will do on the final exam. I will give you the grade based on how many steps you did and based on how well you performed. For example if I have to help you a lot your grade will be lower. Also if you didn't cover all steps in the final exam your grade will also be lower." – M. Sikora
