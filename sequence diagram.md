# Sequence Diagram

A sequence diagram is a type of interaction diagram in UML (Unified Modeling Language) that illustrates the flow of messages and interactions between different objects or components within a system over time. It shows how various elements in a system collaborate to achieve a specific functionality or use case.

---

## SD Uses

- **Understanding System Behavior**: Sequence diagrams provide a visual representation of how different components or objects within a system interact and the flow of messages between them. this aids in understanding the overall behavior of the system.
- **Communication**: As a visual communication tool, sequence diagrams facilitate discussions among stakeholders by presenting complex interactions in a clear and accessible format. They are useful for conveying ideas between technical and non-technical team members.
- **Design and Documentation**: During the design phase, sequence diagrams serve as documentation for the dynamic aspects of a system. They offer a blueprint that developers can follow to implement communication patterns between objects or components.
- **Identifying Issues and Improvements**: developers use sequence diagrams to identify potential issues or bottlenecks in a system's communication flow. This visual representation helps optimize and improve system performance.
- **Testing and Validation**: Sequence diagrams are foundational for designing test cases, especially for scenarios involving interactions between different components. They aid in validating that the system behaves as expected in various use cases.
- **System Maintenance**: During system maintenance or updates, sequence diagrams help developers understand existing interactions between components. This understanding is crucial for identifying potential impacts when making changes to the system.
- **Prototyping and Planning**: In the early stages of a project, sequence diagrams aid in prototyping and planning the communication flow between different modules or subsystems. They contribute to the initial design decisions and architecture.
- **Training and Onboarding**: sequence diagrams serve as valuable training tools for new team members or developers. They provide an overview of the system's behavior, making it easier for individuals to understand the project without delving into the entire codebase.

---

## Creating and Connecting Participants

