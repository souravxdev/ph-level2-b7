# Our Workhorse: The Array & Time Complexity

## Array এবং Time Complexity-এর সম্পর্ক

জাভাস্ক্রিপ্টে Array হলো সবচেয়ে বেশি ব্যবহৃত ডেটা স্ট্রাকচার (Workhorse)। একটি Array-তে টাইম কমপ্লেক্সিটি মূলত নির্ভর করে আমরা কোন মেথডটি ব্যবহার করছি এবং সেই মেথডটি array-এর ভেতরের উপাদানগুলোর (elements) অবস্থান পরিবর্তন (shift/re-index) করছে কি না তার ওপর।

### `O(1)` - Constant Time Operations (খুব দ্রুত)

যেসব অপারেশন Array-এর শেষে কাজ করে এবং ভেতরের কোনো উপাদানের ইনডেক্স (index) পরিবর্তন করে না, তাদের complexity `O(1)`।

- **`push()`:** Array-এর শেষে নতুন element যোগ করে। এটি `O(1)` কারণ অন্য কোনো element-এর ইনডেক্স পরিবর্তন করতে হয় না।
- **`pop()`:** Array-এর শেষ থেকে element রিমুভ করে। এটিও `O(1)`।
- **Element Access `arr[index]`:** সরাসরি ইনডেক্স ধরে ডেটা পড়া। এটি `O(1)`।

### `O(N)` - Linear Time Operations (ইনপুট বাড়লে সময় বাড়ে)

যেসব অপারেশনে Array-এর প্রতিটি element-এর ওপর কাজ করতে হয় বা element-গুলোর ইনডেক্স রিক্যালকুলেট (shift) করতে হয়, তাদের complexity `O(N)`।

- **`shift()`:** Array-এর প্রথম থেকে element রিমুভ করে। এর ফলে বাকি সব element-কে এক ঘর বামে (Left shift) সরাতে হয়। তাই এটি `O(N)`।
- **`unshift()`:** Array-এর শুরুতে নতুন element যোগ করে। এর ফলে বাকি সব element-কে এক ঘর ডানে (Right shift) সরাতে হয়। তাই এটি `O(N)`।
- **Iterations (লুপ চালানো):** Array-এর শুরু থেকে শেষ পর্যন্ত চলা। যতগুলো element থাকবে, ততবার কাজ করতে হবে। যেমন: `for loop`, `forEach()`, `map()`, `filter()`, `reduce()` - এই সবগুলোই `O(N)`।
- **Searching (খোঁজা):** `indexOf()`, `includes()`, `find()`, `findIndex()` - এই মেথডগুলো Array-এর শুরু থেকে খুঁজতে থাকে। সবচেয়ে খারাপ অবস্থায় (Worst case) এগুলোকে পুরো Array চেক করতে হতে পারে, তাই এরা `O(N)`।
- **Modifying / Copying:** `slice()`, `splice()`, `concat()`, `reverse()` - এগুলোর ভেতরেও element-গুলোর ওপর দিয়ে লুপ চালাতে হয় বা কপি করতে হয়, তাই এরা `O(N)`।

### `O(N log N)` - Sorting

- **`sort()`:** জাভাস্ক্রিপ্টের বিল্ট-ইন সর্টিং মেথড সাধারণত `O(N log N)` কমপ্লেক্সিটি ব্যবহার করে (যেমন- V8 ইঞ্জিনে Timsort)।

---

## Major Array Methods Cheat Sheet

| Method                    | Time Complexity | Note (কারণ)                                               |
| :------------------------ | :-------------- | :-------------------------------------------------------- |
| **push()**                | `O(1)`          | শেষে যোগ হয়, re-indexing প্রয়োজন নেই।                     |
| **pop()**                 | `O(1)`          | শেষ থেকে বাদ যায়, re-indexing প্রয়োজন নেই।                |
| **shift()**               | `O(N)`          | প্রথম থেকে বাদ যায়, বাকি সব element বামে shift হয়।        |
| **unshift()**             | `O(N)`          | প্রথমে যোগ হয়, বাকি সব element ডানে shift হয়।             |
| **splice()**              | `O(N)`          | মাঝখান থেকে যোগ বা ডিলিট করলে shift করতে হয়।              |
| **slice()**               | `O(N)`          | নতুন Array তৈরি করে element কপি করতে হয়।                  |
| **concat()**              | `O(N)`          | দুটি Array-এর element-কে যুক্ত করার জন্য iterate করতে হয়। |
| **forEach/map/filter**    | `O(N)`          | প্রতিটি element-এর ওপর ফাংশন চালাতে হয়।                   |
| **find/indexOf/includes** | `O(N)`          | (Worst case) কাঙ্ক্ষিত ডেটা খুঁজতে পুরো Array ঘুরতে হয়।   |
| **sort()**                | `O(N log N)`    | সাধারণত Timsort বা Merge Sort ব্যবহার করে।                |
| **arr[index]**            | `O(1)`          | সরাসরি memory address থেকে ডেটা পড়া যায়।                  |

---

## Summary (সারসংক্ষেপ)

- Array-এর শেষে ডেটা যোগ বা বিয়োগ করা (`push`/`pop`) অনেক দ্রুত, কারণ এগুলো `O(1)`।
- Array-এর শুরুতে ডেটা যোগ বা বিয়োগ করা (`unshift`/`shift`) ধীরগতির, কারণ এতে ভেতরের উপাদানগুলোর ইনডেক্স পরিবর্তন (shift) করতে হয়, যা `O(N)`।
- Array-তে লুপ চালানো বা ডেটা খোঁজা (`map`, `filter`, `find`) মূলত `O(N)`।
- Array-কে সর্ট করার মেথড `sort()` সাধারণত `O(N log N)` সময় নেয়।

---

## Interview Preparation (Top 5 Questions)

1. **Question:** Why is `push()` considered an `O(1)` operation, while `unshift()` is `O(N)`?  
   **Answer:** `push()` adds an element to the end of the array, which does not affect the index of existing elements, operating in constant time `O(1)`. `unshift()` adds an element to the beginning, forcing all existing elements to shift their index by one position, making it an `O(N)` linear operation.

2. **Question:** What is the worst-case time complexity of the `splice()` method when removing an element from the middle of an array?  
   **Answer:** The worst-case time complexity is `O(N)`. When an element is removed from the middle, all the elements succeeding it must be shifted to the left to fill the gap, taking linear time relative to the number of elements moved.

3. **Question:** Does JavaScript's `arr.indexOf()` operate in `O(1)` or `O(N)` time? Why?  
   **Answer:** `arr.indexOf()` operates in `O(N)` time. It iterates sequentially from the beginning of the array checking each element until it finds a match. In the worst-case scenario (item not found or is the last element), it has to traverse the entire array.

4. **Question:** Explain the time complexity of the `arr.sort()` method in JavaScript.  
   **Answer:** The JavaScript specification does not mandate a specific sorting algorithm, but modern engines like V8 (Chrome/Node.js) implement Timsort, which yields a worst-case and average time complexity of `O(N log N)`.

5. **Question:** If you frequently need to check whether a specific item exists, should you store your items in an Array or an Object/Set?  
   **Answer:** You should store them in an Object or a `Set`. Checking for an item's existence in an Array (using `includes` or `indexOf`) is `O(N)`. However, looking up a property in an Object or checking a `Set` (using `has`) is generally an `O(1)` operation due to hash table implementations under the hood.
