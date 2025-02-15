### 1️⃣ **Initialize Terraform**
```bash
terraform init
```
**Description:**  
Initializes the working directory by downloading the necessary provider plugins (AWS, Azure, Google Cloud, etc.).  

### 🔹 **Purpose**
- Ensures Terraform has the required tools to communicate with the platforms defined in the configuration.

---

### 2️⃣ **Plan Infrastructure Changes**
```bash
terraform plan
```
**Description:**  
Previews the changes Terraform will apply by comparing the desired state in the configuration files with the current infrastructure.  

### 🔹 **Purpose**
- Generates an execution plan showing additions, modifications, or deletions.
- No actual changes are made during this step.

---

### 3️⃣ **Apply Changes**
```bash
terraform apply
```
**Description:**  
Executes the Terraform plan and provisions/modifies the infrastructure.  

### 🔹 **Purpose**
- Communicates with cloud provider APIs to create, update, or destroy resources.

---

## **📜 State Management**
Terraform maintains a **state file** (`terraform.tfstate`) to track the infrastructure's current state.

### 🔹 **Remote State**
For collaboration, the state file can be stored remotely (e.g., **S3, Google Cloud Storage**) to:
- Ensure consistency
- Avoid conflicts  

> **⚠️ Importance:** The state file helps Terraform understand existing infrastructure and detect changes.

---

### 4️⃣ **Modify Infrastructure**
When changes are made to the configuration:
1. Run:
   ```bash
   terraform plan
   ```
   - To detect differences between the configuration and current infrastructure.
2. Run:
   ```bash
   terraform apply
   ```
   - To apply the updates.

---

### 5️⃣ **Destroy Infrastructure**
```bash
terraform destroy
```
**Description:**  
Tears down all infrastructure defined in the configuration and cleans up state files.

### 🔹 **Purpose**
- Useful for **decommissioning** infrastructure.
- Ensures no unused resources are left behind.

---

### 6. **Format the configuration**
```bash
terraform fmt
```
**Description:**  
The **terraform fmt** command automatically updates configurations in the current directory for readability and consistency. Format your configuration. Terraform will print out the names of the files it modified, if any. In this case, your configuration file was already formatted correctly, so Terraform won't return any file names.

---

### 7. **Validate the configuration**
```bash
terraform validate
```
**Description:**  
You can also make sure your configuration is syntactically valid and internally consistent by using the terraform validate command. Validate your configuration. The example configuration provided above is valid, so Terraform will return a success message.

---

### 8. **Inspect State**
```bash
terraform show
```
**Description:**  
Inspect the current state using **terraform show**. It also gathered the resource's metadata from the provider and wrote the metadata to the state file.

---

### 9. **Manually Managing State**
```bash
terraform state list
```
**Description:**  
Terraform has a built-in command called **terraform state** for advanced state management. Use the **list** subcommand to list of the resources in your project's state.

---

## **🔄 Terraform Workflow Summary**
| Step        | Command                | Purpose |
|------------|----------------------|---------|
| **Define** | Write `.tf` files | Describe infrastructure as code |
| **Initialize** | `terraform init` | Setup environment & download providers |
| **Plan** | `terraform plan` | Preview infrastructure changes |
| **Apply** | `terraform apply` | Execute changes |
| **State Management** | `terraform state` | Track infrastructure state |
| **Modify** | `terraform plan/apply` | Update infrastructure |
| **Destroy** | `terraform destroy` | Remove infrastructure |

---

## **📌 Notes**
- Always **review** the plan before applying changes.
- Use **remote state storage** in team environments.
- Terraform is **declarative** → you define the desired state, and it ensures compliance.

---
