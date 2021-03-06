## Remove Duplicates from Sorted Array

### Question

Given a sorted array nums, remove the duplicates in-place such that each element appear only once and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array** in-place with O(1) extra memory.

#### Example:
<pre>
Given nums = <b>[1,1,2]</b>,

Your function should return length = <b>2</b>, with the first two elements of nums being <b>1</b> and <b>2</b> respectively.

It doesn't matter what you leave beyond the returned length.
</pre>

<pre>
Given nums = <b>[0,0,1,1,1,2,2,3,3,4]</b>,

Your function should return length = <b>5</b>, with the first five elements of nums being modified to <b>0</b>, <b>1</b>, <b>2</b>, <b>3</b>, and <b>4</b> respectively.

It doesn't matter what values are set beyond the returned length.
</pre>

#### Clarification:

Confused why the returned value is an integer but your answer is an array?

Note that the input array is passed in by **reference**, which means modification to the input array will be known to the caller as well.

Internally you can think of this:

```shell
// nums is passed in by reference. (i.e., without making a copy)
int len = removeDuplicates(nums);

// any modification to nums in your function would be known by the caller.
// using the length returned by your function, it prints the first len elements.
for (int i = 0; i < len; i++) {
    print(nums[i]);
}
```

### Solution
```javascript
/**
 * @param {number[]} nums
 * @return {number}
 */
var removeDuplicates = function(nums) {
    for(var i=0; i< nums.length; i++){
        for(var j = i+1; j< nums.length; j++){
            if(nums[j] == nums[i]){
                nums.splice(j,1);
                j--; //not skip the next item in the array.
            }
        }
    }
    console.log(nums);
};
```
