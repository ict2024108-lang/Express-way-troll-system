# 🚗 Expressway Toll System CLI 🛣️

A lightweight and efficient **C# console application** designed to simulate and manage an expressway toll collection system. The system handles **vehicle entry and exit tracking, toll fare calculations, receipt generation, transaction records, and toll-rate management**.

---

## 📌 Features

* 🚘 **Vehicle Entry & Exit Tracking**
  Register vehicles entering and exiting toll gates at different plaza locations.

* 💰 **Dynamic Toll Calculation**
  Automatically calculate toll fees based on:

  * 🚗 Vehicle classification
  * 📏 Distance traveled
  * 💵 Applicable toll rate

* 🧾 **Receipt Generation**
  Generate itemized transaction receipts for motorists when they exit the expressway.

* 📝 **Transaction Logging**
  Store and view historical vehicle entry/exit transactions and revenue information.

* 📊 **Revenue Reports**
  View transaction history and daily revenue information.

* ⚙️ **Toll Rate Management**
  Configure toll rates according to vehicle classes and distance traveled.

* 🏁 **Gate Management**
  Manage toll gates/plazas and their respective distances.

---

## 🛠️ Project Structure

```text
ExpresswayTollSystemCLI/
│
├── ExpresswayTollSystemCLI/
│   │
│   ├── 📂 Models/
│   │   ├── 🚗 Vehicle.cs
│   │   ├── 🏁 TollGate.cs
│   │   └── 🧾 Transaction.cs
│   │
│   ├── 📂 Services/
│   │   ├── 💰 TollCalculator.cs
│   │   ├── 🚦 EntryExitManager.cs
│   │   └── 💾 StorageService.cs
│   │
│   ├── ▶️ Program.cs
│   └── 📄 ExpresswayTollSystemCLI.csproj
│
└── 📦 ExpresswayTollSystemCLI.sln
```

---

## 🚀 Installation & Setup

### 1️⃣ 📥 Clone the Repository

```bash
git clone https://github.com/your-username/ExpresswayTollSystemCLI.git
```

```bash
cd ExpresswayTollSystemCLI
```

### 2️⃣ 🔄 Restore Dependencies & Build

```bash
dotnet build
```

### 3️⃣ ▶️ Run the Application

```bash
dotnet run --project ExpresswayTollSystemCLI
```

---

## 💻 Usage

When you start the application, you will be presented with the **Command-Line Interface (CLI)** login screen.

---

## 🔐 Login Credentials

Use the following credentials to access the system:

| 👤 Username | 🔑 Password   | 🛡️ Role        |
| ----------- | ------------- | --------------- |
| `admin`     | `admin123`    | 👑 **Admin**    |
| `operator1` | `operator123` | 👷 **Operator** |

### 👑 Admin

The **Admin** role provides access to administrative functions such as:

* ⚙️ Configure toll rates
* 🏁 Manage toll gates
* 📊 View system reports
* 📝 View transaction history
* 🚗 Manage system settings

### 👷 Operator

The **Operator** role is intended for day-to-day toll operations, such as:

* 🚘 Register vehicle entry
* 🏁 Process vehicle exit
* 💰 Calculate toll charges
* 🧾 Generate receipts
* 🚦 View active vehicles

> ⚠️ **Note:** These credentials are provided for demonstration/testing purposes. For production use, passwords should be stored securely and never committed directly to source code.

---

## 🖥️ Main Menu

After successfully logging in, the system displays the following menu:

```text
==================================================
        🚗 EXPRESSWAY TOLL SYSTEM CLI 🛣️
==================================================
1. 🚘 Register Vehicle Entry
2. 💰 Process Vehicle Exit & Charge Toll
3. 🚦 View Active Vehicles in System
4. 📊 View Transaction History & Revenue Reports
5. ⚙️ Configure Toll Rates
6. 🚪 Exit
--------------------------------------------------
Select an option (1-6):
```

---

## 🔄 Example Workflow

### 1️⃣ 🚘 Register Vehicle Entry

Select **Option 1** to register a vehicle entering the expressway.

```text
🚗 Vehicle Number : WP ABC-1234
🏷️ Vehicle Class  : Class 1
🏁 Entry Gate     : Gate A
📏 Entry Distance : 0 km
```

### 2️⃣ 🏁 Process Vehicle Exit

