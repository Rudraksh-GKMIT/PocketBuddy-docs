
## Entity Relationship Diagram

```mermaid

erDiagram
    users{
        UUID id PK
        varchar family_id FK 
        varchar name
        varchar email
        varchar password_hash 
        timestamp created_at 
        timestamp deleted_at 
        timestamp updated_at 
    }
    roles{
        UUID id pk
        varchar name
        timestamp created_at 
        timestamp deleted_at 
        timestamp updated_at
    }
    families {
        UUID id PK
        varchar name 
        timestamp created_at 
        timestamp deleted_at 
        timestamp updated_at 
    }
    transactions {
        UUID id PK 
        int user_id FK 
        varchar type 
        varchar description 
        float amount
        timestamp created_at 
        timestamp deleted_at 
        timestamp updated_at
    }
    user_roles {
        UUID id PK
        int user_id FK
        int role_id FK
        timestamp created_at 
        timestamp deleted_at 
        timestamp updated_at 
    }
    users ||--|| user_roles : "assigned roles"
    families ||--o{ users : "has members"
    users ||--o{ transactions : "records"
    roles ||--o{ user_roles : "assigned to users"
```

## Database Tables

### 1. users
Stores user login information.

**Fields:**

- `id` - Unique user ID
- `family_id` - To connect user to family
- `name` - Login username
- `email` - Personal email 
- `password_hash` - Encrypted password
- `created_at ` - Time at which user is created 
- `deleted_at` - Time at which user is deleted
- `updated_at` - Last Time at which user is updated

---

### 2. transactions
Stores all transactions information.

**Fields:**

- `id` - Unique transactions ID
- `user_id` - Unique user ID which made the transactions
- `type` - transactions type (e.g., Need, Luxury)
- `amount` - amount of transaction
- `description` - transactions details(optional)
- `created_at ` - Time at which transactions is created 
- `deleted_at` - Time at which transactions is deleted
- `updated_at` - Last Time at which transactions is updated

---

### 3. families
Stores user family information.

**Fields:**

- `id` - Unique family ID
- `name` - Name of the family
- `quantity` - Current stock level
- `created_at ` - Time at which family is created 
- `deleted_at` - Time at which family is deleted
- `updated_at` - Last Time at which family is updated

--- 

### 4. roles
Stores role information.

**Fields:**

- `id` - Unique role ID
- `name` - Type of role(e.g., Head,Member)
- `created_at ` - Time at which role is created 
- `deleted_at` - Time at which role is deleted
- `updated_at` - Last Time at which role is updated

### 5. uses_roles
Stores user role information.

**Fields:**

- `id` - Unique ID
- `user_id` - Unique user ID
- `role_id` - Unique role id
- `created_at ` - Time at which role is created 
- `deleted_at` - Time at which role is deleted
- `updated_at` - Last Time at which role is updated
---