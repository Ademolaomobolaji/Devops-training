# Linux Shell Scripting (Control Flows)

- Create a file named control_flow.sh
- set instructions in the file (control_flow.sh) using vim editor 

#!/bin/bash
read -p "Enter a number: " num
echo "You have entered the number $num"
if [ $num -gt 0 ]; then
    echo "The number is positive."
elif [ $num -lt 0 ]; then
    echo "The number is negative."
fi

### Second Task
- Create a shell for each types of the loop
- Insert the code in the file 
- Set the correct permission for the scripts
- Execute the script and evaluate your experience.

 **step-by-step shell scripting exercise** showing **each type of loop**, how to insert code into files, and how to set correct permissions.

--- 

## 1️⃣ FOR Loop Script

### Create file

```bash
nano for_loop.sh
```

### Insert code

```bash
#!/bin/bash

for i in 1 2 3 4 5
do
  echo "Number: $i"
done
```

Save: **CTRL+O → Enter → CTRL+X**

### Set permission

```bash
chmod +x for_loop.sh
```

### Run

```bash
./for_loop.sh
```

---

## 2️⃣ WHILE Loop Script

### Create file

```bash
nano while_loop.sh
```

### Insert code

```bash
#!/bin/bash

count=1

while [ $count -le 5 ]
do
  echo "Count is: $count"
  count=$((count+1))
done
```

### Set permission

```bash
chmod +x while_loop.sh
```

### Run

```bash
./while_loop.sh
```

---

## 3️⃣ UNTIL Loop Script

### Create file

```bash
nano until_loop.sh
```

### Insert code

```bash
#!/bin/bash

num=1

until [ $num -gt 5 ]
do
  echo "Number: $num"
  num=$((num+1))
done
```

### Set permission

```bash
chmod +x until_loop.sh
```

### Run

```bash
./until_loop.sh
```

---

## 4️⃣ FOR Loop With Range Script

### Create file

```bash
nano for_range.sh
```

### Insert code

```bash
#!/bin/bash

for i in {1..5}
do
  echo "Loop value: $i"
done
```

### Set permission

```bash
chmod +x for_range.sh
```

---

## 5️⃣ FOR Loop Over Files Script

### Create file

```bash
nano file_loop.sh
```

### Insert code

```bash
#!/bin/bash

for file in *.sh
do
  echo "Shell file found: $file"
done
```

### Set permission

```bash
chmod +x file_loop.sh
```

---

## ✅ Check Permissions

```bash
ls -l *.sh
```

You should see:

```
-rwxr-xr-x
```

---


