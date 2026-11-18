# OOP (203049) – Practice exam D: Sensor measurements
**Niveau: één stap hoger dan het voorbeeld van de prof** · Language: C++20 · Tijdsindicatie: ~3 uur

*Deze variant legt de nadruk op objecten met eigen geheugen (destructor, copy constructor), inheritance-ketens en abstracte classes als interface.*

---

### Step 1
*Stof: H7 Arrays*
- The theme of this task are measurements from temperature sensors.
- Declare an array of five `double` values (temperatures in °C) and an array of five `int` values (timestamps in seconds).

### Step 2
*Stof: H5 Flow control, H6 Loops*
- Read five measurements from the keyboard.
- Temperature must be in the range −40 … 125 °C (sensor range).
- Each timestamp must be **larger than the previous one**; otherwise ask again.

### Step 3
*Stof: H8 Pointers (dynamische arrays, `try`/`catch` bij `new`)*
- Allocate the arrays dynamically; the user determines the size.
- Put the allocation inside `try`/`catch (std::bad_alloc&)` and print a message if it fails.
- Print the average, the minimum and the maximum temperature.

### Step 4
*Stof: H4 Operations on data, H6 Loops*
- For every pair of consecutive measurements calculate the rate of change in °C per minute and print it.
- Print a warning for every rate whose absolute value is above 2 °C/min.

### Step 5
*Stof: H2*
- Comment the code.

### Step 6
*Stof: H11 Functions, H12 Getting things out of functions*
- Separate functions:
  - `readMeasurement(double& temp, int& time, int previousTime)` – explain each choice of passing.
  - `average(const double* data, size_t n)` – returns the average **by value**.
  - `minMax(const double* data, size_t n, double& min, double& max)` – output parameters.
  - `warningCount(const double* temps, const int* times, size_t n, int* count)` – output parameter **via pointer**.
- Explain: what are the ways a function can give a result back? Why must you never return a reference to a local variable?

### Step 7
*Stof: H17 Classes (constructor, destructor, `this`, pointer-member) · copy constructor: H18*
- Make the class `MeasurementSeries` that **owns dynamically allocated arrays** of temperatures and timestamps (private pointer members) plus `size` and `capacity`.
  - Constructor (capacity) that allocates with `new[]`; destructor that frees with `delete[]`. Print a line in both so you can see when they run.
  - `add(temp, time)` that grows the arrays when they are full.
  - `average()`, `min()`, `max()`.
- Write a **copy constructor** that makes a **deep copy**.
- Show in `main` that:
  - passing a series **by value** to a function calls the copy constructor,
  - changing the copy does **not** change the original.
- Explain: what goes wrong without the copy constructor when the object is passed by value? (Tip: zie "Pass by value en het pointer-member" in H17.)

### Step 8
*Stof: `friend operator<<` in H18 · ⚠️ `>>` en `[]` niet in cursus*
- Overload `<<` for `MeasurementSeries` as a `friend` (print a small table).
- Overload `>>` to read one measurement into the series.
- Overload `[]` so `series[i]` returns the i-th temperature.

### Step 9
*Stof: H14 Lambda functions · ⚠️ `std::list` niet in cursus*
- Make a `std::list<MeasurementSeries>` with series from three different days.
- Write a function `printIf(const std::list<MeasurementSeries>& list, F condition)` that prints only the series for which the lambda `condition` returns `true`.
- Call it twice: once with a lambda "average above 20 °C", once with a lambda that **captures** a threshold the user enters.

### Step 10
*Stof: H18 Inheritance (protected, base constructors, chain), H19 Polymorphism (pure virtual, abstract class, `override`, `final`, virtual destructor)*
- Make an **abstract** base class `Sensor` with:
  - a `protected` member `name`,
  - a pure virtual function `double read() const`,
  - a virtual destructor.
- Derive `TemperatureSensor` (returns a temperature) and derive `CalibratedTemperatureSensor` from `TemperatureSensor` (adds an `offset`; its constructor calls the `TemperatureSensor` constructor). Mark `CalibratedTemperatureSensor` as `final`.
- Fill a `std::vector<std::unique_ptr<Sensor>>` with both types and read all sensors in one loop.
- Explain: why can't you make an object of type `Sensor`? Why can't you store the sensors in a `std::vector<Sensor>`?

### Step 11
*Stof: H15 Function templates (+ specialization), H16 C++20 concepts*
- Make a function template `Average(const T* data, size_t n)` that works for `int` and `double` arrays.
- Constrain it with the standard concept `std::integral || std::floating_point` (or your own concept).
- Write a **template specialization** of `Average` for `const char*`-arrays that prints a message instead of calculating.
- Explain: why does a template not generate any code until you call it?

---

*⚠️ = staat niet in de C++-cursus (freeCodeCamp), maar hoort bij wat de prof vraagt.*

**Extra t.o.v. het voorbeeld:** `try`/`catch` met `bad_alloc` · output parameters via pointer en reference · resource-owning class · destructor · deep copy / copy constructor · `friend` · lambdas als parameter · `protected` · inheritance-keten · abstract class / pure virtual · `final` · smart pointers · template specialization · concepts
