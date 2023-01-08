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



# 字符串

> 切片的min和max 
>
> + nums[起始位置:截取长度]
> + 最终会截取的字符个数 = 截取长度 - 起始位置

```
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



# Map

> 初始化map

```
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

