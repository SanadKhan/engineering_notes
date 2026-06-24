# Valid Anagram

## Problem

Given two strings `s` and `t`, return `true` if the two strings are anagrams of each other, otherwise return `false`.

An **anagram** is a string that contains the exact same characters as another string, but the order of the characters can be different.

## Problem Link

https://neetcode.io/problems/is-anagram/question

## Pattern

[[Hashing]]/ Frequency Count(Hash Map)

## Difficulty

Easy

## Key Observation

Order does not matter, frequency does.

## Initial Thought

Sort both strings and compare

## Better Approach

Use Frequency counter to count occurrence

## When I Got Stuck

Thought about using Set, but Set loses count info.

## Breakthrough

Realized anagram means character counts must match exactly.

## Takeaway

If duplicates matter → think HashMap, not HashSet.

## Complexity

Time: O()  
Space: O()

## Solution

```js
// Final clean solution
function validAnagrams(s, t) {
	if (s.length !== t.length) return false  
  
	const freq = {}  
	  
	for (let i = 0; i < s.length; i++) {  
	freq[s[i]] = (freq[s[i]] || 0) + 1  
	freq[t[i]] = (freq[t[i]] || 0) - 1  
	}  
	  
	for (let key in freq) {  
		if (freq[key] !== 0) return false  
	}  
	  
	return true
}
```

## Mistakes

Used hash set initially instead of hash map (frequency counter)

## Why This Works

Matching frequency either keeping on individual object Or same frequency obj. Same freq adds a small optimization.

## Similar Problems

- [[Contains Duplicate]]
    
## Pattern Notes

[[Hashing]]

## Tags

#dsa #easy #hashing #valid-anagram
