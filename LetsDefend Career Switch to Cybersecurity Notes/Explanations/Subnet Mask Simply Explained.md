### 1. What is a **Subnet Mask**?

- A **subnet mask** is like a **filter** that tells us:
    
    1. Which part of an IP address is the **network address** (the street).
        
    2. Which part is the **host/device address** (the house number).
        
- Without it, devices wouldn’t know _who’s in my neighborhood_ and _who’s far away_.
    

---

### 2. Why do we need it?

- Every device needs both:
    
    - **IP Address** → like your home address.
        
    - **Subnet Mask** → like the map that tells you what is your neighborhood and which houses are nearby.
        
- If devices don’t know their “neighborhood,” they can’t send messages properly.
    

---

### 3. Format of Subnet Mask

- It looks just like an IP address (4 numbers separated by dots).
    
- Example: **255.255.255.0**
    
- In binary, it’s a series of **1s** followed by **0s**:
    
    - 255 = 11111111
        
    - 0 = 00000000
        

So **255.255.255.0** in binary =  
`11111111.11111111.11111111.00000000`

---

### 4. How does it work?

- The **1s** = “network part” (street name).
    
- The **0s** = “host part” (house numbers).
    

Example:

- IP Address: **192.168.1.10**
    
- Subnet Mask: **255.255.255.0**
    
- This means:
    
    - **192.168.1** = network (all devices on this street)
        
    - **.10** = host (specific house number)
        

So all devices with addresses **192.168.1.x** are in the same local network.

---

### 5. Prefix Notation (Short Form)

- Instead of writing the full mask, we just count the number of **1s**.
    
- Example:
    
    - **255.0.0.0** = `/8` (8 ones)
        
    - **255.255.0.0** = `/16` (16 ones)
        
    - **255.255.255.0** = `/24` (24 ones)
        

So:

- **192.168.1.10/24** means IP = 192.168.1.10 with subnet mask 255.255.255.0
    

---

### 6. Quick Analogy 🏘️

Think of a city:

- **Network part (1s)** = the neighborhood name (like “Main Street”).
    
- **Host part (0s)** = the specific house number on that street.
    
- The subnet mask is the **rulebook** that tells us where the neighborhood ends and where a new one starts.
    

---

👉 In short:  
A **subnet mask** is what separates the “network address” (the street) from the “device address” (the house). Without it, computers don’t know who’s close by and who needs a router to reach.