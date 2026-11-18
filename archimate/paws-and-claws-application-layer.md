# Paws & Claws Pet Clinic – Application Layer


## 1. Business Description

Paws & Claws Pet Clinic is a veterinary clinic that provides health checkups, vaccinations, surgery and short-term boarding for domestic animals. Its customers are pet owners who bring their animals in for preventive care or treatment.

The clinic's main customer-facing service is booking and running a veterinary **appointment**: an owner requests a visit, front desk staff schedule it with an available veterinarian, the pet is examined and treated, and the visit is billed.

## 2. Information Systems Description

The clinic relies on three application components. The **Appointment Scheduling System** is the front-line system used by both front-desk staff and pet owners: staff use it through a **Front Desk UI**, and owners use it directly through a **Web Portal UI**. Internally it runs a **Process Appointment Booking** application process, supported by a **Manage Appointment Data** function, which together validate requests, check availability and keep each booking's **Appointment Record** up to date. The system exposes this behaviour as the **Appointment Scheduling Service**, consumed by the Pet Owner and by the Front Desk role.

The **Clinic EMR System** stores each pet's **Patient Medical History** and is used by veterinarians through a **Vet Console UI**. It exposes a **Medical Record Service** that serves the Front Desk role (for check-in) and the Veterinarian role (for examination and recording results). The **Billing System** is a smaller, back-office component: it is not exposed to customers directly, and simply reads the completed appointment to create and update the **Invoice Record** once a visit is finished.

The three systems are loosely coupled around the same business process rather than tightly integrated: the Appointment Scheduling System's data feeds into what the EMR and Billing systems act on, but each keeps its own data object (Appointment Record, Patient Medical History, Invoice Record) and is accessed through its own interface by the role that needs it.

## 3. Model Elements (Application Layer)

| Type | Elements |
|---|---|
| Application Components (3) | Appointment Scheduling System, Clinic EMR System, Billing System |
| Application Function (1) | Manage Appointment Data |
| Application Process (1) | Process Appointment Booking |
| Data Objects (3) | Appointment Record, Patient Medical History, Invoice Record |
| Application Services (2) | Appointment Scheduling Service, Medical Record Service |
| Application Interfaces (3) | Front Desk UI, Web Portal UI, Vet Console UI |

## 4. Key Relationships

- **Assignment:** Appointment Scheduling System → Manage Appointment Data, Process Appointment Booking, Front Desk UI, Web Portal UI; Clinic EMR System → Vet Console UI.
- **Realization:** Appointment Scheduling System realizes Appointment Scheduling Service; Clinic EMR System realizes Medical Record Service.
- **Triggering:** Process Appointment Booking triggers Manage Appointment Data.
- **Access:** Process Appointment Booking writes Appointment Record; Manage Appointment Data reads Appointment Record; Clinic EMR System reads/writes Patient Medical History; Billing System writes Invoice Record.
- **Serving:** Appointment Scheduling Service serves Pet Owner and Front Desk; Medical Record Service serves Front Desk and Veterinarian.

## 5. Submission Files

- `paws_and_claws_application_description.md` – this description
- `paws_and_claws_application_layer.archimate` – ArchiMate model (Business Layer from Lab 2, extended with the Application Layer; view: *Application Layer View*)
