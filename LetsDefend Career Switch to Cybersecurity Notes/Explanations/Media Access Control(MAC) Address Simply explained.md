## 1. What is a **Network Interface Card (NIC)?**

- A **NIC** is a **piece of hardware inside your computer** that connects you to a network (like Wi-Fi or Ethernet).
    
- Think of it like your computer’s **network ID card**.
    
- Without it, your computer can’t talk to other computers on the network.
    

➡️ Types of NICs:

- **Ethernet NIC** → uses cables (wired).
    
- **Wireless NIC** → allows Wi-Fi connections.
    

---

## 2. What is a **MAC Address?**

- A **MAC address** = **physical address** of your NIC.
    
- It’s a **unique number** given to your NIC at the factory (can’t be repeated).
    
- It’s like the **fingerprint** of your network card.
    

---

## 3. How is it Written?

- A MAC address is **48 bits long (6 bytes)**.
    
- Usually shown in **hexadecimal** (base-16).
    
- Example:  
    **2C:54:91:88:C9:E3**
    

---

## 4. Structure of a MAC Address

- First 3 Bytes → **Vendor ID** (who made the NIC, e.g., Intel, Dell, Cisco).
    
- Last 3 Bytes → **Unique ID** assigned by that vendor.
    

➡️ That’s why no two NICs have the same MAC.

---

## 5. MAC Address vs IP Address

- **MAC Address** → Permanent, hardware-based, set when NIC is made (like your fingerprint).
    
- **IP Address** → Software-based, can change depending on the network you’re on (like your home address).
    

Both are needed:

- IP helps find _where you are_.
    
- MAC makes sure the right _device_ gets the data.
    

---

## 6. How to Check Your MAC Address

- On **Windows**:
    
    - Open Command Prompt → type `ipconfig /all`
        
    - Look for **Physical Address**.
        
- On **Linux**:
    
    - Open terminal → type `ifconfig`
        
    - Look for **ether** (that’s your MAC).
        

---

## 7. Finding Vendor Info

- Websites like:
    
    - [macvendors.com](https://macvendors.com/)
    - [macaddress.io](https://macaddress.io/) 