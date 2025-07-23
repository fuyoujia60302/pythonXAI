---

## 🧮 class3-1：關於「清單（List）」的基礎用法

### 什麼是清單？

清單就像是可以裝很多東西的箱子，我們可以把水果、數字、字母放進去。

```python
print(len(["蘋果", "香蕉"]))  # 看箱子裡有幾樣東西
```

### 用 `for` 一個個把清單裡的東西拿出來：

```python
l = [1, 2, 3]
for i in range(len(l)):
    print(l[i])  # 用位置拿東西出來
```

```python
for element in l:
    print(element)  # 直接拿東西，不管位置
```

### 改變清單裡的東西：

```python
l[0] = "A"
l[2] = "c"
print(l)  # 把第一個和第三個東西換掉
```

### 認識「a = b」是什麼意思？

```python
a = [10, 20, 30]
b = a  # b 是 a 的「分身」
b[1] = 200
print(a)  # a 也會跟著改！
```

### 如果不想兩個清單連動，要用「複製」：

```python
c = [40, 50, 60]
d = c[:]  # 複製 c
d[1] = 500
print(c)  # 原本的 c 不會被改
```

### 常用的清單功能：

```python
l1.append(4)  # 加東西進去
l2.remove("b")  # 移除某個東西（只刪第一個找到的）
l3.pop()  # 拿出最後一個
l4.pop(1)  # 拿出指定位置的東西
l5.sort()  # 把數字排大小
l6.sort()  # 把字母排順序
```

---

## 🖼️ class3-2：用 Streamlit 做小工具

### 把網頁分成欄位，放按鈕進去：

```python
col1, col2 = st.columns(2)
col1.button("按鈕1")
col2.button("按鈕2")
```

### 欄位可以有不同寬度，還可以加文字：

```python
col3, col4, col5 = st.columns([1, 2, 3])
with col3:
    st.write("欄位3")
    st.button("按鈕3")
```

### 接收使用者輸入的文字：

```python
text = st.text_input("請輸入文字")
st.write("你輸入的文字是：", text)
```

### 使用「session state」來記住數字：

```python
if "var1" not in st.session_state:
    st.session_state.var1 = 1

if st.button("add 1 to var1"):
    st.session_state.var1 += 1
    st.rerun()  # 重新整理畫面
```

---

## 🍔 class3-3：做一個簡單的點餐機

### 加入餐點：

```python
food = col1.text_input("請輸入餐點")
if col2.button("加入"):
    st.session_state.order.append(food)
    st.rerun()
```

### 顯示已點的清單，還能刪除：

```python
for i in range(len(st.session_state.order)):
    col3.write(st.session_state.order[i])
    if col4.button("刪除", key=i):
        st.session_state.order.pop(i)
        st.rerun()
```

---

## 🔁 class3-4：while 和 for 迴圈 & 隨機數

### while 迴圈：一直做事情直到條件不成立

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

### `break`：遇到就立刻跳出迴圈

```python
while i < 5:
    if i == 3:
        break
```

### 用 `random` 做出 1\~3 的隨機數：

```python
n = random.randrange(1, 4)  # 可能出現 1、2、3
```

### 統計每個數字出現幾次：

```python
count1, count2, count3 = 0, 0, 0
# 看 30 次的結果各出現幾次
```

### 更多隨機數指令：

```python
random.randrange(0, 10, 2)  # 0 到 9 的偶數
random.randint(10, 20)  # 10 到 20 的整數
```

---

## 🎯 class3-5：猜數字遊戲

```python
target = random.randint(1, 100)

while True:
    guess = int(input("請輸入一個數字: "))
    if guess < target:
        print("再大一點")
    elif guess > target:
        print("再小一點")
    else:
        print("猜中了")
        break
```

---

## 🎁 class3-6：一番賞模擬器

### 準備一百張獎券，有一張是中獎的：

```python
table = [0]*100  # 一開始都是 0
table[random.randint(1, 100) - 1] = 1  # 放中獎券
```

### 一直抽獎直到抽到中獎：

```python
while True:
    pick = random.randint(1, 100)
    if table[pick - 1] == 2:
        print("已經抽過了")
    elif table[pick - 1] == 1:
        print("恭喜你中獎！")
        break
    else:
        print("沒有中獎")
    table[pick - 1] = 2  # 標記為已抽過
```

---

這就是你今天上課學到的全部內容 ✨
簡單來說，你已經學會了：

- 清單怎麼用
- 怎麼跑回圈
- 隨機數怎麼做
- Streamlit 做網頁小工具
- 點餐機、猜數字、一番賞模擬器！
