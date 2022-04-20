<!--
Created: Mon Apr 18 2022 10:28:44 GMT-0400 (hora de Bolivia)
Modified: Mon Apr 18 2022 18:33:38 GMT-0400 (hora de Bolivia)
-->

# Wall-E

Your pocket-sized smart financial assistant that controls your finances.

## NoSQL Database Diagram

```mermaid
erDiagram
    DEVICE {
      string id
      string name
      string type
      string browser
      string ip
      string mac
    }
    
    LOCATION {
      string id
      string latitude
      string longitude
      string country
      string city
      string deviceId
    }
    
    PREFERENCE {
      string id
      string language
      string dateFormat
      string timeFormat
      string theme
      string deviceId
    }
    
    WORKSPACE {
      string id
      string name
      string createdAt
      string updatedAt
      string adminId
      string deviceId
    }
    
    ADMIN {
      string id
      string name
      string lastname
      string email
      string deviceId
    }
    
    CURRENCY {
      string id
      string symbol
      string code
      string name
      string adminId
    }
    
    CATEGORY {
      string id
      string name
      string color
      string createdAt
      string updatedAt
      string totalId
      string workspaceId
    }
    
    PROVIDER {
      string id
      string name
      string createdAt
      string updatedAt
      string totalId
      string workspaceId
    }
    
    PRODUCT {
      string id
      string name
      number cost
      number margin
      number price
      boolean perishable
      string createdAt
      string updatedAt
      string workspaceId
    }
    
    INVENTORY {
      string id
      number stock
      number suggest
      string createdAt
      string updatedAt
      string productId
    }
    
    TRANSACT { 
      string id
      string concept
      string type
      number quantity
      string createdAt
      string updatedAt
      string totalId
      string productIdList
      string categoryId
      string providerId
      string workspaceId
    }

    TOTAL {
      string id
      number value
      string type
      string currencyId
      string workspaceId
    }
    
    IMAGE {
      string id
      string source      
      string width
      string height
      string aspect
      string ownerId
      string workspaceId
    }
    
    DEVICE ||--|| LOCATION : "-"
    DEVICE ||--|| PREFERENCE : "-"
    DEVICE ||--|{ WORKSPACE : "-"
    DEVICE ||--|| ADMIN : "-"
    
    ADMIN ||--|{ WORKSPACE : "-"
    ADMIN ||--|{ CURRENCY : "-"
    
    WORKSPACE ||--|{ CATEGORY : "-"
    WORKSPACE ||--|{ TRANSACT : "-"
    WORKSPACE ||--|{ PROVIDER : "-"
    WORKSPACE ||--|{ PRODUCT : "-"
    WORKSPACE ||--|{ TOTAL : "-"
    WORKSPACE ||--|{ IMAGE : "-"
    
    CATEGORY ||--|| TOTAL : "-"
    
    PROVIDER ||--|| TOTAL : "-"
    PROVIDER ||--|{ IMAGE : "-"
    
    PRODUCT ||--|{ INVENTORY : "-"
    PRODUCT ||--|{ IMAGE : "-"
    
    TRANSACT }|--|{ PRODUCT : "-"
    TRANSACT ||--|| CATEGORY : "-"
    TRANSACT ||--|| PROVIDER : "-"
    TRANSACT ||--|| TOTAL : "-"
    
    TOTAL ||--|| CURRENCY : "-"
```
