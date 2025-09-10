## 1. What is ARP?

- **ARP (Address Resolution Protocol)** is like a **translator**.
    
- Its job: match an **IP address** (logical address) to a **MAC address** (physical address).
    
- Why? Because computers talk to each other using **MAC addresses** at the data link layer, but we usually identify devices with **IP addresses**.
    

👉 Without ARP, your computer would know the IP of another device but wouldn’t know how to actually send data to it.

---

## 2. How Does ARP Work?

Imagine Device A wants to talk to Device B:

1. **Device A knows B’s IP** but not its MAC.
    
2. Device A shouts to everyone on the network:  
    → **“Who has IP 192.168.1.20? Tell me your MAC!”** (this is an **ARP Request**, a broadcast).
    
3. All devices hear the shout, but **only Device B replies**:  
    → **“That’s me, my MAC is AA:BB:CC:DD:EE:FF.”** (this is the **ARP Reply**).
    
4. Device A now saves this info in its **ARP Table** so it doesn’t have to ask again soon.
    

---

## 3. What is an ARP Table?

- The ARP table is like a **phone book** stored on each device.
    
- It keeps a list of IP addresses and their matching MAC addresses.
    
- Two types of entries:
    
    - **Dynamic** → learned automatically by asking around (ARP requests).
        
    - **Static** → manually entered by an admin (they don’t change until removed).
        

👉 On **Windows**, you see it with: `arp -a`  
👉 On **Linux**, you see it with: `arp` or `ip neigh`

---

## 4. ARP in Everyday Life (Analogy)

Think of IP addresses as **names** and MAC addresses as **faces**:

- You might know someone’s name (IP), but to find them in a crowd you need to know their face (MAC).
    
- ARP is like asking:
    
    - “Hey, who is **Sindiswa**?”
        
    - The real Sindiswa raises their hand and says: “It’s me, this is my face.”
        
- After that, you remember both the name + face pairing in your **mental phonebook** (ARP table).
    

---

## 5. ARP Packet Details 

Each ARP message has fields. The important ones:

### 📌 1. **Hardware Type**

- Tells what “delivery system” we’re using at the **data link layer**.
    
- Example: `0x0001 = Ethernet` (the postal service).  
    👉 Think of it like saying: _“This letter will be sent by Post Office, not by FedEx.”_
    

---

### 📌 2. **Protocol Type**

- Tells what “language/address system” we’re using at the **network layer**.
    
- Example: `0x0800 = IPv4` (Internet Protocol).  
    👉 Like saying: _“We’re writing the address in street addresses (IPv4), not in GPS coordinates.”_
    

---

### 📌 3. **Hardware Length**

- Shows how long the **hardware address** is.
    
- Example: Ethernet MAC = `6 bytes`.  
    👉 Like saying: _“The postal code has 6 digits.”_
    

---

### 📌 4. **Protocol Length**

- Shows how long the **protocol (IP) address** is.
    
- Example: IPv4 = `4 bytes`.  
    👉 Like saying: _“The street address has 4 parts (e.g., 192.168.1.1).”_
    

---

### 📌 5. **Operation Code (Opcode)**

- Tells if this is a **question** or an **answer**.
    
- `1 = ARP Request` (_“Who has this address?”_)
    
- `2 = ARP Reply` (_“I have it!”_)  
    👉 Like: _“Are we asking for your address or giving it?”_
    

---

### 📌 6. **Sender Hardware Address**

- The sender’s **MAC address**.  
    👉 Like: _“Here’s my return address (house number).”_
    

---

### 📌 7. **Sender Protocol Address**

- The sender’s **IP address**.  
    👉 Like: _“Here’s my street address.”_
    

---

### 📌 8. **Target Hardware Address**

- The receiver’s **MAC address**.  
    👉 Like: _“This is the house number I want to send to.”_  
    (If unknown, it’s left blank in a Request.)
    

---

### 📌 9. **Target Protocol Address**

- The receiver’s **IP address**.  
    👉 Like: _“This is the street address I’m looking for.”_
    

---

✅ Put together:  
An ARP packet is basically an **envelope** that says:

- “I’m using Ethernet (Hardware Type)”
    
- “I’m talking about IPv4 (Protocol Type)”
    
- “Here’s my MAC & IP (Sender fields)”
    
- “Who has this IP? Tell me your MAC (Target fields + Opcode).”
    

---

## 6. Reviewing ARP with Tools

- Tools like **Wireshark** let you capture ARP packets and see exactly who’s asking “Who has IP X?” and who’s replying.
    
- You’ll clearly see:
    
    - **ARP Request:** broadcast to everyone.
        
    - **ARP Reply:** unicast (direct response).
        

---

👉 **In short:**

- ARP = translator that finds the MAC address for a known IP.
    
- It works by broadcasting a request and waiting for the correct reply.
    
- Results are stored in the ARP table for faster future communication.