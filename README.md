# Expressway Toll System CLI

A lightweight and efficient **C# console application** designed to simulate and manage an expressway toll collection system. The system handles vehicle entry and exit tracking, toll fare calculations, receipt generation, transaction records, and toll-rate management.

---

## 📌 Features

* **Vehicle Entry & Exit Tracking**
  Register vehicles entering and exiting toll gates at different plaza locations.

* **Dynamic Toll Calculation**
  Automatically calculate toll fees based on:

  * Vehicle classification
  * Distance traveled
  * Applicable toll rate

* **Receipt Generation**
  Generate itemized transaction receipts for motorists when they exit the expressway.

* **Transaction Logging**
  Store and view historical vehicle entry/exit transactions and revenue information.

* **Revenue Reports**
  View transaction history and daily revenue information.

* **Toll Rate Management**
  Configure toll rates according to vehicle classes and distance traveled.

* **Gate Management**
  Manage toll gates/plazas and their respective distances.

---

## 🛠️ Project Structure

```text
ExpresswayTollSystemCLI/
│
├── ExpresswayTollSystemCLI/
│   │
│   ├── Models/
│   │   ├── Vehicle.cs
│   │   │   └── Vehicle properties and class definitions
│   │   │
│   │   ├── TollGate.cs
│   │   │   └── Toll gate/plaza details and distances
│   │   │
│   │   └── Transaction.cs
│   │       └── Transaction and receipt data models
│   │
│   ├── Services/
│   │   ├── TollCalculator.cs
│   │   │   └── Distance and fare calculation logic
│   │   │
│   │   ├── EntryExitManager.cs
│   │   │   └── Vehicle entry and exit management
│   │   │
│   │   └── StorageService.cs
│   │       └── Transaction and history persistence
│   │
│   ├── Program.cs
│   │   └── Main entry point and CLI menu interface
│   │
│   └── ExpresswayTollSystemCLI.csproj
│
└── ExpresswayTollSystemCLI.sln
    └── Visual Studio Solution File
```

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ExpresswayTollSystemCLI.git
```

Navigate to the project directory:

```bash
cd ExpresswayTollSystemCLI
```

### 2. Restore Dependencies and Build

```bash
dotnet build
```

### 3. Run the Application

```bash
dotnet run --project ExpresswayTollSystemCLI
```

---

## 💻 Usage

When you start the application, you will be presented with the following command-line menu:

```text
==================================================
           EXPRESSWAY TOLL SYSTEM CLI
==================================================
1. Register Vehicle Entry
2. Process Vehicle Exit & Charge Toll
3. View Active Vehicles in System
4. View Transaction History & Revenue Reports
5. Configure Toll Rates
6. Exit
--------------------------------------------------
Select an option (1-6):
```

---

## 🔄 Example Workflow

### Step 1 – Register Vehicle Entry

Select **Option 1** to register a vehicle entering the expressway.

For example:

```text
Vehicle Number: WP ABC-1234
Vehicle Class: Class 1
Entry Gate: Gate A
Entry Distance: 0 km
```

### Step 2 – Process Vehicle Exit

When the vehicle exits the expressway, select **Option 2**.

For example:

```text
Exit Gate: Gate D
Exit Distance: 45 km
```

### Step 3 – Calculate Toll

The system calculates the distance traveled:

```text
Distance Traveled = Exit Distance - Entry Distance

Distance Traveled = 45 km - 0 km

Distance Traveled = 45 km
```

The applicable toll rate is then calculated according to the vehicle class.

### Step 4 – Generate Receipt

The system records the transaction and displays a receipt containing details such as:

```text
==================================================
              EXPRESSWAY TOLL RECEIPT
==================================================
Vehicle Number : WP ABC-1234
Vehicle Class  : Class 1
Entry Gate     : Gate A
Exit Gate      : Gate D
Distance       : 45 km
Date & Time    : 2026-10-12 20:30
Payment Method : Cash
Toll Amount    : Rs. XXXX.XX
==================================================
```

---

## ⚙️ Configuration & Toll Rates

Toll rates and vehicle-class multipliers can be configured through the application's toll calculation logic.

The main calculation logic is located in:

```text
Services/TollCalculator.cs
```

An optional `appsettings.json` configuration file can also be used if implemented.

### Vehicle Classes

| Vehicle Class | Description                     | Toll Rate Multiplier |
| ------------- | ------------------------------- | -------------------: |
| **Class 1**   | Motorcycles & Passenger Cars    |       1.0× Base Rate |
| **Class 2**   | SUVs, Vans & Light Trucks       |       1.5× Base Rate |
| **Class 3**   | Heavy Buses & Multi-Axle Trucks |       2.5× Base Rate |

### Toll Calculation

The general calculation is:

```text
Toll Amount = Distance Traveled × Base Rate × Vehicle Class Multiplier
```

For example:

```text
Distance = 45 km
Base Rate = Rs. 10/km
Vehicle Class = Class 2
Multiplier = 1.5

Toll Amount = 45 × 10 × 1.5
            = Rs. 675
```

---

## 🧩 Main Components

### Models

The `Models` folder contains the application's main data structures.

* **Vehicle.cs** – Stores vehicle information and vehicle classification.
* **TollGate.cs** – Stores toll gate/plaza information and distances.
* **Transaction.cs** – Stores transaction and receipt information.

### Services

The `Services` folder contains the application's core business logic.

* **TollCalculator.cs** – Calculates travel distance and toll charges.
* **EntryExitManager.cs** – Manages vehicle entry and exit operations.
* **StorageService.cs** – Handles transaction and historical data storage.

### Program.cs

`Program.cs` is the main entry point of the application. It provides the command-line interface and handles the main system menu.

---

## 🔧 Built With

| Technology              | Description                         |
| ----------------------- | ----------------------------------- |
| **C#**                  | Programming Language                |
| **.NET**                | Application Framework               |
| **Console Application** | User Interface                      |
| **Visual Studio**       | Development Environment             |
| **Visual Studio Code**  | Alternative Development Environment |

---

## 📋 System Requirements

Before running the application, make sure you have:

* .NET SDK installed
* Visual Studio or Visual Studio Code
* Windows, Linux, or macOS
* Git (if cloning from GitHub)

You can verify your .NET installation using:

```bash
dotnet --version
```

---

## 📁 Future Improvements

Possible future enhancements include:

* MySQL database integration
* Graphical User Interface (GUI)
* Online payment integration
* Automated daily/monthly reports
* Admin and user login system
* Multiple toll plaza support
* Advanced vehicle management
* PDF receipt generation
* Real-time revenue dashboard

---

## 📄 License

This project is licensed under the **MIT License**.

See the `LICENSE` file for more information.

---

# Login

| Username   | Password     | Role     |
|------------|--------------|----------|
| admin      | admin123     | Admin    |
| operator1  | operator123  | Operator |


## 👨‍💻 Project

**Expressway Toll System CLI**

A C#-based expressway toll management system developed for educational and demonstration purposes.
