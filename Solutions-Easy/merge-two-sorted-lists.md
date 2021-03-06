## Merge Two Sorted Lists

### Question

Merge two sorted linked lists and return it as a new list. 
The new list should be made by splicing together the nodes of the first two lists.

#### Example:
```shell
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
```

### Solution
```javascript
/**
 * Definition for singly-linked list.
 * function ListNode(val) {
 *     this.val = val;
 *     this.next = null;
 * }
 */
/**
 * @param {ListNode} l1
 * @param {ListNode} l2
 * @return {ListNode}
 */
var mergeTwoLists = function(l1, l2) {
    var l3 = new ListNode(null); //create dummy node to get started
    var prev = l3;
    
    while(l1 && l2){
        if(l1.val <= l2.val){
            prev.next = l1;
            l1 = l1.next;
        }else{
            prev.next = l2;
            l2 = l2.next;
        }
        prev = prev.next;
    }
    
    prev.next = l1 || l2;
    // -> if (!l1) { prev.next = l2;} -> if (!l2) { prev.next = l1;}
    
    return l3.next;
};
```
