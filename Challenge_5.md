# 🎯 Challenge 5: Executable Permissions for Scripts

## 🧠 Objective  
Understand the concept of **executable permissions**, how to grant them to a script, and the difference between executing a script **directly** versus **passing it to an interpreter**.

---

## 🪜 Steps

### ✅ Step 1: Create a Simple Shell Script

Create a new file named `~/my_script.sh` in your home directory and add a **shebang line** with a simple echo command:

```bash
echo '#!/bin/bash' > ~/my_script.sh
echo 'echo "Hello from my script!"' >> ~/my_script.sh
```
`Note: The >> appends to the file, while > would overwrite it.`

### ✅ Step 2: Attempt to Execute Without Permissions (Expected Failure)

Try to run the script directly:

```bash
~/my_script.sh
Expected behavior: Permission denied (because there’s no execute permission yet).
```

### ✅ Step 3: Execute Using the Interpreter (Works without Execute Bit)

Run the script explicitly with the bash interpreter:

```bash
bash ~/my_script.sh
Expected behavior: It should print the message successfully.
```
Expected behavior: It should print the message successfully.

### 📌 Initial Script Permissions (Before chmod)
```bash
ls -l ~/my_script.sh
```
Expected Output (Example):
```
-rw-rw-r-- 1 your_username your_username 31 Jul 27 21:30 my_script.sh
```

### ✅ Step 4: Grant Executable Permissions

Add execute permission for the owner:

```bash
chmod u+x ~/my_script.sh
```
### 📌 Script Permissions After Granting Execute (After Step 4)
```bash
ls -l ~/my_script.sh
```

### ✅ Step 5: Execute With Permissions (Directly)

Run the script again directly:
```bash
~/my_script.sh
```
Expected behavior: Now it works!

## 📋 Command Summary Table

| Command                                             | Purpose                                                                 |
|-----------------------------------------------------|-------------------------------------------------------------------------|
| `echo '#!/bin/bash' > ~/my_script.sh`              | Creates a new file `my_script.sh` and adds the shebang line            |
| `echo 'echo "Hello from my script!"' >> ~/my_script.sh` | Appends an echo statement to the script                                |
| `~/my_script.sh`                                    | Attempts to execute the script directly (fails without execute bit)    |
| `bash ~/my_script.sh`                               | Executes the script using the `bash` interpreter (works without `x`)   |
| `chmod u+x ~/my_script.sh`                          | Grants execute (`x`) permission to the owner of the script             |
| `ls -l ~/my_script.sh`                              | Lists detailed file permissions and verifies changes                   |

