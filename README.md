# 大便程式碼原則 State-of-the-Art Shitcode Principles

[![State-of-the-art Shitcode](https://img.shields.io/static/v1?label=State-of-the-art&message=Shitcode&color=7B5804)](https://github.com/trekhleb/state-of-the-art-shitcode)

這是業界最先進的大便程式碼原則，你應該符合這些準則，才能算是完美的大便程式碼。

# 0.取得時髦的勳章

如果你的專案有完整遵照大便程式碼原則，那你就可以使用 "state-of-the-art shitcode" 徽章。

[![State-of-the-art Shitcode](https://img.shields.io/static/v1?label=State-of-the-art&message=Shitcode&color=7B5804)](https://github.com/trekhleb/state-of-the-art-shitcode)

# 💩1. 使用容易混淆的變數名稱

> 少打一點字，多點時間思考。

Good 👍🏻

```python
a = 42
```

Bad 👎🏻

```python
age = 43
```

# 💩2. 使用不同命名風格

> 為「不同」慶祝！

Good 👍🏻

```python
wWidth = 640
h_height = 480
```

Bad 👎🏻

```python
window_width = 640
windows_height = 480
```

# 💩3. 永遠，永遠，永遠都不要下註解

> 不要讓任何人讀懂你的程式碼。

Good 👍🏻

```python
cloth = list(input())
```

Bad 👎🏻

你的註解中，應該要說「為什麼」而不是單純的「做什麼」，要讓別人可以理解這行程式碼背後的邏輯。

```python
# Cause str can't assign value with specific index, but list can do.
cloth = list(input())
```

# 💩4. 永遠都要用你的母語去下註解

> 如果你違反了前面的「不要下註解」原則，至少你還可以試試看這個。在寫註解時盡量使用自己的母語或是熟悉的語言，不要使用英文去寫，自己看得懂比較重要。

Good 👍🏻

```python
# 如果發生 Error 時，就隱藏 modal。
toggle_modal(False)
```

Bad 👎🏻

```python
# Hide modal window on error.
toggle_modal(False)
```

# 💩5. 盡可能的使用各種的格式化風格

> 跟別人不一樣，就是你獨特魅力！

Good 👍🏻

```python
i = ['tomato', 'onion', 'mushrooms']
d = [ "ketchup", "mayonnaise" ]
```

Bad 👎🏻

```python
i = ["tomato", "onion", "mushrooms"]
d = ["ketchup", "mayonnaise"]
```

# 💩6. 盡可能的把程式寫在同一行。

Good 👍🏻

```python
leap_year = [i for i in list(map(int(i) + 1911, input().split(", "))) if i % 4 == 0 and i % 100 != 0 or year % 400 == 0]
```

Bad 👎🏻

```python
year = list(map(int(i) + 1911, input().split(", ")))
leap_year = list()
for i in year:
    if (i % 4 == 0 and i % 100 != 0) or year % 400 == 0:
        leap_year.append(i)

```

# 💩7. 噓！不要讓別人發現錯誤

> 不管怎樣，發生錯誤時沒有必要讓所有人都知道。沒有日誌檔、沒有錯誤提示，讚啦。

Good 👍🏻

```python
try:
    ...
except:
    ...
finally:
    ...
```

Bad 👎🏻

```python
try:
    ...
except NameError as NE:
    print("Name is not defined!")
    print(NE)
finally:
    ...
```

# 💩8. 廣泛的使用全域變數

> 全域變數超好用，函式不用一直傳參數，方便多了。

Good 👍🏻

```python
x = [5, 3]
def square():
    x[0] = x[0] ** 2

square() # Now x is 25
```

Bad 👎🏻

```python
x = [5, 3]
def square(num):
    return num ** 2

x[0] = square(x[0]) # Now x is 25
```

# 💩9. 宣告沒有要使用的變數

> 以防萬一，說不定自己之後會用到。

Good 👍🏻

```python
def sum(a, b, c):
    timeout = 1300
    result = a + b
    return result
```

Bad 👎🏻

```python
def sum(a, b, c):
    return a + b
```

# 💩10. 不要使用型態提示

Good 👍🏻

```python
def sum(a, b):
    return a * b

guess_what = sum("1", 5) # it work! but it's weird.
guess_what_again = sum([0], "5"); # Error
```

Bad 👎🏻

```python
def sum(a: int, b: int): -> int:
    if not isinstance(a, int) or not isinstance(b, int):
        return None

    return a * b

guess_what = sum("1", 5); # return None
```

# 💩11. 就算程式碼不會執行，一樣要先保留

> 永遠都要有的 B 計畫！

Good 👍🏻

```python
def square(num):
    if not isinstance(num, int):
        return None
    else:
        return num ** 2

    return None # 這就是你的B計畫！
```

Bad 👎🏻

```python
def square(num):
    if not isinstance(num, int):
        return None

    return num ** 2
```

# 💩12. 金字塔萬歲

> 寫程式要想翱翔在空中的鳥一樣，飛行隊伍要排好！

Good 👍🏻

```python
def some_function():
    if condition1:
        if condition2:
            for i in range(10):
                print(i)

```

Bad 👎🏻

```python
def some_function():
    if not condition1 or not condition2:
        return None

    for i in range(10):
        print(i)
```

# 💩13. 縮排沒差啦

Good 👍🏻

```python
fruits = ['apple',
  'orange', 'grape', 'pineapple']
toppings = ['syrup', 'cream',
                    'jam',
                    'chocolate']
desserts = []
for f in fruits:
    for t in toppings:
        desserts.append([f,
            t]
        )


```

Bad 👎🏻

```python
fruits = ['apple', 'orange', 'grape', 'pineapple']
toppings = ['syrup', 'cream', 'jam', 'chocolate']
desserts = []

for f in fruits:
    for t in toppings:
        desserts.append([f, t])

```

# 💩14. 不需要控管套件資訊

> 為什麼要鑽牛角尖，過去的就讓它過去吧，舊的不去新的不來。

Good 👍🏻

```bash
$ ls

requirements.txt
```

Bad 👎🏻

```bash
$ ls

requirements.txt
requirements-lock.txt
```

# 15. 布林值變數命名為 flag

Good 👍🏻

```python
flag = True
```

Bad 👎🏻

```python
is_done = False
is_empty = False
```

# 16. 函式內的程式碼越長越好

> 不要將你的程式碼依照功能性去做拆分，假如哪天 IDE 的搜尋功能壞掉了，你該如找到那個重要的函式？

- 一萬行程式碼在一個檔案內是可以的。
- 一千行程式碼在一個函式內是可以的。
- 所有有關於服務的程式碼，不管是第三方套件提供的，或是自行撰寫的，就只要放在 servive.py 裡面就好，懂？

# 17. 不要撰寫測試

> 這是一個不需要且無意義的工作。

# 18. 不要使用 Linter

> 你想怎麼寫程式就怎麼寫，電腦不能限制你的創意想法！

# 19. 創立專案時，不需要創建 README 檔案

> 幹嘛增加自己的工作量？打那麼多文件，又沒有人會認真看。

# 20. 保留不必要的程式碼

> 不要刪掉程式沒有使用到的程式碼，頂多就是註解該段程式碼而已。
