# Undo/Redo with Stacks (C++)

A C++ console project that implements **Undo** and **Redo** for a string using two `stack` containers from the STL.

---

## About

The `clsMystring` class stores a string and keeps track of its history, so every change can be undone and redone, just like in a text editor.

---

## Project Structure

```
Stack-Project-Undo-and-Redo/
├── main.cpp                    # Test program
├── clsMystring.h               # Undo/Redo string class
├── Project_7.sln               # Visual Studio solution
├── Project_7.vcxproj
├── Project_7.vcxproj.filters
└── .gitignore
```

---

## How It Works

| Member | Purpose |
|---|---|
| `_Value` | The current string |
| `_Undo` | Stack of previous values |
| `_Redo` | Stack of values that were undone |

- **Set value**: the current value is pushed to the Undo stack, then replaced by the new one.
- **Undo**: the current value goes to the Redo stack, and the last value from the Undo stack becomes the current one.
- **Redo**: the current value goes to the Undo stack, and the last value from the Redo stack becomes the current one.

---

## Example

```cpp
clsMystring S1;
S1.value = "Mohammed";
S1.value = "Mohammed2";
S1.value = "Mohammed3";

S1.Undo();   // Mohammed2
S1.Undo();   // Mohammed
S1.Redo();   // Mohammed2
```

---

## Concepts Used

- Classes and encapsulation
- STL `stack`
- Properties using `__declspec(property)`
- Getters and setters
