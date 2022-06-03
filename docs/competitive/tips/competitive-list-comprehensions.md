# 内包表記

Pythonでは、内包表記というとてもキモくて便利な機能があります。
内包表記を使うことで、記述量を減らし、多少速度を上げることができます。

内包表記基本形は以下の通りです。

```py title="内包表記基本形"
[値 for 変数 in イテラブルオブジェクト]
```

## 基本的な内包表記

少し簡単な動作をしてみましょう。
普通のコードと内包表記のコードを比べてみることで違いがわかりやすいと思います。

=== "普通"
    ```py title="main.py"
    nums = [1, 2, 3, 4, 5]
    squared_nums = []

    for num in nums:
        squared_nums.append(num**2)

    print(squared_nums) # -> [1, 4, 9, 16, 25]
    ```

=== "内包表記"
    ```py title="main.py"
    nums = [1, 2, 3, 4, 5]
    squared_nums = [i**2 for num in nums]

    print(squared_nums) # -> [1, 4, 9, 16, 25]
    ```

## if文を使った内包表記

### elseがない場合

内包表記の中にif文を入れて偶数飲みを取り出すようにしてみましょう。
後ろから読むことでわかりやすくなると思います。

=== "普通"
    ```py title="main.py"
    nums = [1, 2, 3, 4, 5]
    even_nums = []

    for num in nums:
        if num % 2 == 0:
            squared_nums.append(num)

    print(even_nums) # -> [2, 4]
    ```

=== "内包表記"
    ```py title="main.py"
    nums = [1, 2, 3, 4, 5]
    even_nums = [num for num in nums if num % 2 == 0]

    print(even_nums) # -> [2, 4]
    ```

### elseがある場合

内包表記の中にif文でelseを使う場合は前に持ってこないといけないことに寄与つけてください。

=== "普通"
    ```py title="main.py"
    nums = [1, 2, 3, 4, 5]
    even_nums = []

    for num in nums:
        if num % 2 == 0:
            squared_nums.append(num)
        else:
            squared_nums.append("odd!")

    print(even_nums) # -> ['odd!', 2, 'odd!', 4, 'odd!']
    ```

=== "内包表記"
    ```py title="main.py"
    nums = [1, 2, 3, 4, 5]
    even_nums = [num if num % 2 == 0 else "odd!" for num in nums]

    print(even_nums) # -> ['odd!', 2, 'odd!', 4, 'odd!']
    ```

## 二重ループの内包表記(ネスト)

内包表記ではfor分をネストすることができます。

=== "普通"
    ```py title="main.py"
    dimensional_nums = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    normal_nums = []

    for nums in dimensional_nums:
        for num in nums:
            normal_nums.append(num)

    print(normal_nums) # -> [1, 2, 3, 4, 5, 6, 7, 8, 9]
    ```

=== "内包表記"
    ```py title="main.py"
    dimensional_nums = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
    normal_nums = [num for nums in dimensional_nums for num in nums]

    print(normal_nums) # -> [1, 2, 3, 4, 5, 6, 7, 8, 9]
    ```

## 辞書内包表記

=== "普通"
    ```py title="main.py"
    name_and_price = [
        ["apple",  100],
        ["banana", 240],
        ["mango",  320]
    ]

    product = {}

    for name, price in name_and_price:
        product[name] = price

    print(product) # -> {'apple': 100, 'banana': 240, 'mango': 320}
    ```

=== "内包表記"
    ```py title="main.py"
    name_and_price = [
        ["apple",  100],
        ["banana", 240],
        ["mango",  320]
    ]

    product = {name: price for name, price in name_and_price}

    print(product) # -> {'apple': 100, 'banana': 240, 'mango': 320}
    ```

## ジェネレータ内包表記

ジェネレータを使うことでメモリーの使用量を多少減らせます。
ジェネレータについては配列の部分で詳しく解説します。

=== "普通"
    ```py title="main.py"
    def nums():
        for i in range(10):
            yield i // 2

    print(nums())
    ```

=== "内包表記"
    ```py title="main.py"
    nums = (i // 2 for i in range(10))
    print(nums) # -> <generator object <genexpr> at 0x152782131ac0>
    ```

## 参考サイト一覧
[Python Doc - データ構造](https://docs.python.org/ja/3/tutorial/datastructures.html)
