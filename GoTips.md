# 数组

> 特定位置初始化

```go
nums := [4]int{1:-1,3:-1}
```

> 二维数组初始化

```go
answer1 := make([][]int, row)
for i := range answer1 {
    answer1[i] = make([]int, column)
}
```

> 添加二维数组

```go
mp := map[string][]string{}
ans := make([][]string,0,len(mp))
// 直接添加新的一个一维数组，也就是增加了行数
// 不是在一个一维数组后面添加，也就书不是增加列数
for _,v := range mp {
    ans = append(ans,v)
}
// ans = [["...","...","..."],["...","..."],["..."]]
```



# 字符串

> 切片的min和max 
>
> + nums[起始位置:截取长度]
> + 最终会截取的字符个数 = 截取长度 - 起始位置

```go
s := "abc"
fmt.Println(s[1:2]) // b
fmt.Println(s[1:3]) // bc
```

> 字符串与byte转换

```go
bs,ts := []byte(s),[]byte(t) 			 // 字符串 -> byte
bStr,tStr := string(bs[:]),string(ts[:]) // byte  -> 字符串
```

> 字符串比较

```go
if srt1 == str2 { ... } //区分大小写
fmt.Println(strings.EqualFold("GO","go")) // 不区分大小写
```

> 字符串中字符排序

```go
s := []byte(str)
sort.Slice(s,func(i,j int) bool { return s[i] < s[j]} )
sortedStr := string(s)
```



# Map

> 初始化map

```go
sl,tl := len(s),len(t)          // 获取字符串长度
tm := make(map[rune]int,tl)     // 初始化一个map数据结构
```

> 判断map中元素是否存在

```go
if _,ok := tm[v]; ok {
	tm[v] = i // 记录出现的位置
	fmt.Println(v,i)
}
```



# Tips

> + 再设置一个待求的**min**是，最开始设置为**len(nums) + 1**
> + 再设置一个待求的**max**是,最开始设置为**0**



> goto的使用

```go
for i,v := range s {

    if _,ok := tm[v]; ok {
        // 判断t中字符串是否都出现了
        for _,vtm := range tm {
            if vtm == -1 {
                goto WALK // goto
            }
        }
    }

    WALK: 
}
```

