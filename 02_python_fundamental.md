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