🔗 Mermaid.js reference link:
[Sequence diagrams](https://docs.mermaidchart.com/mermaid-oss/syntax/sequenceDiagram.html)

````
```mermaid
sequenceDiagram
    Actor Manager
    participant Alice as sup1
    participant James as sup2
    participant Bob as sup3

    Manager->>Alice: Call a meeting,now
    Alice->>James: Hi James, It's Alice
    James->>Alice: Hello Alice
    Alice->>Bob: Are you there Bob

```
````

```mermaid
sequenceDiagram
    Actor Manager
    participant Alice as sup1
    participant James as sup2
    participant Bob as sup3

    Manager->>Alice: Call a meeting,now
    Alice->>James: Hi James, It's Alice
    James->>Alice: Hello Alice
    Alice->>Bob: Are you there Bob

```

---

## Working with messages, Notes and comments

````
```mermaid
sequenceDiagram
    Actor Manager
    Note right of Alice: text right
    Note left of Alice: text left
    Note over Alice: text over
    Note over James, Bob: text over<br/>James and Bob

    Manager->>Alice: Call a meeting,now
    Alice->>James: Hi James, It's Alice
    % return message
    James--)Alice: Hello Alice
    Alice--xBob: Are you there Bob

    % Note Comment
    % Note <position> of <object(s)>: <description>
    % message Symbols
    % - (solid line)
    % -- (dotted line)
    % > (no arrow)
    % >> (Filled Arrow - sync)
    % ) (stick arrow - async)

```
````

```mermaid
sequenceDiagram
    Actor Manager
    Note right of Alice: text right
    Note left of Alice: text left
    Note over Alice: text over
    Note over James, Bob: text over<br/>James and Bob

    Manager->>Alice: Call a meeting,now
    Alice->>James: Hi James, It's Alice
    % return message
    James--)Alice: Hello Alice
    Alice--xBob: Are you there Bob

    % Note Comment
    % Note <position> of <object(s)>: <description>
    % message Symbols
    % - (solid line)
    % -- (dotted line)
    % > (no arrow)
    % >> (Filled Arrow - sync)
    % ) (stick arrow - async)

```

---

## Sequence Objects Advanced

````
```mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    Bob->>Alice: Fine, thank you. And you?
    create participant Carl
    Alice->>Carl: Hi Carl, what's up?
    Carl--)Alice: I am fine Alice
    create actor D as Donald
    Carl->>D: Hi!
    destroy Carl
    Alice-xCarl: Bye bye Carl
    D--)Bob: Great Job Bob!
    destroy Bob
    Bob--xAlice: Have a nice day!

```
````

```mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    Bob->>Alice: Fine, thank you. And you?
    create participant Carl
    Alice->>Carl: Hi Carl, what's up?
    Carl--)Alice: I am fine Alice
    create actor D as Donald
    Carl->>D: Hi!
    destroy Carl
    Alice-xCarl: Bye bye Carl
    D--)Bob: Great Job Bob!
    destroy Bob
    Bob--xAlice: Have a nice day!


```

---

## Activation Box

````
```mermaid
sequenceDiagram
    Server->>Database: Give no data
    activate Database
    Database-->>Server: here you go
    deactivate Database

```
````

```mermaid
sequenceDiagram
    Server->>Database: Give no data
    activate Database
    Database-->>Server: here you go
    deactivate Database

```

````
```mermaid
sequenceDiagram
    participant User
    participant App as "Shopping App"
    participant Gateway as "Payment"
    participant Bank

    User->>+App: Select Item and Checkout
    App->>+Gateway: Initiate payment Request
    Gateway->>+Bank: Process Payment
    Bank-->>-Gateway: Payment Approved
    Gateway-->>-App: Payment Success
    App-->>-User: Order Confirmed
```
````

```mermaid
sequenceDiagram
    participant User
    participant App as "Shopping App"
    participant Gateway as "Payment"
    participant Bank

    User->>+App: Select Item and Checkout
    App->>+Gateway: Initiate payment Request
    Gateway->>+Bank: Process Payment
    Bank-->>-Gateway: Payment Approved
    Gateway-->>-App: Payment Success
    App-->>-User: Order Confirmed
```

---

## Alternative Frame 1

(alt..else..end, opt..end)

````
```mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick?
        Bob->>Alice: Not so good
    else not sick
        Bob->>Alice: Feeling like a daisy
    end

    opt other response
        Bob->>Alice: Thanks for asking
    end

```
````

```mermaid
sequenceDiagram
    Alice->>Bob: Hello Bob, how are you?
    alt is sick?
        Bob->>Alice: Not so good
    else not sick
        Bob->>Alice: Feeling like a daisy
    end

    opt other response
        Bob->>Alice: Thanks for asking
    end

```

---

## Exercise (Actors, participants, Messages, Alt)

(Actor, participant, Activation Box, Alt)

````
```mermaid
sequenceDiagram
    actor User as "End user"
    participant App as "Application"
    participant Server as "Server"
    participant DB as "Database"

    User->>App: Request Data
    activate App

    App->>Server: fetch Data
    activate Server
    alt Data Exists?
        Server->>DB: Query Database
        activate DB

        DB--)Server: Return Data
        deactivate DB
        Server--)App: return Data
    else Data Does Not Exist
        Server--xApp:Terminate (Data not Found)

    end

    deactivate Server

    App--)User: Display Data

    deactivate App

```
````

```mermaid
sequenceDiagram
    actor User as "End user"
    participant App as "Application"
    participant Server as "Server"
    participant DB as "Database"

    User->>App: Request Data
    activate App

    App->>Server: fetch Data
    activate Server
    alt Data Exists?
        Server->>DB: Query Database
        activate DB

        DB--)Server: Return Data
        deactivate DB
        Server--)App: return Data
    else Data Does Not Exist
        Server--xApp:Terminate (Data not Found)

    end

    deactivate Server

    App--)User: Display Data

    deactivate App

```

---

## Alternative frame 2

(Parallel communication)

````
```mermaid
sequenceDiagram
    par Alice to Bob
        Alice->>Bob: Hello Guys!
    and Alice to John
        Alice->>John: Hello Guys!
        par John to Charlie
            John->>Charlie: Can we go!
        and John to Diana
            John->>Diana: Can we go!
        and John to Jane
            John->>Jane: Can we go!
        end
    end
    Bob--)Alice: Hi Alice!
    John--)Alice: Hi Alice!

```
````

```mermaid
sequenceDiagram
    par Alice to Bob
        Alice->>Bob: Hello Guys!
    and Alice to John
        Alice->>John: Hello Guys!
        par John to Charlie
            John->>Charlie: Can we go!
        and John to Diana
            John->>Diana: Can we go!
        and John to Jane
            John->>Jane: Can we go!
        end
    end
    Bob--)Alice: Hi Alice!
    John--)Alice: Hi Alice!

```

---

## Alternative Frame 3

(Critical Region)

````
```mermaid
sequenceDiagram
    critical Establish connection to DB
        Service-->DB: Connect

    option Network Timeout
        Service-->Service: Log error

    option Credentials rejected
        Service-->Service: Log different error
    end
```
````

```mermaid
sequenceDiagram
    critical Establish connection to DB
        Service-->DB: Connect

    option Network Timeout
        Service-->Service: Log error

    option Credentials rejected
        Service-->Service: Log different error
    end
```

---

## More on Frames

(Loops, Break)

````
```mermaid
sequenceDiagram
    Alice->>John: Hello John, how are you?
    loop Every minute
    John--)Alice: Great!
    end
```
````

```mermaid
sequenceDiagram
    Alice->>John: Hello John, how are you?
    loop Every minute
    John--)Alice: Great!
    end
```

````
```mermaid
sequenceDiagram
    participant User as "User"
    participant App as "Messaging App"
    participant Server as "Message Server"

    User->>App: OpenMessaging App
    activate App

    loop Check for new Messages
        App->>Server:Request New Message(s)
        activate Server
    end

    App-->>User: Display Messages
    deactivate App

```
````

```mermaid
sequenceDiagram
    participant User as "User"
    participant App as "Messaging App"
    participant Server as "Message Server"

    User->>App: OpenMessaging App
    activate App

    loop Check for new Messages
        App->>Server:Request New Message(s)
        activate Server
    end

    App-->>User: Display Messages
    deactivate App

```

````
```mermaid
sequenceDiagram
    Consumer-->API: Book something
    API-->BookingService: Start booking process
    break when the booking process fails
        API-->Consumer: show failure
    end
    API-->BillingService: Start billing process
```
````

```mermaid
sequenceDiagram
    Consumer-->API: Book something
    API-->BookingService: Start booking process
    break when the booking process fails
        API-->Consumer: show failure
    end
    API-->BillingService: Start billing process
```

---
