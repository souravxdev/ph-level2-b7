# Visual Comparison of Different Time Complexity

## মূল কনসেপ্ট (Core Concepts)

- **Worst Case Scenario:** Time complexity হিসাব করার সময় আমরা সবসময় সবচেয়ে খারাপ অবস্থা (Worst case) বিবেচনা করি। অর্থাৎ, একটি অ্যালগরিদম সর্বোচ্চ কতটুকু সময় নিতে পারে, সেটাই আমাদের মূল ফোকাস।
- **Drop Constants (ধ্রুবক বাদ দেওয়া):** Time complexity-তে যেকোনো constant value বা ধ্রুবক সংখ্যাকে ignore করা হয়। যেমন: `O(2N)` হয়ে যায় `O(N)`।

---

## বিভিন্ন Time Complexity এর উদাহরণ (Examples in Code)

### 1. `O(1)` - Constant Time

ইনপুটের সাইজ যত বড়ই হোক না কেন, execution time সবসময় একই থাকবে। যদি কোনো লুপ একটি নির্দিষ্ট সংখ্যা পর্যন্ত চলে (যেমন ৫ বার), তবে সেটি ইনপুটের উপর নির্ভরশীল নয়, তাই সেটিও `O(1)`।

```javascript
// Example 1: Array-এর নির্দিষ্ট index থেকে ডেটা পড়া
const arr = [1, 2, 3, 4, 5];
console.log(arr[2]); // O(1)

// Example 2: Object-এর নির্দিষ্ট property পড়া বা আপডেট করা
const obj = { name: "John", age: 30 };
obj.name = "Doe"; // O(1)

// Example 3: Constant Loop
const largeArr = [1, 2 /* ... up to 1000000 elements */];
for (let i = 0; i < 5; i++) {
  // এই লুপ সবসময় ৫ বারই চলবে, array এর সাইজ যাই হোক না কেন।
  console.log(largeArr[i]);
} // Overall O(1)
```

### 2. `O(N)` - Linear Time

যখন ইনপুটের সাইজ `N` এর সাথে সরাসরি লুপের পরিমাণ বাড়ে। Single loop বা JavaScript-এর বিল্ট-ইন লুপ মেথডগুলো সাধারণত `O(N)` হয়।

- **Examples:** Single `for` loop, `arr.map()`, `arr.forEach()`, `arr.find()`

```javascript
const n = 100;
for (let i = 0; i < n; i++) {
  // n times
  console.log(i);
} // O(N)
```

### 3. `O(N^2)` - Quadratic Time

যখন একটি লুপের ভেতর আরেকটি লুপ (Nested Loop) থাকে, তখন প্রতিটি বাইরের উপাদানের জন্য ভেতরের লুপটি সম্পূর্ণভাবে চলে।

- **Examples:** Nested `for` loop

```javascript
const n = 10;
for (let i = 0; i < n; i++) {
  // n times
  for (let j = 0; j < n; j++) {
    // n times
    console.log(i, j);
  }
} // O(N * N) => O(N^2)
```

### 4. Sibling Loops (পাশাপাশি লুপ)

যখন দুটি লুপ একটার ভেতর আরেকটা না থেকে পাশাপাশি থাকে, তখন তাদের execution time যোগ হয়।

```javascript
const n = 100;
const m = 50;

for (let i = 0; i < n; i++) { ... } // n times
for (let j = 0; j < m; j++) { ... } // m times
// Total time: n + m
```

**হিসাব করার নিয়ম:**

- যদি `n` অনেক বড় হয় `m` এর চেয়ে (`n > m`), তাহলে এটি হবে **`O(N)`** (কারণ ছোট value ignore করা হয়)।
- যদি `m` অনেক বড় হয় `n` এর চেয়ে (`m > n`), তাহলে এটি হবে **`O(M)`**।
- যদি `n` এবং `m` সমান হয় (`n = m`), তাহলে `n + n = 2n`। যেহেতু constant ignore করা হয়, তাই এটি হবে **`O(N)`**।

---

## Summary (সারসংক্ষেপ)

- অ্যালগরিদমের দক্ষতা পরিমাপে সবসময় **Worst Case** হিসাব করা হয়।
- Big-O calculation-এ **Constant values (ধ্রুবক)** সর্বদা ignore করা হয়।
- Object property access, Array index access এবং নির্দিষ্ট সংখ্যার লুপ হলো `O(1)`।
- Single লুপ, `map`, `forEach` হলো `O(N)`।
- Nested লুপ হলো `O(N^2)`।
- পাশাপাশি চলা (Sibling) লুপগুলোর ক্ষেত্রে সময় যোগ হয়, কিন্তু দিনশেষে সবচেয়ে বড় ইনপুট সাইজটিকেই (Dominant term) গ্রহণ করা হয়।

---

## Interview Preparation (Top 5 Questions)

1. **Question:** Why do we always consider the "worst-case scenario" when evaluating an algorithm's time complexity?  
   **Answer:** We consider the worst-case scenario (Big-O) because it provides an upper bound on the time the algorithm will take. It guarantees that the algorithm will never perform worse than this, ensuring predictability under maximum load.

2. **Question:** In Big-O notation, why do we drop constants (e.g., treating `O(2N)` as `O(N)`)?  
   **Answer:** Big-O notation is concerned with the _growth rate_ of the execution time as the input size approaches infinity, not the exact time. As `N` becomes very large, constant factors have an insignificant impact on the overall growth curve, so they are dropped to focus on the dominant term.

3. **Question:** What is the time complexity of accessing an element in an array by its index vs. finding an element using `arr.find()`?  
   **Answer:** Accessing an array element by its index (e.g., `arr[5]`) is an `O(1)` constant time operation. Finding an element using `arr.find()` requires iterating through the array elements one by one until the target is found, making it an `O(N)` linear time operation in the worst case.

4. **Question:** If you have two unnested (sibling) `for` loops, one running `N` times and the other running `M` times, what is the overall time complexity?  
   **Answer:** The overall time complexity is `O(N + M)`. If we know that one is significantly larger than the other, we drop the smaller term (e.g., if `N >> M`, it becomes `O(N)`). If `N` and `M` are approximately the same, it would be `O(2N)`, which simplifies to `O(N)` after dropping the constant.

5. **Question:** Does a `for` loop always result in an `O(N)` time complexity?  
   **Answer:** No, it depends on the condition of the loop. If a `for` loop runs a fixed number of times regardless of the input size (e.g., `for(let i=0; i<5; i++)`), its time complexity is `O(1)` because the number of operations is constant.
