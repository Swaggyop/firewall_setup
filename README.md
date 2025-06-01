# 🔐 Task 4: Setup and Use a Firewall on Windows (Telnet Version)

## 🎯 Objective

Configure and test basic Windows Firewall rules to allow or block traffic on a specific port using only one machine. This example uses **port 23 (Telnet)**.

## 🛠 Tools Used

* Windows Defender Firewall (`wf.msc`)
* Telnet Client (Windows feature)
* Command Prompt

## 📄 Deliverables

* Screenshots of rule creation, test results, and removal
* Documentation of steps and summary of firewall behavior

---

## ✅ Steps Performed

### 1. Open Firewall Configuration Tool

* Press `Win + R` → type `wf.msc` → press **Enter**
* Launches Windows Defender Firewall with Advanced Security

### 2. List Current Firewall Rules

* Inside `wf.msc`, click **Inbound Rules** to view all existing inbound firewall rules

### 3. Add a Rule to Block Inbound Traffic on Port 23 (Telnet)

1. Click **New Rule...** in the right-hand panel
2. Choose **Port** > Next
3. Select **TCP** > enter **23** as the port
4. Choose **Block the connection**
5. Apply to **Domain, Private, Public** profiles
6. Name it: `Block Telnet Test` > Finish

### 4. Test the Rule Locally

* Open **Command Prompt**
* Run:

  ```
  telnet localhost 23
  ```
* Expected result (if blocked):

  ```
  Connecting To localhost...Could not open connection to the host, on port 23: Connect failed
  ```

### 5. Add SSH Allow Rule (Skip for Windows)

SSH (port 22) is generally for Linux. This step is skipped.

### 6. Remove the Test Block Rule

* Go to **Inbound Rules**
* Locate `Block Telnet Test` rule
* Right-click > **Delete**

---

## 📌 7. Documented Commands or GUI Steps Used

* Enabled Telnet via **Control Panel > Windows Features**
* Used `wf.msc` to create a new inbound rule
* Blocked TCP port 23 using GUI
* Used `telnet localhost 23` to test connectivity
* Deleted the rule via right-click in Inbound Rules

---

## 📌 8. Summary: How Windows Firewall Filters Traffic

Windows Firewall evaluates all network traffic against a set of **rules** defined by the user or system policies. These rules control traffic based on:

* Protocol (TCP/UDP)
* Port number
* Direction (Inbound/Outbound)
* Application or service
* Network profile (Domain, Private, Public)

In this exercise:

* A rule was added to **block TCP port 23** for all inbound traffic.
* When tested with `telnet localhost 23`, the connection was refused, demonstrating the rule’s effect.
* Once the rule was removed, access to port 23 was restored.

This confirms that Windows Firewall can effectively manage traffic to protect services from unauthorized access—even from the same machine.

---

## 🖼️ Recommended Screenshots

* Windows Features > Telnet Client enabled
* `wf.msc` showing created rule
* Telnet connection attempt before and after the rule
* Deleted rule confirmation

---

## 🧠 Conclusion

This task successfully demonstrated how to block and test traffic on a specific port (Telnet/Port 23) using Windows Firewall. The entire procedure was done using a **single laptop**, making it ideal for individual lab environments or learning purposes.

---

## ✍️ Author

**Saswat Kumar**
Cybersecurity Student
