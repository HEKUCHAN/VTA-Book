# 文字列

ここではPythonの文字列について深堀していきます。
Pythonの文字列にはいろんな便利なメゾットや機能がついているので、それについて学んでいきましょう。

## 文字列の表し方

Pythonで文字列で表すには、`"..."`と`...`の部分に文字を書いて文字列年て表すことができます。また、`"（ダブルクォーテーション）`を`'（シングルクォーテーション）`にかえても大丈夫です。

```py title="main.py"
"文字列"
'文字列'
文字列じゃない
```

## 文字列の結合

Pythonでは、`+`を使って文字列の結合ができます。

```py title="main.py"
print("Pyt" + "hon") # -> Python

# 変数に入れて結合可能
some_string = "Hello "
print(some_string + "world!") # -> Hello world!
```

また空白を開けて文字列の結合をすることも可能です、ただ ==可読性が著しく下がる== のでおすすめしません。
変数を使った場合は結合ができないので注意が必要です。

```py title="main.py"
print("Pyt" "hon") # -> Python

# 変数に入れて結合不可能
some_string = "Hello "
print(some_string "world!") # -> SyntaxError: invalid syntax

# 式も結合ができません。
print(("Python" * 2) "Ruby") # -> SyntaxError: invalid syntax
```

## 文字列の反復

演算子の`*`を使って、文字列を反復することができます。

```py title="main.py"
print("Python" * 3) # -> PythonPythonPython
```


## 複数行の文字列を作る
```py title="main.py"
description = """sumary_line

Keyword arguments:
argument -- description
Return: return_description
"""

print(description)
# |
# v
# sumary_line

# Keyword arguments:
# argument -- description
# Return: return_description
```

## 参考サイト一覧
特になし
