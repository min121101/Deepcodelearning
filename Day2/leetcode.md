# 第二天leetcode

## 349.求两个数组的交集

```python
class Solution:
    def intersection(self, nums1, nums2):
        return list(set(nums1) & set(nums2))    # 两个数组先变成集合，求交集后还原为数组
```

python的&可以求交集

## 88.合并两个有序数组

```python
class Solution:
    def merge(self, nums1, m, nums2, n):
        nums1[m:] = nums2
        nums1.sort()
```

按照题意数组切片然后sort一下

## 234.回文链表

```python
class Solution:
    def isPalindrome(self, head: ListNode) -> bool:
        vals = []
        current_node = head
        while current_node is not None:
            vals.append(current_node.val)
            current_node = current_node.next
        return vals == vals[::-1]
```

一个简单的堆栈即可

