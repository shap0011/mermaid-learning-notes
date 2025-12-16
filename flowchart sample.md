# Flowchart Diagram

## Introduction to Flowchart

---

## Flowchart Basics

````
```mermaid
flowchart
    a-->b

```
````

```mermaid
flowchart
    a-->b

```

---

## Orientation and Error Handling

TD; TB;

````
```mermaid
flowchart LR
      A[start]; B[car]; C[toy]
      A --> B
      A --> C & D
      C --> F
      B --> F
      D --> G
      D --> H

```
````

```mermaid
flowchart
      A[start]; B[car]; C[toy]
      A --> B
      A --> C & D
      C --> F
      B --> F
      D --> G
      D --> H

```

---

## Working with Nodes - Node Text

````
```mermaid
flowchart
      A["A:Family()"]
      B["B:Man 👨"]
      C["`C:Woman👩
      **#quot;Bags#quot;**
      _Shows_`"]
      A --> B
      A --> C & D[D:Children]
      C --> F[F:Married #9829;]
      B --> F
      D --> G["`G:**Boy**`"]
      D --> H[H:Girl]

```
````

```mermaid
flowchart
      A["A:Family()"]
      B["B:Man 👨"]
      C["`C:Woman👩
      **#quot;Bags#quot;**
      _Shows_`"]
      A --> B
      A --> C & D[D:Children]
      C --> F[F:Married #9829;]
      B --> F
      D --> G["`G:**Boy**`"]
      D --> H[H:Girl]

```

---

## Working with Links

### Line connection

````
```mermaid
flowchart
      %% solid directional link
      A --> B
      %% opened link
      C --- D
      %% termination of connection
      E --x F
      G --o H
      %% multidirectional link
      I <--> J
      %% dotted link
      K -.-> L
      M ==> N
      %% O --text here--> P
      O -->|text here| P
      Q -.text here.-> R
      S ==>|text here| T
```
````

```mermaid
flowchart
      %% solid directional link
      A --> B
      %% opened link
      C --- D
      %% termination of connection
      E --x F
      G --o H
      %% multidirectional link
      I <--> J
      %% dotted link
      K -.-> L
      M ==> N
      %% O --text here--> P
      O -->|text here| P
      Q -.text here.-> R
      S ==>|text here| T
```

### Invisible line connection

````
```mermaid
flowchart LR
      %% invisible line connection
      x1 ~~~ |text here| x2
      a;b;c
```
````

```mermaid
flowchart LR
      %% invisible line connection
      x1 ~~~ |text here| x2
      a;b;c
```

---

## More on Working with Links

````
```mermaid
flowchart
     %% A --> C
     %% A --> D
     %% B --> C
     %% B --> D

     A & B --> C & D

```
````

```mermaid
flowchart
     %% A --> C
     %% A --> D
     %% B --> C
     %% B --> D

     A & B --> C & D

```

````
```mermaid
flowchart LR
     A --text--> B --text--> C --text--> A
```
````

```mermaid
flowchart LR
     A --text--> B --text--> C --text--> A

```

````
```mermaid
flowchart
     A --> C
     A --> D
     B --> C
     B --> D
     C --> F --> H
     A ----> G
     A -...-> I
     A ====> J

```
````

```mermaid
flowchart
     A --> C
     A --> D
     B --> C
     B --> D
     C --> F --> H
     A ----> G
     A -...-> I
     A ====> J

```

````
```mermaid
flowchart
      A([Start]) --> B[/Input x/]
      B --> C{x > 5?}
      C -..-x |Yes| D((stop))
      C --> |No| F[/print x/]
      F --> G[x = x + 1]
      G --> C
```
````

```mermaid
flowchart
      A([Start]) --> B[/Input x/]
      B --> C{x > 5?}
      C -..-x |Yes| D((stop))
      C --> |No| F[/print x/]
      F --> G[x = x + 1]
      G --> C
```

---

## Working with Subgraph

````
```mermaid
graph LR
      subgraph one[single]
            A1
      end

      subgraph multiple
            direction LR
            subgraph two[double]
                  B1 --> B2
            end

            subgraph three[triple]
                  direction LR
                  C1 --> C2 & C3
            end
      end

      one --> multiple
      two --> three
      B2 --> C1

```
````

```mermaid
graph LR
      subgraph one[single]
            A1
      end

      subgraph multiple
            direction LR
            subgraph two[double]
                  B1 --> B2
            end

            subgraph three[triple]
                  direction LR
                  C1 --> C2 & C3
            end
      end

      one --> multiple
      two --> three
      B2 --> C1

```

---

## Flowchart Node Interactivity

[Flowchart Node Interactivity](https://shap0011.github.io/mermaid-learning-notes/Flowchart%20Node%20Interactivity.html)

---

## Flowchart - Styling Lines and Nodes
