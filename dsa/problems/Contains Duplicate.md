# Contains Duplicate

## Problem
Given an integer array nums, return true if any value appears more than once in the array, otherwise return false. 

## Problem Link ([Ref](https://neetcode.io/problems/duplicate-integer/question?list=neetcode150))

## Pattern
[[Hashing]] / Frequency Count 

## Difficulty
Easy 

## Key Observation
Need fast lookup to know if an element has been seen before.

Brute force comparison of each element with every other element would take O(n²).

Hashing reduces lookup to O(1).

## Initial Thought
Compare every number with every other number.

Realized repeated scanning is expensive.

## Better Approach
Store each visited element in a hash map/object.

If an element appears again, duplicate exists.

## When I Got Stuck
Initially thought frequency count was needed.

Realized only presence check is enough.

Can stop at first duplicate.

## Breakthrough
Questions asking:
- "have we seen this before?"
- "does this exist already?"

usually indicate HashSet / HashMap.

## Takeaway
Whenever:
- duplicate detection
- unique elements
- existence lookup

think Hashing first.

## Complexity
Time: O(n)
Space: O(n)

## Solution
```js
class Solution {
    hasDuplicate(nums) {
        if (nums.length < 2) return false;

        const seen = new Set();

        for (const num of nums) {
            if (seen.has(num)) return true;
            seen.add(num);
        }

        return false;
    }
}
```

## Mistakes

## Why This Works

## Similar Problems

- [[Valid Anagram]]
    

## Pattern Notes

[[Hashing]]

## Tags

#easy #dsa #hashing #contains-duplicate  