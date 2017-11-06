## Problem

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

### Solution

We can solve this problem with O(N) time complexity using a HashMap. 

public int[] twoSum(int[] nums,
int target) {

/* array to return the result */
int[] arr = new int[2];

/* map for num and index pair */
Map<Integer, Integer> map = 
new HashMap<Integer, Integer>();

/* iterate through the array */
for (int i = 0; i < nums.length; i++) {

/* check if the map has an element which is
* equal to the difference between the
* target and current element */
Integer val = map.get(target
- nums[i]);
if (val == null) {
/* no match found, add the current item
* and index to map */
map.put(nums[i], i);
} else {
/* match found, update the index values */
arr[0] = val;
arr[1] = i;
break; // exit the loop
}
}
return arr;
}
Time Complexity: O(N)
The array is traversed only once. So the time complexity is directly proportional to the size of the array i.e. O(N).

Space Complexity: O(N)

O(1) + O(N) = O(N). O(1) for the variables and O(N) for the hashmap. For hashmap, with the increase of the number of entries, the hashmap's space will increase linearly. So space complexity of hashmap is O(N).

Difficulty: Easy