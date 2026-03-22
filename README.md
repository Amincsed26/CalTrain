# 🚆 CalTrain Synchronization Project

## 📌 Overview

This project implements a solution to the **CalTrain synchronization problem**, a classic concurrency problem in operating systems.

The goal is to coordinate multiple passenger threads and train threads such that:

* Passengers wait for a train to arrive
* Trains allow passengers to board safely
* No race conditions or deadlocks occur

The implementation is written in **C** using synchronization primitives such as **mutexes**, **condition variables**, and/or **semaphores**.

---

## 🖼️ Project Preview
![caltrain](https://github.com/WorldisAmen/California-Train/assets/145727573/b9528552-4e95-4556-945d-f2d709153430)
![image](https://github.com/WorldisAmen/California-Train/assets/145727573/170b0e84-2891-4c7f-ab50-e137388cd936)

---

## 🎯 Problem Description

In the CalTrain system:

* Passengers arrive at a station and wait for a train
* A train arrives with a limited number of available seats
* Passengers board the train until:

  * The train is full, or
  * There are no more waiting passengers
* The train departs only after all boarding passengers are seated

### Constraints

* No passenger boards before a train arrives
* The number of boarding passengers must not exceed available seats
* Proper synchronization must be ensured between threads

---

## ⚙️ Features

* Thread-safe implementation
* Handles multiple passengers and trains concurrently
* Prevents race conditions, deadlocks, and starvation
* Efficient synchronization between threads

---

## 🧠 Concepts Used

* Multithreading (POSIX Threads - `pthreads`)
* Mutex locks
* Condition variables
* Thread synchronization techniques

---

## 🏗️ Project Structure

```
.
├── caltrain.c
├── Makefile
└── README.md
```

---

## 🔧 How It Works

### Passenger Thread

* Waits for a train to arrive
* Boards when space is available
* Signals when seated

### Train Thread

* Announces arrival
* Allows passengers to board
* Waits until boarding is complete
* Departs afterward

---

## ▶️ Compilation & Execution

### Compile

```bash
gcc -pthread caltrain.c -o caltrain
```

### Run

```bash
./caltrain
```

---

## 🧪 Example Scenario

1. Multiple passengers arrive at the station
2. A train arrives with limited seats
3. Only some passengers board
4. Others wait for the next train

---

## 🚨 Synchronization Challenges Solved

* Preventing passengers from boarding before train arrival
* Avoiding overbooking
* Ensuring proper coordination before departure

---
