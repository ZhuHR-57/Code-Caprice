# 链表

## 删除元素

思路：头指针 + 头指针代理

```go
// 头指针
newHead := &ListNode{Next: head}
// 头指针代理
for tmp := newHead; tmp.Next != nil;{...}
```

