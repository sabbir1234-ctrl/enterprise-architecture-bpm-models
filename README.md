# Enterprise Architecture and Business Process Models

Models from my Software Engineering coursework at Vilnius University Šiauliai Academy (autumn 2026).
They cover **ArchiMate** enterprise architecture (business, application and technology layers), **BPMN 2.0** executable processes and **DMN** decision tables.

![ArchiMate](https://img.shields.io/badge/ArchiMate-3.x-blue) ![BPMN](https://img.shields.io/badge/BPMN-2.0-orange) ![DMN](https://img.shields.io/badge/DMN-1.3-green) ![Camunda](https://img.shields.io/badge/Camunda-8-black)

## ArchiMate models — [`archimate/`](archimate)

| Model | Layer / focus |
|-------|---------------|
| City Library Business Architecture | Business layer: actors, roles, processes, services |
| Coffee Shop — Process a Cafe Order | Business process with its supporting services |
| Paws & Claws Pet Clinic — Application Layer | Application components, services and data objects ([write-up](archimate/paws-and-claws-application-layer.md)) |
| Clinic Technology Layer | Nodes, system software, networks and deployment |
| Pet Clinic — Views and Stakeholders | Viewpoints for different stakeholders, combining all layers |

Open the `.archimate` files with [Archi](https://www.archimatetool.com/).

## BPMN processes — [`bpmn/`](bpmn)

| Process | Description |
|---------|-------------|
| Paws & Claws — Handle Appointment | Booking flow that calls the slot-availability decision |
| Riverside Library — Borrow a Book | Automated loan process with user tasks, gateways and DMN-based approval |
| Riverside Library — Borrow a Book (Azure) | The same process, extended with a REST connector that stores loan receipts through an Azure Function |

## DMN decisions — [`dmn/`](dmn)

| Decision | Description |
|----------|-------------|
| Paws & Claws — Slot Availability | Decides whether an appointment slot can be booked |
| Riverside Library — Loan Approval | Rules for approving, reserving or rejecting a book loan |

Open the BPMN and DMN files with [Camunda Modeler](https://camunda.com/download/modeler/).

## Related

The Azure Function used by the Borrow-a-Book process is in
[riverside-library-loan-function](https://github.com/sabbir1234-ctrl/riverside-library-loan-function).
