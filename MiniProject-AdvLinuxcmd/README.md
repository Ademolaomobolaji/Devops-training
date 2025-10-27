# File Permission and Access Rights 

### Numeric representation of permissions.
 In Linux, Permission are represented using numeric value. Each Permission (No permission, read, write and execute) is assigned a numberic value.
 - -no permission = 0
 - read = 4
 - write= 2 and 
 - execute = 1


---

## 🧩 ** Linux File Permissions?**

In Linux, every file and directory has **permissions** that control who can **read**, **write**, or **execute** it.
These permissions are assigned to **three categories of users**:

| Category       | Meaning                              | Example                   |
| -------------- | ------------------------------------ | ------------------------- |
| **User (u)**   | The owner of the file                | The person who created it |
| **Group (g)**  | Users in the same group as the owner | Team members              |
| **Others (o)** | Everyone else                        | All other users           |

---

## ⚙️ **Permission Types**

Each category (User, Group, Others) can have **three permissions**:

| Symbol | Meaning | Numeric Value | Example Effect                                |
| :----: | :------ | :-----------: | :-------------------------------------------- |
|  **r** | Read    |      `4`      | View file content or list directory           |
|  **w** | Write   |      `2`      | Modify or delete file                         |
|  **x** | Execute |      `1`      | Run the file as a program or access directory |

---

## 🔢 **How Numeric (Octal) Permissions Work**

Each permission is represented by a **number**:

* `r` = 4
* `w` = 2
* `x` = 1

To get the numeric permission, **add up the values** for each category.

### Example:

| Permission | r | w | x | Total |
| ---------- | - | - | - | ----- |
| User       | 4 | 2 | 1 | **7** |
| Group      | 4 | 0 | 1 | **5** |
| Others     | 4 | 0 | 0 | **4** |

So, permission:

```
rwxr-xr--
```

becomes:

```
754
```

---

## 💡 **Common Numeric Permission Codes**

|   Code  | Symbolic    | Meaning                                       |
| :-----: | :---------- | :-------------------------------------------- |
| **777** | `rwxrwxrwx` | Everyone can read, write, execute             |
| **755** | `rwxr-xr-x` | Owner full control; others can read & execute |
| **700** | `rwx------` | Only owner can read, write, execute           |
| **644** | `rw-r--r--` | Owner can read/write; others can read only    |
| **600** | `rw-------` | Owner can read/write; no access for others    |
| **444** | `r--r--r--` | Everyone can read only                        |

---

## 🧮 **Changing Permissions Using `chmod`**

You use the `chmod` command followed by the numeric code and file name.

### Example 1:

```bash
chmod 755 script.sh
```

➡ Gives the owner full rights, and others read & execute access.

### Example 2:

```bash
chmod 644 myfile.txt
```

➡ File owner can read/write, everyone else can only read.

---

## 🔐 **Quick Reference Diagram**

```
       USER   GROUP   OTHERS
rwx →  7       5       4
```

So, `chmod 754` = **User: rwx**, **Group: r-x**, **Others: r--**

---


