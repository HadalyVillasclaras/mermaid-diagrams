# Just testing Mermaid diagrams :)

```mermaid
flowchart
  A --> B
````

---
Sequence diagram
```mermaid
sequenceDiagram
  autonumber
  participant Client
  participant OAuthProvider
  participant Server
  Client ->> OAuthProvider: Request access token
  activate OAuthProvider
  OAuthProvider->>Client: Send access token
  deactivate OAuthProvider
  Client->>Server: Request resource
  activate Server
  Server->>OAuthProvider: Validate token
  activate OAuthProvider
  OAuthProvider->>Server: Token valid
  deactivate OAuthProvider
  Server->>Client: Send results
  deactivate Server
```


---
Class diagram
```mermaid
classDiagram
  class Order{
    +OrderStatus status
  }
  class OrderStatus {
    <<enumeration>>
    FAILED
    PENDING
    PAID
  }
  class PaymentProccessor{
    <<interface>>
    -String apiKey
    #connect(String url, JSON header)
    +processPayment(Order order) OrderStatus
  }
  class Customer{
    +String name
  }
  Customer <|--PrivateCustomer
  Customer <|--BusinessCustomer
  PaymentProcessor <|-- StripePaymentProcessor
  PaymentProcessor <|-- PaypalPaymentProcessor
  Order o-- Customer
  Car *-- Engine
```

---
E-R Diagram
```mermaid
erDiagram
  Customer ||--o{ Order : places
  Order ||--|{ LineItem : contains
  Customer {
    String id
    String name
  }
  Order {
    String id
    OrderStatus status
  }
  LineItem{
    String code
    String description
    int quantity
    int price
  }

```

```mermaid
pie showData
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5

```

```mermaid
flowchart LR
  S[Start] --> A;
  A(Enter your email address) --> B{Existing user?};
  B --> |No| C(Enter name)
  C --> D{Accept conditions?}
  D --> |No| A
  D --> |Yes| E(Send email)
  B --> |Yes| E
  E --> End
````
