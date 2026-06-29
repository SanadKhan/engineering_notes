# Two Sum

## Problem

Given an array of integers `nums` and an integer `target`, return the indices `i` and `j` such that `nums[i] + nums[j] == target` and `i != j`.

You may assume that _every_ input has exactly one pair of indices `i` and `j` that satisfy the condition.

Return the answer with the smaller index first.

**Example 1:**

```java
Input: 
nums = [3,4,5,6], target = 7

Output: [0,1]
```


Explanation: `nums[0] + nums[1] == 7`, so we return `[0, 1]`.

**Example 2:**

```java
Input: nums = [4,5,6], target = 10

Output: [0,2]
```

**Example 3:**

```java
Input: nums = [5,5], target = 10

Output: [0,1]
```

**Constraints:**

- `2 <= nums.length <= 1000`
- `-10,000,000 <= nums[i] <= 10,000,000`
- `-10,000,000 <= target <= 10,000,000`
- **Only one valid answer exists.**

## Problem Link

https://neetcode.io/problems/two-integer-sum/question?list=neetcode150

## Pattern

[[Hashing]]/ Frequency Count

## Difficulty

#easy 

## Key Observation

For every number x, the required pair is target - x.

## Initial Thought

Use nested loops and check every pair.  Tried for optimized solution.

## Better Approach

Use hash map to store the indices and check for its existence.

## When I Got Stuck

Could not identify why hashing fits here

## Breakthrough

Realized problem asks:  
"Have I seen the complement before?"

That is hashmap lookup.

## Takeaway

Whenever a problem asks for:
- pair sum
- complement
- previous occurrence

Think HashMap.
## Complexity

Time: O(n)  
Space: O(n)

## Solution

```js
// Final clean solution
function twoSum(nums, target){
    const indices={}
    for(let i=0; i<nums.length; i++) {
        indices[nums[i]] = i
    }
    for(let i=0; i<nums.length; i++){
        const diff = target - nums[i]
        if(indices[diff] !=undefined && indices[diff] != i) {
            return [i, indices[diff]]   
        }
    }
}

const input = [3,4,3,6]
const target = 6

console.log(twoSum(input, target))
```

## Mistakes

Can thought of mathematical expressions for the solution.

## Why This Works

For each number, check if its complement already exists.

## Similar Problems

- [[Valid Anagram]]
- [[Contains Duplicate]]   

## Pattern Notes

Hashing works well for:
- fast lookup
- complement lookup
- remembering previous values

## Tags

#dsa #hashing  #two-sum #arrays