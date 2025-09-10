### 1. What is a **Collision**?

- A **collision** happens when **two devices send data at the same time** on the same network path.
    
- The signals crash into each other, and the data has to be resent (like two people talking at once and no one understands).
    

---

### 2. What is a **Collision Domain**?

- A **collision domain** is the **area of a network where collisions can happen**.
    
- In other words, it’s the group of devices that **share the same network path** and could “talk over each other.”
    

---

### 3. How do devices affect Collision Domains?

- **Hubs**:
    
    - Hubs send data to _all ports_, so everyone shares the same line.
        
    - That means **the whole hub is one big collision domain**.
        
- **Switches**:
    
    - Switches are smarter: they send data directly to the **intended device**.
        
    - That means **each port on a switch is its own collision domain** (collisions only happen inside that tiny link).
        

---

### 4. Quick Analogy 🚦

- Think of cars on a road:
    
    - A **hub** is like one long single-lane road → if two cars try to drive at the same time, they crash → **one big collision domain**.
        
    - A **switch** is like a highway with separate lanes → each lane is isolated, so cars don’t crash into each other → **each port = its own collision domain**.
        

---

👉 So in short:  
A **collision domain** = the area where data packets can crash into each other if devices talk at the same time.

- **Hubs** = one big collision domain.
    
- **Switches** = each port is its own collision domain.