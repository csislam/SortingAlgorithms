# SortingAlgorithms.java

![Java](https://img.shields.io/badge/Language-Java-blue?style=flat-square)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)
![Build Status](https://github.com/csislam/SortingAlgorithms/actions/workflows/java.yml/badge.svg)

> Educational and research-focused Java implementations of classic sorting algorithms with performance benchmarks and modular design.

---

## 📌 Overview

This repository provides clean implementations of essential sorting algorithms in Java for research, education, and benchmarking purposes.

### 🧠 Implemented Algorithms

- 🔁 Bubble Sort
- 📥 Insertion Sort
- 📤 Selection Sort
- 🧩 Merge Sort
- ⚡ Quick Sort
- 🗂️ Heap Sort
- 📊 Counting Sort
- 🧮 Radix Sort
- 🌀 Shell Sort

---

## 📖 Research & Educational Purpose

Sorting algorithms are critical for data processing, system design, and algorithmic research. This project aims to serve as:

- A **benchmarking suite** for runtime/memory trade-offs
- A **learning resource** for CS students & interview prep
- A **reference base** for hybrid or parallel sorting research

### 🎓 Learning Outcomes

- Understand algorithmic complexity: time & space
- Identify stable vs unstable algorithms
- Conduct empirical comparisons
- Analyze behavior on various dataset types

---

## 📊 Performance Benchmark (Empirical)

Run on Java 17, Intel i7, 16GB RAM (Random array, size: 100,000)

| Algorithm      | Time (ms) | Space      | Stable |
|----------------|-----------|------------|--------|
| Bubble Sort    | 2500+     | O(1)       | ✅     |
| Insertion Sort | 1800+     | O(1)       | ✅     |
| Selection Sort | 2200+     | O(1)       | ❌     |
| Merge Sort     | 90        | O(n)       | ✅     |
| Quick Sort     | 65        | O(log n)   | ❌     |
| Heap Sort      | 100       | O(1)       | ❌     |
| Counting Sort  | 15        | O(k+n)     | ✅     |
| Radix Sort     | 30        | O(n+k)     | ✅     |
| Shell Sort     | 130       | O(1)       | ❌     |

---

## 🚀 Usage

### Compile

```bash
javac src/*.java

Run
bash
Copy
Edit
java src/SortingTest
Example
java
Copy
Edit
int[] arr = {9, 3, 7, 1, 4};
MergeSort.sort(arr);
System.out.println(Arrays.toString(arr)); // Output: [1, 3, 4, 7, 9]
⚙️ Benchmark Example
java
Copy
Edit
long start = System.nanoTime();
QuickSort.sort(arr);
long end = System.nanoTime();
System.out.println("QuickSort Time (ns): " + (end - start));
📚 References
Cormen et al., Introduction to Algorithms

Knuth, The Art of Computer Programming

https://www.geeksforgeeks.org

https://visualgo.net/en/sorting

https://ocw.mit.edu

🛠️ Contributing
Pull requests are welcome! Please include test cases for new algorithms.


---

### ✅ Optional: Setup GitHub Actions

To enable the badge and CI:

1. Create `.github/workflows/java.yml` in your repo.
2. Paste this GitHub Actions workflow:

```yaml
name: Java CI

on: [push, pull_request]

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Set up JDK 17
        uses: actions/setup-java@v3
        with:
          java-version: '17'
          distribution: 'temurin'
      - name: Compile Java
        run: javac src/*.java
      - name: Run Tests
        run: java src/SortingTest
