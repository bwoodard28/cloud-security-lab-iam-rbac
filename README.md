# Azure IAM Demo: Role-Based Access Control (RBAC)

This project demonstrates how Azure RBAC affects access to resources.  
We created a restricted user (`labuser`) and tested **two scenarios**:

1. **Over-permissioned (Owner role)**  
2. **Scoped / Least Privilege (Storage Blob Data Reader)**  

---

## 1. Starting Point
`labuser` initially has no roles.  
![No roles](screenshots/00-no-roles.png)

---

## 2. Over-Permissioned Example
Assigning `Owner` role at the subscription scope → `labuser` can manage everything.  
- **Role assignment**  
![Owner Role Assignment](screenshots/03-role-assignment-owner.png)  
- **Full access confirmed**  
![Owner Success](screenshots/06-owner-success.png)  

⚠️ *This demonstrates the risk of assigning broad roles unnecessarily.*  

---

## 3. Least Privilege Example
Instead, assign a scoped **Storage Blob Data Reader** role on just the storage account.  
- **Scoped role assignment**  
![Role Scoped](screenshots/05-role-scoped.png)  

---

## 4. Results of Least Privilege
- Listing storage accounts still fails at subscription level:  
![List Denied](screenshots/07-list-denied.png)  

- But blob access inside the assigned storage account succeeds:  
![Blob Success](screenshots/08-blob-success.png)  

✅ *This demonstrates proper least-privilege access.*  

---

## Key Takeaways
- Broad “Owner” assignments give users full control and break security principles.  
- Scoped roles enforce least privilege, reducing risk.  
- Authorization failures are expected and prove RBAC is working correctly.
