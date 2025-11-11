
## Functional Description

### Admin Registration
**Role:** Admin

**Description:** The admin creates a family account and initializes the system.  
**Flow:**

1. Admin registers using basic details (name, email, password).  
2. System creates a unique family ID.  
3. Admin logs in to access the family dashboard.

---

### Add Family Members
**Role:** Admin  
**Description:** Admin creates accounts for each family member.  
**Flow:**

1. Admin navigates to “Add Member”.  
2. Enters member name, email, and sets a password.  
3. The system generates credentials for the member.  

---

### Add Transaction
**Role:** Family Member  
**Description:** Member records an expense or income manually.  
**Flow:**

1. Member logs in to their account.  
2. Goes to “Add Transaction.”  
3. Fills in amount, category, date, and description.  
4. Clicks “Save,” and data is stored in the database.  

---

### View Family Analytics
**Role:** Admin  
**Description:** Admin reviews overall family spending and insights.  
**Flow:**

1. Admin opens the “Family Dashboard.”  
2. System aggregates data from all members.  
3. Displays graphical reports of category-wise and member-wise spending.  

---
