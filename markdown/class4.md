---

# 🐍 Python 課堂筆記（第四堂）

## 📘 第 4-1 節：字典（dictionary）

字典就像是一個裝東西的盒子，你可以用「名字」找到裡面的「東西」。

```python
d2 = {"apple": "蘋果"}
d3 = {1: "one", 2: "two", 3: "three"}
```

🔍 查找資料：

```python
print(d2["apple"])  # 會印出：蘋果
print(d3[2])        # 會印出：two
```

🔄 看所有的 key 或 value：

```python
for key in d3.keys():      # 只印出鍵
    print(key)

for value in d3.values():  # 只印出值
    print(value)

for key, value in d3.items():  # 同時印出鍵和值
    print(f"{key} : {value}")
```

🛠️ 修改字典內容：

```python
d3[2] = "二"           # 改掉原本的 two
d3[4] = "four"         # 新增一筆資料
v = d3.pop(1)          # 把 key=1 的資料刪除
```

❓ 判斷某個東西在不在裡面：

```python
print(2 in d3)           # True
print(1 in d3)           # False（被刪掉了）
print("three" in d3)     # False（因為 "three" 是值，不是鍵）

fruits = ["apple", "banana", "cherry"]
print("banana" in fruits)  # True
```

---

## 📘 第 4-2 節：Streamlit 圖片展示

我們用 Streamlit 做一個可以顯示圖片的簡單網頁！

```python
import streamlit as st
import os

file_path = "image"
files = os.listdir(file_path)
st.write(files)  # 顯示圖片檔案清單

img_size = st.number_input("圖片大小", min_value=50, max_value=500, value=300, step=50)

for img in files:
    st.image(f"{file_path}/{img}", width=img_size)
```

---

## 📘 第 4-3 節：購物平台小專案

這是一個簡單的購物平台，可以：

- 顯示商品圖片、價格和庫存
- 點按鈕就能「購買」
- 新增庫存數量

🔧 重點功能：

```python
st.session_state.products = {}  # 存放商品資訊
```

🔍 每個商品會顯示：

- 圖片
- 價格
- 庫存
- 購買按鈕（會減少庫存）

➕ 底下還可以新增商品的庫存數量。

---

## 📘 第 4-4 節：函式（function）

函式就像是小機器，可以把一些動作包在一起，之後想用就叫它。

```python
def hello():
    print("hello")

def hello2(name):
    print("hello " + name)

def my_max(a, b):
    if a > b:
        return a
    else:
        return b
```

🧮 圓形面積計算：

```python
def calculate_circle_area(r, pi=3.14, scale=1):
    return (r * scale) ** 2 * pi
```

📏 全域變數 / 區域變數說明：

```python
def calculate_square_area():
    area = length**2
```

📏 計算距離：

```python
def distance(x1, y1, x2, y2):
    return ((x2 - x1) ** 2 + (y2 - y1) ** 2) ** 0.5
```

---

## 📘 第 4-5 節：擲骰子遊戲

我們做了一個骰子機器，可以丟出很多次骰子，並統計出現的次數！

```python
import random

def roll_dice(n):
    save = []
    for i in range(n):
        number = random.randint(1, 6)
        save.append(number)
    return save
```

🔢 數幾次每個點數出現：

```python
for num in outcome:
    if num == 1:
        n1 += 1
    elif num == 2:
        n2 += 1
    ...
```

📊 最後印出：

- 每個點數出現幾次
- 丟骰子結果清單

---

📌 **小提醒：**

- `print()` 是用來顯示東西的
- `def` 是定義函式
- `for` 是重複做很多次
- `if` 是判斷式（如果...就...）

---
