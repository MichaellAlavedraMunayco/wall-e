<!--
Created: Mon Apr 18 2022 10:28:44 GMT-0400 (hora de Bolivia)
Modified: Mon Apr 18 2022 10:28:44 GMT-0400 (hora de Bolivia)
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
      string locationId
      string preferenceId
      string workspaceIdList
    }    
    
    LOCATION {
      string id
      string latitude
      string longitude
      string country
      string city
    }
    
    PREFERENCE {
      string id
      string language
      string dateFormat
      string timeFormat
      string uiTheme
    }
    
    WORKSPACE {
      string id
      string name
      string adminId
      string createdAt
      string updatedAt
    }
    
    ADMIN {
      string id
      string fullname
      string email
    }
    
    CURRENCY {
      string id
      string symbol
      string code
      string name
      string workspaceId
    }
    
    CATEGORY { }
    
    PROVIDER { }
    
    PRODUCT { }
    
    INVENTORY { }
    
    TRANSACT { 
      string id
      string concept
      string type
      string total
      string createdAt
      string updatedAt
      string categoryId
      string providerId
      string currencyId
    }
    
    DEVICE ||--|| LOCATION : "-"
    DEVICE ||--|| PREFERENCE : "-"
    DEVICE ||--|| WORKSPACE : "-"
    WORKSPACE ||--|| ADMIN : "--"
```
