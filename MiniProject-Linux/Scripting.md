# Basic Shell Scripting

- A basic shell script that will create multiple folders and create multiple linux users at once would look like this.

#!/bin/bash

### Create directories
mkdir Folder1
mkdir Folder2
mkdir Folder3

### Create users
sudo useradd user1
sudo useradd user2
sudo useradd user3


---

##  **TASK 1: Create and Verify a Shell Script**

### Step 1: Create a folder

* Open your terminal.
* Run the following command to create a new folder:

  
  mkdir shell-scripting
  
* This command creates a directory called **shell-scripting** in your current working directory.

---

### Step 2: Move into the new folder

* Change directory to the folder you just created:

  
  cd shell-scripting


---

### Step 3: Create a new file using `vim`

* Use the **vim** editor to create a shell script file named **my_first_shell_script.sh**:

  
  vim my_first_shell_script.sh
  

---

### Step 4: Add shell script code

* Once in **vim**, press `i` to enter *INSERT* mode.
* Paste or type your shell script code (the one provided earlier).
  Example placeholder:

  ```bash
  #!/bin/bash
  mkdir folder1 folder2 folder3
  useradd user1
  useradd user2
  useradd user3
  ```
* Press `Esc` to exit *INSERT* mode.

---

### Step 5: Save and exit

* Type the following to save and quit **vim**:

  ```
  :wq
  ```

  This writes the file to disk and closes the editor.

---

### Step 6: Verify the file

* Confirm that the file exists using:

  ```bash
  ls -latr
  ```
* You should see **my_first_shell_script.sh** listed in the output.

---

 **TASK 2: Make the Script Executable and Test It**

### Step 1: Add execute permission for the owner

* Run the following command to give the file’s owner permission to execute it:

  
  chmod u+x my_first_shell_script.sh

* You can verify the new permission using:

  
  ls -l my_first_shell_script.sh


  You should see something like:

  -rwx------ 1 user user 85 Nov 10 11:45 my_first_shell_script.sh
  ```

  (The **x** indicates execute permission for the owner.)

---

### Step 2: Run the shell script

* Execute the script by running:

  ```bash
  ./my_first_shell_script.sh
  ```

---

### Step 3: Verify folders were created

* List the contents of the current directory to ensure the folders exist:

  ```bash
  ls
  ```
* You should see:

  ```
  folder1  folder2  folder3  my_first_shell_script.sh
  ```

---

### Step 4: Verify users were created

* Run the **id** command for each user to confirm:

  ```bash
  id user1
  id user2
  id user3
  ```
* Expected output:

  ```
  uid=1001(user1) gid=1001(user1) groups=1001(user1)
  uid=1002(user2) gid=1002(user2) groups=1002(user2)
  uid=1003(user3) gid=1003(user3) groups=1003(user3)
  ```

---

✅ **End Result:**

* You have a working shell script saved and executable.
* The script successfully created 3 folders and 3 users on your Ubuntu server.

