# 🚨 Emergency Alert Triggering System

This C++-based simulation provides an emergency alert triggering system using **hash tables** and **priority queues**. The system prioritizes emergencies based on severity and proximity, providing life-saving precautionary guidelines for different emergency situations like fire, road accidents, heart strokes, and more.

---

## 📌 Features

- 📊 Efficient data storage using **hash tables**
- ⚡ Prioritized emergency handling with **priority queues**
- 🔔 Handles various emergency types:
  - Fire Accidents
  - Road Accidents
  - Heart Strokes
  - Pregnancy Alerts
  - Child Abuse
- 🔄 Allows **insertion**, **deletion**, and **searching** of emergencies
- 📝 Provides **precautionary actions** for each emergency type
- 📁 Logs all emergencies to a file `logs/emergency_log.txt`

---

## 🧱 Data Structures Used

| Data Structure | Purpose |
|----------------|---------|
| **Hash Table** | Maps emergency numbers to a list of incident entries, allowing O(1) average-case access for quick updates. |
| **Priority Queue** | Ensures the most urgent emergencies (highest severity and nearest) are handled first. |

---

## 📖 Emergency Codes

| Number | Emergency Name    | Threshold Value |
|--------|-------------------|-----------------|
| 0      | Fire Accident     | 300             |
| 1      | Road Accident     | 200             |
| 2      | Heart Stroke      | 100             |
| 3      | Pregnancy Alert   | 50              |
| 4      | Child Abuse       | 25              |

---

## 🚀 How to Run

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/EmergencyAlertSystem.git
   cd EmergencyAlertSystem


2. **Compile the C++ code**:
   Use the `g++` command or a Makefile to compile the code:

   ```bash
   g++ -o EmergencySystem src/EmergencyAlertSystem.cpp
   ```

   Alternatively, you can use the Makefile to automatically compile:

   ```bash
   make
   ```

3. **Run the program**:

   ```bash
   ./EmergencySystem
   ```

4. **Follow the interactive prompts** to add, delete, and search for emergency incidents.

---

## 🧪 Sample Output

```text
Enter the number which corresponds to your emergency.
> 0
Enter severity value.
> 400
Enter distance.
> 2

Priority Queue:
Emergency Number: 0, Severity: 400, Distance: 2
Precautions:
- Evacuate the area immediately and call emergency services.
- Use fire extinguishers if safe to do so and if trained.
- Stay low to the ground if smoke is present.
- Call : 101
```

---

## 📁 Logs

The program logs all emergency reports to the following file:

```
logs/emergency_log.txt
```

This log file stores all emergency entries, including timestamps, severity values, distances, and precautionary actions, which can be used for auditing, statistics, or training purposes.

---

## 🔐 Future Enhancements

Here are some possible enhancements for future versions:

* 🌐 **GUI Interface**: Create a user-friendly graphical interface for easier interaction.
* 📍 **GPS Tracking**: Integrate real-time location data to dynamically prioritize emergencies based on proximity.
* 📲 **SMS/Email Notifications**: Enable automated notifications to relevant personnel during emergencies.
* 👤 **User Authentication**: Implement user and admin logins for restricted access and auditing.
* 🎯 **Emergency Drills**: Create simulated emergency drills for training and preparedness.

---

## 📋 File Structure

```
EmergencyAlertSystem/
│
├── src/
│   └── EmergencyAlertSystem.cpp    # Main C++ code file
│
├── logs/
│   └── emergency_log.txt          # Log file for all emergencies
│
├── README.md                      # Project documentation
│
├── Makefile                       # Optional: For easier compilation
```

---

## 🤝 Contributing

Contributions are welcome! If you'd like to contribute, feel free to fork this repository, make changes, and submit a pull request. If you have any feature requests or bug reports, please open an issue.

---

## 📜 License

This project is licensed under the MIT License.

```

