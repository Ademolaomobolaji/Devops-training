# Shell Scripting- Mini Project
---

## Step 1: Create the project directory

From your terminal, create a directory called **shell-scripting**:

```bash
mkdir shell-scripting
```

---

## Step 2: Change into the directory

```bash
cd shell-scripting
```

---

## Step 3: Create the shell script using vim

Open a new file called **my_first_shell_script.sh** with `vim`:

```bash
vim my_first_shell_script.sh
```

---

## Step 4: Insert the shell script code

Press **i** to enter *insert mode*, then paste the following code:

```bash
#!/bin/bash

# Create directories
mkdir Folder1
mkdir Folder2
mkdir Folder3

# Create users
sudo useradd user1
sudo useradd user2
sudo useradd user3
```

---

## Step 5: Save and exit vim

1. Press **Esc**
2. Type:

   ```bash
   :wq
   ```
3. Press **Enter**

---

## Step 6: Confirm the file was created

Run:

```bash
ls -latr
```

You should see output similar to:

```bash
-rw-r--r-- 1 root root 149 Feb 11 14:35 my_first_shell_script.sh
```

👉 Notice there is **no execute (x)** permission yet.

---

## Step 7: Add execute permission for the owner

Grant execute permission to the file owner:

```bash
chmod u+x my_first_shell_script.sh
```

Verify the permission change:

```bash
ls -l my_first_shell_script.sh
```

Expected output:

```bash
-rwxr--r-- 1 root root 149 Feb 11 14:35 my_first_shell_script.sh
```

---

## Step 8: Run the shell script

Execute the script:

```bash
./my_first_shell_script.sh
```

> If prompted, enter your sudo password to allow user creation.

---

## Step 9: Verify the folders were created

Run:

```bash
ls
```

You should see:

```bash
Folder1  Folder2  Folder3  my_first_shell_script.sh
```

---

## Step 10: Verify the users were created

Check each user with the `id` command:

```bash
id user1
id user2
id user3
```

Expected output example:

```bash
uid=1000(user1) gid=1000(user1) groups=1000(user1)
```

---

## ✅ Summary of What You Achieved

* Created a project directory
* Wrote a shell script using **vim**
* Learned about Linux file permissions
* Used **chmod** to make a script executable
* Executed a shell script
* Created directories and Linux users
* Understood the purpose of the **shebang (#!/bin/bash)**

You’re now officially running executable shell scripts on Linux 🚀
