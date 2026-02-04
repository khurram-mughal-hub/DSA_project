# Swiftex Logistics: Online Parcel Tracking & Management System

Swiftex Logistics is a high-performance C++ simulation of a modern courier service. The project features a dual-terminal architecture: a **Client Panel** for users to book and track parcels, and an **Admin Dashboard** for live monitoring and route management.

This project was developed as a 3rd-semester **Data Structures and Algorithms (DSA)** final project, emphasizing manual implementation of core structures without relying on the STL.

## 🚀 Key Features

### 📦 Client Panel (`source.cpp`)
* **Booking System:** Users book parcels by source/destination, weight, and priority (Overnight, 2-Day, Normal).
* **Live Tracking:** Real-time visual progress bars showing the exact location of a parcel.
* **Undo/Cancellation:** O(1) time complexity cancellation of bookings before dispatch.
* **Smart Scheduling:** Internal engine processes days and hours, handling dispatches automatically.

### 🛡️ Admin Dashboard (`admin.cpp`)
* **Live Hub Monitoring:** Monitor specific traffic for any of the 8 major cities.
* **Traffic Visualization:** View outgoing vehicles, load status, and arrival progress.
* **Route Blocking:** Simulate delays by blocking routes, forcing the system to find alternative paths.
* **Context-Aware Logs:** A live feed highlighting critical events (lost parcels) with color-coded alerts.

## 🏗️ Data Structures & Algorithms (The "DSA" Core)

To demonstrate memory management and algorithm optimization, several components were built from scratch:

* **Custom Hash Table (`ParcelHashTable`):**
    * Uses **Chaining (via Linked Lists)** for collision handling.
    * Provides **O(1)** average time complexity for parcel lookups.
* **Dijkstra’s Algorithm:**
    * Finds the shortest delivery path between cities.
    * Integrates a custom **Min-Heap** to optimize priority queue operations.
* **Custom Template Vector:**
    * A manually implemented dynamic array to handle TripInfo and logs without using `std::vector`.
    * Includes deep copy constructors and assignment operators for safe memory management.

## ⚙️ Technical Implementation

* **Multithreading:** Uses `std::thread` and `std::mutex` to run the simulation engine and user interface simultaneously.
* **Inter-Process Communication:** The two applications communicate via shared files (`system_state.txt` and `notifications.txt`).
* **Visuals:** Uses ANSI color codes and math-based progress bars for a professional terminal UI.

## 🛠️ How to Run

1. **Compile the Client:** `g++ source.cpp -o client -lpthread`
2. **Compile the Admin:** `g++ admin.cpp -o admin`
3. Run both executables in separate terminal windows.
