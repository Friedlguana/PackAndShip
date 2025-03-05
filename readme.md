
# 🎯 GDSC Tech (Cyber Security) Task: Pack and Ship

---

## 📂 Initial Analysis

### Step 1 - Basic Recon
Ran `file` and `strings` commands on the binary file to get an overview of what I would be dealing with. Found some info:

![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-04%20212517.png?raw=true)
![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-04%20213053.png?raw=true)

Initially thought password would be in plaintext but found nothing of use. But this means I can unpack the file with upx, which may be a way to the solution.

---

### Step 2 - Static Analysis in Ghidra

- Opened the binary in **Ghidra**.
- Found a lot of interesting stuff in main()

![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-05%20131000.png?raw=true)



---

## 🔎 Studying `deobfuscate()`

Looking at the decompiled program:

![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-05%20162536.png?raw=true)
- A quick run through chatGPT tells us that the code XORs to deobfuscate.
- It uses the `KEY` as it's key for XORing.

---

## 🔨 Extracting the Data & Key

- Located the obfuscated data by referencing the argument variable:
![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-05%20163932.png?raw=true)

- Same method to find key. Results were:

Obfuscated Data: `31 d0 41 c7 80 d4 08 2b e2 4a 87 f1 9c 27 1f d1 0d dd f8 a2 10 22 f0 2e f8 83 95 2d 61 ce 2c c3`

Key: `53 a4 79 b2 c1 e5 7d
`

---

## 🧬 XOR Deobfuscation

- XORed the value in cyberchef revealing a string:

![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-05%20164231.png?raw=true)

- Ran the string as password for the program which then printed:

![screenshot](https://github.com/Friedlguana/PackAndShip/blob/main/Screenshot%202025-03-05%20164714.png?raw=true)

*tbh I first copied the flag data and deobfuscated it to get the actual flag value. But i guess this is how the solution was supposed to go. Anyways...*

