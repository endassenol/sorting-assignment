
# Sorting Assignment – Bubble Sort on Python List & Linked List

This project is part of Assignment #4 for the "Sorting @ GitHub Actions" module. The main goal is to implement the **Bubble Sort algorithm** such that it works on both a regular **Python list** and a **custom Linked List** structure, and to validate this functionality through **unit testing and GitHub Actions**.

## 🧠 Project Overview

The codebase allows the `bubble_sort()` function to accept two different data structures:
- A built-in Python `list` (already implemented),
- A custom `LinkedList` class, which we extended to support sorting.

All sorting logic and data structure management is done in pure Python.

## 📦 File Structure

```
sorting-assignment/
├── ds.py                    # Node and LinkedList class definitions
├── main.py                  # Example runner or entry point (optional)
├── sorting_algorithms.py   # bubble_sort implementation
├── tests/
│   ├── __init__.py
│   └── test_sorting.py     # Unit tests for sorting algorithm
├── .github/
│   └── workflows/
│       └── python-tests.yml # GitHub Actions CI
```

## 🔁 How `__iter__()` Was Used

To allow `LinkedList` objects to be iterated (e.g., used in loops or converted to lists), we implemented the `__iter__()` method inside the `LinkedList` class. This enabled us to easily write unit tests like:

```python
assert list(linked_list) == [1, 2, 3]
```

It also made the internal values of the linked list visible during test assertions.

## ⚙️ GitHub Actions Integration

We used **GitHub Actions** to automate test runs every time we push code to the repository. The workflow file `python-tests.yml` installs dependencies and runs the `unittest` framework on our `tests/` folder.

### Workflow Trigger
```yaml
on:
  push:
    branches: [master]
  pull_request:
    branches: [master]
```

## ✅ Unit Testing

All test cases are written using Python’s built-in `unittest` module. Test coverage includes:
- Sorting a regular Python list
- Sorting a custom linked list
- Edge cases: single-element, empty list, negative values, already sorted input

Run tests locally with:
```bash
python -m unittest discover tests
```

## ❗Error vs Failure

- **Error**: Occurs when the test cannot run at all (e.g., syntax error, attribute not found).
- **Failure**: The test runs but the result is not what we expected.

### Example

- Error:
  ```bash
  AttributeError: 'LinkedList' object has no attribute 'next'
  ```

- Failure:
  ```bash
  AssertionError: [2, 1] != [1, 2]
  ```

## 🤖 AI Usage

This README and parts of the implementation guidance were assisted by **ChatGPT** to clarify the structure, edge cases, and documentation best practices. However, all code was written and understood by me as part of the learning process.

---

### 📅 Deadline: 21 May 2025  
Project completed and pushed with automated test verification.
