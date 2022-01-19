# 第一天leetcode

## 两数之和

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i in range(0, len(nums)):
            if i < target:
                for j in range(i+1, len(nums)):
                    if (nums[i] + nums[j]) == target:
                        return i, j
```

暴力解决

时间复杂度为$O(n^2)$

## 有效括号

使用堆栈来做

```python
class Solution(object):
    def isValid(self, s):
        """
        :type s: str
        :rtype: bool
        """
        m = False
        stack = [0]
        if len(s) == 1:
            m = False
        if(s[-1] == ']')or(s[-1] == '}')or(s[-1] == ')'):
            m = True
            for i in s :
                if(i == '(')or(i == '{')or(i == '['):
                    stack.append(i)
                if (i == ')'):
                    if(stack[-1] == '('):
                        del stack[-1]
                        m = True
                    else:
                        m = False
                        return m
                if (i == ']'):
                    if (stack[-1] == '['):
                        del stack[-1]
                        m = True
                    else:
                        m = False
                        return m
                if (i == '}'):
                    if(stack[-1] == '{'):
                        del stack[-1]
                        m = True
                    else:
                        m = False
                if m == False:
                    break
        if len(stack) != 1:
            m = False
        return m
```

## 转小写

```java
class Solution {
    public String toLowerCase(String s) {
        return s.toLowerCase();
    }
}
```

直接调用API

