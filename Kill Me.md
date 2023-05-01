```mermaid

stateDiagram-v2
    A --> *E : 0
    A --> D : 1
    
    *B --> A : 0
    *B --> C : 1

	C --> G : 0
    C --> *B : 1

	D --> *E : 0
    D --> A : 1

	*E --> H : 0
    *E --> C : 1

	F --> C : 0
    F --> *B : 1

	G --> F : 0
    G --> *E : 1

	H --> *B : 0
    H --> H : 1

```