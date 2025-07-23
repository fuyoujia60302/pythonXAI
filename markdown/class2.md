---

# 🐍 今天的 Python 上課筆記

## 🧮 1. 輸入數字 & 判斷分數等第

我們用 `Streamlit` 做了一個可以輸入數字的小程式！

```python
import streamlit as st

number = st.number_input("請輸入一個數字", step=1, min_value=0, max_value=100)
st.write(f"你輸入的數字是: {number}")
```

### 💯 分數判斷：

我們還學會了怎麼判斷成績對應的等第（像是A、B、C…）

```python
score = st.number_input("請輸入分數", step=1, min_value=0, max_value=100)

if score >= 90:
    st.write("你的等第是A")
elif score >= 80:
    st.write("你的等第是B")
elif score >= 70:
    st.write("你的等第是C")
elif score >= 60:
    st.write("你的等第是D")
else:
    st.write("你的等第是F")
```

👉 用 `if`、`elif`、`else` 來做選擇判斷，就像玩問答遊戲一樣，條件符合就顯示對應結果。

---

## 🔘 2. 點按鈕 + 有趣特效！

```python
st.button("點我", key="button1")

if st.button("點我", key="button2"):
    st.balloons()

if st.button("點我", key="button3"):
    st.snow()
```

🎈 點第二個按鈕會有氣球！
❄️ 點第三個按鈕會下雪！

---

## 🔁 3. `for` 迴圈：重複做事情的魔法

我們學了 `for` 迴圈，它可以幫我們重複做一樣的事情！

```python
for i in range(10):
    print(i)  # 會印出 0 到 9
```

```python
for i in range(2, 6):
    print(i)  # 印出 2, 3, 4, 5
```

```python
for i in range(2, 10, 2):
    print(i)  # 印出 2, 4, 6, 8（每次加2）
```

---

## 🗼 4. 數字金字塔 & 箭頭金字塔

### 🔢 數字金字塔

```python
num1 = st.number_input("請輸入第一個數字(1-9)", step=1, min_value=1, max_value=9)

for i in range(1, num1 + 1):
    st.write(str(i) * i)
```

🌟 輸入 5，會印出：

```
1
22
333
4444
55555
```

### 🏹 箭頭金字塔

````python
num2 = st.number_input("請輸入箭頭的層數", step=1, min_value=1)

# 建立箭頭圖形
arrow = ""
for i in range(1, num2 + 1):
    arrow = arrow + (" " * (num2 - i) + "*" * (i * 2 - 1) + "\n")
for i in range(num2):
    arrow = arrow + (" " * (num2 - 1) + "*" + "\n")

st.write(f"""```{arrow}```""")
````

🎯 這段會畫出一個像箭頭的金字塔圖案，用 `*` 做出來！

---

## 📦 5. 串列（List）：把很多東西裝在一起！

### 🧺 我們可以用方括號 `[]` 裝東西：

```python
L1 = []  # 空的串列
L2 = ["蘋果"]
L3 = ["蘋果", "香蕉", "橘子"]
L4 = [1, 2, 3, 4, 5]
L5 = [1, "蘋果", True, 3.14]  # 什麼都能放
L6 = [1, 2, 3, ["蘋果", "香蕉"]]  # 裡面還可以放一個串列
```

### 🎯 如何拿出裡面的東西：

```python
print(L6[1])        # 印出 2（因為從0開始算）
print(L6[3][0])     # 印出 "蘋果"（第4個東西裡的第一個）
```

### 🧩 範圍取資料：

```python
L = [1, 2, 3, "a", "b", "c"]
print(L[1:4:2])  # 取出第2到第4個，每隔1個取一次 → [2, "a"]
print(L[1:4])    # 取第2到第4個 → [2, 3, "a"]
print(L[::2])    # 每隔一個取一次 → [1, 3, "b"]
```

---

## 🎉 總結

今天我們學了好多東西：

- 怎麼輸入數字、按鈕特效 🎈❄️
- 怎麼用 `if` 判斷等第 💯
- 用 `for` 迴圈重複做事情 🔁
- 畫出金字塔圖案 🗼
- 用串列把資料收集起來 📦

---
