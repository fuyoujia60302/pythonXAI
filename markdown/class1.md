---

## 🐍 Python 語言入門小筆記

### 💬 註解是什麼？

程式裡的註解不會被電腦執行，是給人看的文字。

- `#` 是單行註解，像這樣：

  ```python
  # 這是一行註解
  ```

- 三個雙引號 `"""` 可以寫多行註解：

  ```python
  """
  這是
  多行
  註解
  """
  ```

---

### 🖨️ 用 `print()` 把東西顯示出來

```python
print(123)  # 印出一個數字
print(3.14)  # 印出小數
print(True)  # 印出布林值（真的）
print(False)  # 印出布林值（假的）
print("Hello World!")  # 印出文字
```

---

### 🧠 變數是什麼？

變數就像一個盒子，可以放資料進去！

```python
a = 10
print(a)  # 印出 10

a = "apple"
print(a)  # 現在變成 "apple" 這個字
```

---

### ➕➖➗✖️ 算數運算

```python
print(7 + 3)  # 加法：10
print(7 - 3)  # 減法：4
print(7 * 3)  # 乘法：21
print(7 / 3)  # 除法：2.333...
print(7 // 3)  # 整數除法：2
print(7 % 3)  # 餘數：1
print(2**3)  # 次方：2的3次方 = 8
```

---

### 🧩 字串 (文字) 小技巧

```python
s1 = "Hello"
s2 = "World"
s3 = s1 + " " + s2  # 字串加在一起
print(s3)  # 印出 Hello World

print(s1 + s2 * 3)  # 印出 HelloWorldWorldWorld
```

---

### 🧓 f-string：更方便的字串

```python
name = "Python"
age = 31
print(f"我是{name}, 今年{age}歲")  # 印出：我是Python, 今年31歲
```

---

### 📏 `len()` 可以算出字串長度

```python
print(len("Hello"))  # 5
print(len(""))  # 0，因為裡面沒東西
```

---

### 🔍 `type()` 可以看資料型別

```python
print(type(True))  # bool (布林值)
print(type(123))  # int (整數)
print(type(123.0))  # float (小數)
print(type("Hello"))  # str (字串)
```

---

### 🔁 轉換資料型別

```python
print(int(True))  # 轉成整數：1
print(float("123"))  # 轉成小數：123.0
print(str(1000))  # 轉成字串："1000"

print(bool(0))  # False
print(bool(1))  # True
print(bool(""))  # False，因為字串是空的
print(bool("hello"))  # True，有內容就是 True
```

---

### 🧑‍💻 `input()`：請使用者輸入東西

```python
get = input("請輸入一些內容: ")
print(get)
print(type(get))  # 不管輸入什麼，input 拿到的都是字串
```

---

### ⭕ 計算圓面積的小練習

```python
r = int(input("請輸入圓的半徑: "))
area = 3.14 * r**2
print(f"圓的面積為: {area}")
```

---

### 🌐 Streamlit：做簡單的網頁畫面！

```python
import streamlit as st

st.title("這是標題")
st.write("這是 write 寫的內容")
st.text("這是 text 寫的內容")
```

#### Markdown 是什麼？

Markdown 是一種簡單的排版語言，可以讓文字變漂亮：

```python
st.markdown("""
* **粗體文字**
* *斜體文字*
* [這是連結](https://www.example.com)
""")
```

也可以加上不同大小的標題：

```markdown
# 標題 1

## 標題 2

### 標題 3

#### 標題 4
```

還可以加上程式碼框：

```python
print("Hello World!")
```
