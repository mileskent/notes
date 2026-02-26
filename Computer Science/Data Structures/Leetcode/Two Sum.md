---
date: 2026-02-26
aliases: 1. Two Sum
---
# Prompt
Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have **_exactly_ one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

* **Constraints:**
	- `2 <= nums.length <= 104`
	- `-109 <= nums[i] <= 109`
	- `-109 <= target <= 109`

# Examples
* **Example 1:**
	* **Input:** nums = \[2,7,11,15\], target = 9
	* **Output:** \[0,1\]
	* **Explanation:** Because nums\[0\] + nums\[1\] == 9, we return \[0, 1\].
* **Example 2:**
	* **Input:** nums = \[3,2,4\], target = 6
	* **Output:** \[1,2\]
- **Example 3:**
	- **Input:** nums = \[3,3\], target = 6
	- **Output:** \[0,1\]

# Solution
In [[C++]]
```cpp
vector<int> twoSum(vector<int>& nums, int target) {
	unordered_map<int, int> num2index;
	for (int i = 0; i < nums.size(); ++i) {
		int num = nums.at(i);
		int complement = target - num;
		if (num2index.contains(complement)) {
			return {num2index[complement], i};
		}
		num2index[num] = i;
	}
	return {};
}
```

## Explanation
The goal is to find two numbers in the array that sum to the given target. 

Iterate through the input array, considering what value for each number would sum to the target. We call this complementary number the "complement". We store the complement and the index of the number, so that if we find the complement later on, we can check by inspecting the keys of the map, which are all complements. Eventually, we will hit a number where its complement already exists in the map. We can then check the value for that key to get the index of the other number. 

## [[Big O]] Analysis
### [[Time Complexity]]
The worst case time complexity of this solution is $O(n)^*$, as we loop $n$ times through the input, and within each loop we check if the complement exists within the [[HashMap]], and we store a key value pair into the map, which are both $O(1)^*$. See [[Amortized Notation]].
### [[Auxiliary Space Complexity]]
The auxilliary space complexity is $O(n)$, as we use a HashMap, which in the worst case, would be of $n-1$ length.

