# PocketBuddy Backend – Test Plan

## 1. Introduction
This test plan outlines the testing strategy for the **PocketBuddy Backend**, covering modules such as authentication, user management, transactions, categories and expense-sharing workflows. The goal is to ensure API correctness, reliability, security, and seamless integration of financial features.

## 2. Objectives
- Validate that all core backend APIs behave as expected.  
- Ensure proper functioning of JWT authentication and role-based permissions (Admin/User).  
- Verify accuracy of database operations—transactions,  categories, and summaries.  
- Detect bugs early and maintain backend stability.  
- Ensure API responses match defined schema and error structures.

## 3. Scope

### In Scope
Unit tests for:
- User signup/login  
- JWT access token flows  
- CRUD operations:  
  - Transactions  
  - Categories   
  - Members   
- Validations and error handling  
- Admin-protected endpoints  

### Out of Scope
- Frontend tests  
- UI/UX validation  
- Load, performance, or stress testing  
- Infrastructure-specific tests (CI/CD, EC2 configuration)

## 4. Test Items
Components to be tested:

### Authentication Module
- Signup, Login  
- Password hashing  
- JWT token creation & validation  
- Token expiry and refresh flow  

### Authorization Module
- Admin-only routes  
- User-level access   

### Transaction Module
- Add new transaction  
- Edit/update transaction  
- Delete transaction   
- Fetch all transactions  
- Filter by category
- Expense summary  

###  & Splitting
- Add/remove members  
- Add expenses in group  
- Fetch family summary  

### Common Backend Behavior
- Standardized error responses  
- Validation failures  
- Status code correctness  

## 5. Testing Approach

### Unit Testing
- Framework: **pytest**  
- Use SQLite in-memory DB  
- Override FastAPI dependencies for `get_db()`  
- Mock:
  - JWT creation/verification  
  - User roles  

### Integration Testing
- Use **FastAPI TestClient (HTTPX)**  
- Test complete workflows:  
  - Signup → Login → Add Transaction → Fetch Summary  
  - Add Members → Add Expense  
- Validate:
  - Status codes  
  - Schema  
  - Edge cases  


## 6. Test Environment
- **Language:** Python  
- **Framework:** FastAPI  
- **Database:** SQLite (test) / PostgreSQL (production)  
- **Tools:**  
  - `pytest`  
  - `HTTPX TestClient`  
  

## 7. Test Data

### Dummy Users
- `admin@example.com`  
- `user1@example.com`  
- `user2@example.com`  

### Dummy JWT Tokens
- Valid access token  
- Invalid/expired tokens  

### Transactions
- Valid transactions (food, travel, shopping)  
- Invalid payloads (missing fields, negative amount)  

### Categories
- Valid and invalid category names  

## 8. High-Level Test Cases

### Authentication
- Signup success  
- Duplicate email  
- Login success  
- Wrong password  
- Token generation  
- Expired/invalid token access  

### Authorization
- Admin-only endpoint access  
- User-only access  
- Missing token → 401  
- Insufficient permission → 403  

### Users
- Create user  
- Validation errors  

### Transactions
- Create transaction  
- Edit transaction  
- Delete transaction  
- Fetch all transactions  
- Fetch by category
- Summary calculations accuracy  


### Family Member 
- Add member  
- Remove member  


### Common API Behavior
- 400 – Validation errors  
- 401 – Unauthorized  
- 403 – Forbidden  
- 404 – Not Found  
- 500 – Unexpected errors  

## 9. Exit Criteria
Testing is considered complete when:
- All critical & high-priority test cases pass  
- No major or blocking defects remain  
- All core APIs produce stable and correct responses  

