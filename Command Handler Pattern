The Command Handler Pattern is based on the principle of decoupling the sender (who issues a command) from the receiver (who executes the command). It allows commands to be processed in a structured and scalable way.

Key Concepts:
🔹 Command – A simple DTO (Data Transfer Object) that represents an action to be executed.
🔹 Command Handler – Processes the command and applies business logic.
🔹 Dispatcher (Mediator) – Routes the command to the appropriate handler (optional).
🔹 Domain (Business Logic Layer) – Where business rules are enforced

2. How the Command Handler Pattern Works
Step-by-Step Execution:
1️⃣ A Client issues a Command
The command represents an intent (e.g., CreateOrderCommand).
2️⃣ A Dispatcher or Mediator (optional) sends the Command to the appropriate Handler
This prevents tight coupling between components.
3️⃣ The Command Handler processes the Command
It applies business rules and interacts with the domain.
4️⃣ Results are saved or events are published
The handler may update a database or trigger an event.

![Image](https://github.com/user-attachments/assets/262e7aa3-c706-4e75-b9b8-4cec9f15d4b3)
