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
