# 🏛️ Object-Oriented Programming (OOP): Classes & Objects

Data Science aur development mein bade programs ko manage karne ke liye hum OOP ka use karte hain. Iske 2 sabse bade pillars hain: Class aur Object.

## 1. Class (The Blueprint / Template)
Class ek **Naksha (Blueprint) ya Recipe** hai. Yeh batati hai ki banne wali cheez kaisi dikhegi (Attributes/Variables) aur kya kaam karegi (Methods/Functions).
* **Important:** Class sirf ek idea hai, yeh memory (RAM) mein jagah nahi gherte jab tak iska object na banaya jaye.

## 2. Object (The Instance / Reality)
Object us nakshe ko dekh kar banayi gayi **Asli Cheez (Realization)** hai. 
* Ek blueprint (Class) se aap hazaron asli objects bana sakte hain.
* Har object apna alag data rakhta hai aur memory occupy karta hai.

---

### 💻 Syntax & Example (The 'Dot' Magic)

```python
# 1. Class Banana (Blueprint design karna)
class Car:  
    brand = "Toyota" 

# 2. Object Banana (Asli gaadi tayar karna)
car1 = Car()  
car2 = Car()  

# 3. Dot (.) Operator (Object ke data ko access karna)
print(car1.brand)  # Output: Toyota
