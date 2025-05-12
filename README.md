Here's a new, detailed `README.md` file for your **Emergency Alert Triggering System** project:

---

# 🚨 Emergency Alert Triggering System

This project is a C++-based system that simulates an emergency alert triggering system using key data structures such as **hash tables** and **priority queues**. It is designed to log, prioritize, and respond to various emergencies like fire accidents, road accidents, and more.

## 📌 Features

* 📊 Uses a **hash table** for efficient data storage and retrieval.
* ⚡ Implements a **priority queue** to ensure high-severity, close-range emergencies are handled first.
* 🔔 Multiple emergency types handled: Fire, Road Accidents, Heart Strokes, Pregnancy Alerts, and Child Abuse.
* 🔄 Supports real-time **insertion, deletion, and searching** of emergency entries.
* 🧠 Dynamically calculates emergency priorities based on severity and proximity.
* 📝 Detailed **precaution guidelines** for each emergency type.
* 📁 Logs emergencies to a text file for persistent record-keeping.

## 🧱 Data Structures Used

* **Hash Table**: Maps emergency numbers to a list of incidents using the division method (`e_num % 5`).
* **Priority Queue**: Ranks emergency reports by:

  1. Emergency number (type-based priority),
  2. Severity (higher is more urgent),
  3. Distance (closer is more urgent).

## 📖 Emergency Codes

| Number | Emergency Name  | Threshold Value |
| ------ | --------------- | --------------- |
| 0      | Fire Accident   | 300             |
| 1      | Road Accident   | 200             |
| 2      | Heart Stroke    | 100             |
| 3      | Pregnancy Alert | 50              |
| 4      | Child Abuse     | 25              |

## 🚀 How to Run

1. Compile the program using a C++ compiler:

   ```bash
   g++ -o EmergencySystem main.cpp
   ```

2. Run the compiled program:

   ```bash
   ./EmergencySystem
   ```

3. Follow the on-screen prompts to:

   * Add new emergencies,
   * Search or delete incidents,
   * View prioritized emergency responses.

## 📋 Example Interaction

```
Enter the number which corresponds to your emergency.
> 0
Enter severity value.
> 400
Enter distance.
> 2
...
Priority Queue:
Emergency Number: 0, Severity: 400, Distance: 2
Precautions:
- Evacuate the area immediately and call emergency services.
- Use fire extinguishers if safe to do so and if trained.
- Stay low to the ground if smoke is present.
- Call : 101
```

## 🔐 Future Enhancements

* GUI-based interface for easier use
* Real-time location tracking with GPS integration
* SMS/Email notification support
* Admin/User login system
* Emergency drill simulations

## 📁 Output

The system outputs a log file:

```
emergency_log.txt
```

This contains a timestamped list of all handled emergencies for review and analysis.

## 🤝 Contributing

Feel free to fork the repository and submit pull requests to add new features or fix bugs.

---
