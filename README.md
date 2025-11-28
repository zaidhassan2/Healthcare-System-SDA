# Healthcare-System-SDA
UML-based design and architecture documentation for a Health Care Management System, including class, package, deployment, component, and sequence diagrams.
Topics/Tags:
uml, software-architecture, healthcare-system, sda, class-diagram, sequence-diagram, deployment-diagram.
# 🏥 Healthcare-System-SDA

## Software Design and Architecture Documentation (Phase 2)

[cite_start]This repository contains the design and architectural documentation for a proposed **Health Care System** [cite: 2][cite_start], developed as a project for the Software Design and Architecture (SDA) course.

The project uses the Unified Modeling Language (UML) to visualize the system structure, components, deployment environment, and key processes.

### 👥 Team Members
* [cite_start]Aiman Ijaz (23F-3083) [cite: 3]
* [cite_start]Muhammad Zaid Hassan (23F-3031) [cite: 3]
* [cite_start]Muhammad Faheem Akhtar (23F-3066) [cite: 4]

---

## 📐 Design Diagrams

The design phase utilizes several key UML diagrams to fully define the system architecture and behavior.

### 1. Class Diagram
[cite_start]This diagram outlines the core entities (classes) and their relationships within the system[cite: 12].
* [cite_start]**Key Classes:** User, Doctor [cite: 6][cite_start], Patient [cite: 25][cite_start], Admin [cite: 29][cite_start], Appiontment [cite: 19][cite_start], Notifications [cite: 32][cite_start], ScheduleDetails [cite: 11][cite_start], MessageDetails[cite: 36].
* **Functionality Examples:**
    * [cite_start]**User** can log in, set/reset passwords[cite: 147, 154].
    * [cite_start]**Doctor** has schedule details and appointment management[cite: 9, 11].
    * [cite_start]**Patient** has appointment and message details[cite: 19, 34].

### 2. Package Diagram
[cite_start]This diagram organizes the system's core functionality into logical groups (packages) and shows their dependencies[cite: 43].
* **Key Packages:**
    * [cite_start]**Staff Management:** Contains Doctor [cite: 47, 49, 51] [cite_start]and Admin [cite: 48, 50] [cite_start]classes[cite: 45].
    * [cite_start]**Appointment System:** Manages the Appointment process[cite: 54].
    * [cite_start]**Patient Management:** Includes Patient [cite: 59, 60][cite_start], Medical Record [cite: 61][cite_start], and Prescription[cite: 62].
    * [cite_start]**Billing System:** Handles Billing[cite: 42].
* [cite_start]**Relationships:** Admin manages both Patient and Doctor[cite: 41, 46]. [cite_start]Patient books an Appointment [cite: 52] [cite_start]and receives Billing[cite: 39]. [cite_start]The Appointment results in a Medical Record[cite: 57].

### 3. Deployment Diagram
[cite_start]This diagram maps the software components onto the hardware and infrastructure where they will run[cite: 67].
* **Core Nodes:**
    * [cite_start]**Main Hospital Server:** Hosts the Power Supply System [cite: 69][cite_start], Security System [cite: 76][cite_start], and Mobile Communication[cite: 77].
    * [cite_start]**Patient Database:** Stores Patient [cite: 92][cite_start], Medical Record [cite: 93][cite_start], and Prescription[cite: 94].
    * [cite_start]**Billing System, Appointment Server, Staff Management System**[cite: 89, 90, 91].
* [cite_start]**Interfaces:** The User Interface [cite: 79] [cite_start]is secured [cite: 78] [cite_start]and allows access to billing [cite: 82] [cite_start]and scheduling[cite: 83]. It connects to the Appointment Server and Database systems.

### 4. Component Diagram
[cite_start]This diagram shows the system's structure as a set of interacting components[cite: 101].
* [cite_start]**Core Components:** Admin [cite: 105][cite_start], Doctor [cite: 102][cite_start], Patient [cite: 103][cite_start], Staff [cite: 106][cite_start], Lab technician [cite: 108][cite_start], Appointment [cite: 104][cite_start], Prescription [cite: 107][cite_start], and Database[cite: 109].

### 5. Sequence Diagrams

Sequence diagrams illustrate the time-ordered interactions between objects to achieve a specific functionality.

#### 5.1. Appointment Booking Process
* [cite_start]**Patient** initiates the process by searching for a Doctor (`searchDoctor()`)[cite: 113, 115].
* [cite_start]An **Alternative (alt)** flow determines if the Doctor is Available [cite: 116, 117] [cite_start]or Unavailable[cite: 124].
    * [cite_start]**If Available:** Patient views availability (`viewAvailability()`) [cite: 118][cite_start], books an appointment (`bookAppointment()`) [cite: 119][cite_start], and receives a confirmation (`sendConfiramtion()`)[cite: 123]. [cite_start]The Doctor confirms availability with the Appointment system (`confirmAvailability()`)[cite: 122].
    * [cite_start]**If Unavailable:** Patient receives an unavailable notification (`sendUnavilableNotofication()`)[cite: 125].

#### 5.2. Admin Notification
* [cite_start]**Admin** adds a notification (`addNotification()`) [cite: 127, 129] [cite_start]to the **Notification** system[cite: 130].
* [cite_start]The system then iterates **[For Each User]** [cite: 132] [cite_start]to send the notification (`sendNotification()`)[cite: 133].

#### 5.3. User Login Process
* [cite_start]**User** attempts to log in (`loginUser()`)[cite: 141, 147].
* An **Alternative (alt)** flow handles the result:
    * [cite_start]**[Success]:** Redirects to the dashboard (`redirectToDashboard()`)[cite: 143, 144].
    * [cite_start]**Failure:** Displays an error message (`showErrorMessage`)[cite: 145, 146].

#### 5.4. Password Reset Process
* [cite_start]**User** attempts to set a new password (`setPassword()`)[cite: 149, 154].
* [cite_start]An **Alternative (alt)** flow handles sending the reset email **[Send Pasword reset Email]** [cite: 151, 152] [cite_start]using `sendPaswordResetEmail()`[cite: 153].