When the vehicle exits the expressway, select **Option 2**.

```text
🏁 Exit Gate      : Gate D
📏 Exit Distance  : 45 km
```

### 3️⃣ 📏 Calculate Toll

```text
Distance Traveled = Exit Distance - Entry Distance

Distance Traveled = 45 km - 0 km

📏 Distance Traveled = 45 km
```

### 4️⃣ 🧾 Generate Receipt

```text
==================================================
          🧾 EXPRESSWAY TOLL RECEIPT
==================================================
🚗 Vehicle Number : WP ABC-1234
🏷️ Vehicle Class  : Class 1
🏁 Entry Gate     : Gate A
🏁 Exit Gate      : Gate D
📏 Distance       : 45 km
📅 Date & Time    : 2026-10-12 20:30
💳 Payment Method : Cash
💰 Toll Amount    : Rs. XXXX.XX
==================================================
              ✅ THANK YOU!
==================================================
```

---

## ⚙️ Configuration & Toll Rates

Toll rates and vehicle-class multipliers can be configured through the application's toll calculation logic.

📂 Main calculation logic:

```text
Services/TollCalculator.cs
```

### 🚘 Vehicle Classes

| 🏷️ Vehicle Class | 🚗 Description                     | 💰 Toll Rate Multiplier |
| ----------------- | ---------------------------------- | ----------------------: |
| **Class 1**       | 🏍️ Motorcycles & Passenger Cars   |      **1.0× Base Rate** |
| **Class 2**       | 🚙 SUVs, Vans & Light Trucks       |      **1.5× Base Rate** |
| **Class 3**       | 🚛 Heavy Buses & Multi-Axle Trucks |      **2.5× Base Rate** |

### 🧮 Toll Calculation

```text
💰 Toll Amount = Distance Traveled × Base Rate × Vehicle Class Multiplier
```

Example:

```text
📏 Distance       = 45 km
💵 Base Rate      = Rs. 10/km
🚙 Vehicle Class  = Class 2
✖️ Multiplier     = 1.5

💰 Toll Amount = 45 × 10 × 1.5

✅ Toll Amount = Rs. 675
```

---

## 🧩 Main Components

### 📦 Models

* 🚗 **Vehicle.cs** – Stores vehicle information and vehicle classification.
* 🏁 **TollGate.cs** – Stores toll gate/plaza information and distances.
* 🧾 **Transaction.cs** – Stores transaction and receipt information.

### ⚙️ Services

* 💰 **TollCalculator.cs** – Calculates travel distance and toll charges.
* 🚦 **EntryExitManager.cs** – Manages vehicle entry and exit operations.
* 💾 **StorageService.cs** – Handles transaction and historical data storage.

### ▶️ Program.cs

`Program.cs` is the main entry point of the application. It provides the **command-line interface** and handles the main system menu.

---

## 🔧 Built With

| 💻 Technology              | 📝 Description                      |
| -------------------------- | ----------------------------------- |
| 🔷 **C#**                  | Programming Language                |
| 🟣 **.NET**                | Application Framework               |
| ⌨️ **Console Application** | User Interface                      |
| 🟦 **Visual Studio**       | Development Environment             |
| 🖥️ **Visual Studio Code** | Alternative Development Environment |

---

## 📋 System Requirements

* 🟣 **.NET SDK** installed
* 🟦 **Visual Studio** or **Visual Studio Code**
* 🪟 Windows, 🐧 Linux, or 🍎 macOS
* 🌐 **Git** for cloning the repository

Check your .NET installation:

```bash
dotnet --version
```

---

## 🔮 Future Improvements

* 🗄️ MySQL database integration
* 🖥️ Graphical User Interface (GUI)
* 💳 Online payment integration
* 📊 Automated daily/monthly reports
* 🔐 Advanced authentication and authorization
* 🏁 Multiple toll plaza support
* 🚗 Advanced vehicle management
* 📄 PDF receipt generation
* 📈 Real-time revenue dashboard

---

## 📄 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.

---

## 👨‍💻 Project

### 🚗 Expressway Toll System CLI 🛣️

A **C#-based expressway toll management system** developed for educational and demonstration purposes.

---

### ⭐ If you like this project, don't forget to give it a Star! ⭐

**Made with ❤️ using C# and .NET**
