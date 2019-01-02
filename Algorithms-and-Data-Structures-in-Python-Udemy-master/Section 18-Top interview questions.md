# Reversing an array in-place
> [1,2,3,4,5]-->[5,4,3,2,1]

* Solution: Two pointer
```
def reverse_list(lst):
    p1=0
    p2=len(lst)-1
    while p1<p2:
        lst[p1],lst[p2]=lst[p2],lst[p1]
        p1+=1
        p2-=1
    return lst
```

# Palindrome problem
> A palindrome is a string thayt read the same froward and backward

* Solution: `[::-1]`
```
def check_palindrome(string)
    return string==''.join(string[::-1])# reversed(string)
```

# Integer reversing problem
> 1234-->4321

* Solution: `%, //`
```
def reversed_integer(num):
    reverse=0
    reminder=0
    while num>0:
        reminder=num%10
        reverse=reverse*10+reminder
        num=num//10
    return reverse
```

# Duplicates in an array
> get all duplicates from an array in O(N) in-place,where the integer values are smaller than the length of the array!
* Solution: absolute value
```
def duplicates(lst):
    for i in lst:
        if lst[abs(i)]>=0:
            lst[abs(i)]=-lst[abs(i)]
        else:
            print(i)
```
```
[z[i] for i in range(len(z)) if i == z.index(z[i])]
```
```
[item for item in set(my_list) if my_list.count(item) > 1]
```
# Possible subarray
> find out all possible subarray

```
def sub_lists(my_list):
	subs = [[]]
	for i in range(len(my_list)):
		n = i+1
		while n <= len(my_list):
			sub = my_list[i:n]
			subs.append(sub)
			n += 1
	
	return subs
```

# Anagram problem
> Check whether two words or phrases are anagrams or not 
> Example: restful--> fluster

* Solution: `sorted()`

```
def anagram(str1,str2):
    if len(str1)!=len(str2):
        return False
    str1=sorted(str1)
    str2=sorted(str2)
    return str1==str2
```
```
def is_anagram(str1, str2):
   return Counter(str1) == Counter(str2)
```
# Sum subarray (DP!!)
>  find the sum of contiguous subarray within a one-dimensional array of numbers which has the largest sum!
* Solution: 
  1. current_max=max(nums[i],current_max+nums)
  2. max_global=max(current_max,max_global)

```
def kadane_algorithm(nums):
    max_global=nums[0]
    max_current=nums[0]
    for i in range(1,len(nums)):
        max_current=max(nums[i],max_current+nums[i])
        max_global=max(max_current,max_global)
    return max_global
```

# Finding the middle node in a linked list
> Finding the middle node of a linked list without extra memory(in-place)

* Solution: two-pointers
```
def middle_node(self):
  slow_pointer=self.head
  fast_pointer=self.head
  while fast_pointer.next and fast_pointer:
      slow_pointer=slower_pointer.next
      fast_pointer=fast_pointer.next.next
  return slow
```
# Reverse a linked list
> in-place
* Solution: three pointers: previous,current,next
```
def reverse_linked_list(ll):
    current=self.head
    pre=None
    next=None
    while current:
        next=current.next
        current.next=pre
        pre=current
        current=next
    self.head=pre
```

# Max in a stack
> return maximum value in stack, use O(n) extra memory
* Solution: keep maximum value in another stack
```
if data>self.max_stack[-1]:
  self.max_stack.append(data)
else:
  seld.max_stack.append(maxstack[-1])
 
# Queue with stack problem
>  design a queue abstract data type with the help of stacks

* Solution: pop enqueue_stack to push dequeue_stack
```
def enqueue(self):
    self.enqueue_stack.append(data)
def dequeue(self):
    if len(self.dequeue_stack)==0:
      while len(self.enqueue_stack)!=0:
            self.dequeue_stack.append(self.enqueue_stack.pop())
    return self.dequeue_stack.pop()
```
* Solution:  Recursive
```
def dequeue(self):
    if len(self.stack)==1:
        return self.stack.pop()
     item=self.stack.pop
     dequeue_item=dequeue()
     self.stack.append(item)
     return dequeue_item
```
# Compare binary trees
>Returns true if the trees are identical (same topology with same values in the nodes) otherwise it returns false
* Solution:Recursive
```
def compare_trees(self,node1,node2):
    if not node1 or not node2:# topology
        return node1==node2
    if node1.data!-node2.data:$ value
        return False
     return self.compare_trees(node1.left,node2.left) and self.compare_trees(node1.right,node2.right)
```
