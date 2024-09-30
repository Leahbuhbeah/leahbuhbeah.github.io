```mermaid
erDiagram
CUSTOMER ||--o{ SALE : make
 CUSTOMER {
    string name
    string customerID PK
    string sector
 }
 PRODUCT {
    string model PK
    string size
    string color
    string pattern
 }
 SALE ||--o{ PRODUCT : includes
 SALE ||--o{ INVENTORY : affect
 SALE {
    string customerID PK, FK
    string transactionID UK
    string date
    int price
    string duration
    PRODUCT[] products
 }
 INVENTORY ||--o{ PRODUCT : provides
 INVENTORY {
    int[] prices
    string[] model PK, FK
    int[] amount
 }
```
The customer makes a purchase
Leading into the product amount and type
Which leads into a sale that has specific information regarding the sale
All of which stems from the inventory amount on hand.
