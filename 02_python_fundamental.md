# Use of enumerate()

**Concept:** 
Python mein `enumerate()` ka sabse bada kaam hai: **Ginti (Index)** aur **Samaan (Item)** dono ek sath nikal kar dena. 
*Fayda:* Isse humein alag se `i = 0` aur `i += 1` (manual counter) nahi likhna padta.

**Code Example:**
\```python
word_list = ["apple", "banana", "cherry", "mango", "orange", "grape"]
target_word = input("Enter target word: ").lower()

# enumerate ne khud index generate kiya
for indx, char in enumerate(word_list):
    if char == target_word:
        print(f"'{target_word}' found at index: {indx}")
        break
else:
    print("Not found")
\```



# Use of tuple()
**Concept:**
(1) jb hame output tuple me chahiye to hm list, set etc... ko tuple me convert kar sakte he tuple() ka use karke:
 
**Code Example:**
\```python
exam_marks = (56, 77, 23, 35, 40, 89, 90, 94, 97, 21, 33)

passing_marks = []
fail = []

for num in exam_marks:
    if num >= 35:
        passing_marks.append(num)
    else:
        fail.append(num)

valid_marks = tuple(passing_marks)
invalid_marks = tuple(fail)

print(f"Passed marks {valid_marks}")
print(f"Failed marks {invalid_marks}")
\```


**Concept:** 
List Comprehension Python ka ek bohot powerful shortcut hai. Yeh humein ek naye List banane ka aasan aur fast tarika deta hai, jiske liye humein lamba `for` loop aur `.append()` nahi likhna padta.

\```python
exam_marks = (56, 77, 23, 35, 40, 89, 90, 94, 97, 21, 33)

# Pehle List Comprehension se filter kiya, aur seedha tuple() mein pack kar diya
valid_marks = tuple([num for num in exam_marks if num >= 35])
invalid_marks = tuple([num for num in exam_marks if num < 35])

print(f"Passed marks {valid_marks}")
print(f"Failed marks {invalid_marks}")
\```

***Explaination***
for se pehle wala num yeh batata hai ki "Nayi list ke andar aakhiri (final) result kya daalna hai."
[num | for num in exam_marks | if num >= 35]
# Part 3 (if num >= 35): Yeh check karega ki number 35 se bada hai ya nahi. (Maan lijiye isne list mein se 56 ko pakda).
# Part 2 (for num in exam_marks): Yeh loop hai jo ek-ek karke number laata hai.
# Part 1 (Pehla num): Yeh decide karta hai ki jo 56 pakda gaya hai, uske sath kya karna hai? Kyunki yahan sirf num likha hai, toh yeh 56 ko waise ka waisa hi nayi list mein daal dega.

***Is pehle num ko change karne se kya hoga?***
# Agar aap us pehle num ki jagah kuch aur likh dein, toh output poori tarah badal jayega. Maan lijiye EduConnect software mein humein sabko 5 grace marks (bonus) dene hain.

# Example 1
\```python
# Pehle num ki jagah num + 5 likh diya
bonus_marks = [num + 5 for num in exam_marks if num >= 35]

# Ab nayi list mein 56 nahi jayega, 56 + 5 = 61 jayega!

# Example 2: Value ko word se replace karna
# Pehle num ki jagah "Pass" likh diya
status = ["Pass" for num in exam_marks if num >= 35]
# Ab list aisi dikhegi: ['Pass', 'Pass', 'Pass', ...]

***Summary***
Dusra num (for ke baad wala): Wo ek variable hai jo ek-ek box utha kar laata hai.
Pehla num (for ke pehle wala): Wo aadesh (command) hai ki us box ka kya karna hai (waise hi rakhna hai, usme kuch jodna hai, ya use badalna hai).




# Sets in Python (The 4th Pillar)

**Concept:**
Set ek aisi tokri (collection) hai jisme **sirf unique (alag) items** aa sakte hain. Isme koi bhi item repeat (duplicate) nahi ho sakta. Data Science aur Data Analysis mein jab kisi bade data mein se sirf "Unique" values nikalni hon, tab Sets ka sabse zyada use hota hai.

**Syntax (Pehchaan):**
Sets ko hamesha **Curly Brackets `{}`** ke andar likha jata hai (lekin Dictionary ki tarah Key-Value nahi hote, sirf items hote hain).
`my_set = {1, 2, 3, 4}`

---

### 📌 Sets ke 3 Sabse Bade Rules (Properties):
1. **No Duplicates:** Isme ek value sirf ek baar hi aa sakti hai. Agar aap `{1, 2, 2, 3}` likhenge, toh Python usko automatically theek karke `{1, 2, 3}` kar dega.
2. **Unordered:** Sets ka koi order nahi hota. Jab aap print karenge, toh items aage-peeche aa sakte hain. (Isi wajah se aap list ki tarah index `my_set[0]` nahi laga sakte).
3. **Changeable (Modifiable):** Aap set mein naye item daal (add) sakte hain aur nikal (remove) sakte hain.

---

### 🛠️ Sabse Zyada Use Hone Wale Methods:

**1. Common nikalna (Intersection):** *(Jo dono mein ho)*
```python
set1 = {1, 2, 3}
set2 = {3, 4, 5}
print(set1.intersection(set2)) # Output: {3}


**2. Sabko milana (Union): (Dono ko jodna, par bina duplicate ke)**
set1 = {1, 2}
set2 = {2, 3}
print(set1.union(set2)) # Output: {1, 2, 3}

**3. Check karna kuch common toh nahi (isdisjoint):**
print(set1.isdisjoint(set2)) # Haan ya Naa (True/False) mein jawab dega

**4. Naya item Add karna:**
my_set = {1, 2}
my_set.add(10)

**5. Item Hatana (Remove):**
my_set.remove(10)





