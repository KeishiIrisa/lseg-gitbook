# 基本文法

## 1. インデント

インデントとは、行頭の空白や字下げのことです。Pythonでは文のまとまり（ブロック）を認識するためにインデントが必要になります。

以下のコードは"Hello, World!"を5回繰り返し出力するためのプログラムです。

```python
def hello_world():
    # 繰り返しのブロック
    for i in range(5):
        # 処理
        print("Hello, World!")
```



## 2. 変数とは

変数とはデータや情報を格納しておく物です。

数値は数字をそのまま記入すればOKですが、文字列はクオーテーション「’’」かダブルクオーテーション「”」で囲む必要があります。

変数は格納されているデータを変更することができます。

```python
# 数値を格納する場合
age = 15

# 文字列を格納する場合
name = “田中”
```

{% hint style="success" %}
変数の名前はわかりやすい物にしましょう。
{% endhint %}

例えば、年齢を格納する変数は「age」、名前を格納する変数は「name」

複数の単語をつなげるときはアンダースコアを使用します。

変数は数字から始まる名前にすることができないので注意してください。

```python
my_age
name_1
name_2
```

{% hint style="warning" %}
変数名には、使ってはいけない単語があります。それが**予約語**です。特にclassは変数として定義してエラーになることがよくあります。
{% endhint %}

```
【予約語一覧】

class, except, continueなど
```

## 3. 定数

定数とは、格納したデータを変更しない値を言います。

Python以外の言語では「定数」が完全に変更できない状態になっているものもあります。

しかし、Pythonでは完全に変更できない「定数」は定義することができません。

そこで、定数として扱いたい変数は、すべて大文字で名前をつけることがあります。

**「すべて大文字の変数は変更しない」**&#x3068;覚えておきましょう。

```python
MAX_LIMIT = 100
PI = 3.141592
```

{% hint style="success" %}
実際の開発では文字数制限など、プログラムを通して変わらないものを定数として定義しますが、基本は変数として定義します。
{% endhint %}

## 4. データ型

Pythonのデータ型とは、変数に代入するデータの種類のことです。

Pythonでは、変数に値を代入する際に、その値のデータ型が自動的に判断されます。

プログラム内でデータを処理する際、データ型が合わないとエラーになることもあるので、自分が扱っている変数のデータ型には注意しましょう。

{% hint style="success" %}
Pythonは動的型付け言語であり、定義した変数に対してint型やstr型を入れることも可能です。実際の開発では、変数を定義する際にどんな型の変数なのかを書いておき、型が違うことによるエラーを防ぎます。これをタイプアノテーションと言います。
{% endhint %}

**参考サイト**

{% embed url="https://note.com/tasting/n/na6152e3aac51" %}

{% embed url="https://zenn.dev/kazu1/articles/662816f4acaede" %}

### 4.1. 型の種類

1. ブーリアン型
   1. 真（True）または偽（False）のいずれかを表すデータ型です。
2. #### 数値（int、float）
   1. 整数（int）: 整数を表すデータ型です。
   2. 浮動小数点数（float）: 小数点を含む数値を表すデータ型です。
3. #### 文字列（str）
   1. 文字の並び（テキスト）を表すデータ型です。
4. #### リスト（list）
   1. 順序を持った複数の値（要素）を一つにまとめたデータ型です。要素は**変更可能**です。
5. #### タプル（tuple）
   1. 順序を持った複数の値を一つにまとめたデータ型ですが、リストと異なり要素は**変更不可能**です。
6. #### 辞書（dict）
   1. キーと値のペアを保持するデータ型です。各キーは一意であり、そのキーに関連付けられた値を格納します。
7. #### 集合（set）
   1. 一意な要素の集まりを表すデータ型です。順序は保持されず、重複する要素は持てません。

```python
# ブーリアン型 
a = True
b = False

# int型
int_1 = 5
int_2 = -100

# float型
float_1 = 3.14
float_2 = -0.001

# str型
str_1 = "hello"
str_2 = 'Python'

# list型
list_1 = [1, 2, 3]
list_2 = ['a', 'b', 'c']
list_3 = [1, 2, 3, 'a', 'b', 'c']

# tuple型
tuple_1 = (1, 2, 3)
tuple_2 = ('a', 'b', 'c')
tuple_3 = (1, 2, 3, 'a', 'b', 'c')

# dict型
dict = {'name': 'Alice', 'age': 25}

# set型
set = {1, 2, 3, 'a', 'b', 'c'}
```

### 4.2. データ型の確認方法

データ型の確認はtype()を使用します。

```python
age = 15
name = "田中"

print(age)
print(type(age))

print(name)
print(type(name))

# 出力結果
# 15
# <class 'int'>
# 田中
# <class 'str'>
```

## 5 演算子と式

1. #### 算術演算子（加算、減算、乗算、除算）
   1. +（加算）、-（減算）、\*_（乗算）、/（除算）、%（剰余）、_\*\*（べき乗）
2. #### 比較演算子
   1. \==（等しい）、!=（等しくない）、<（未満）、>（超過）、<=（以下）、>=（以上）
3. #### 論理演算子
   1. and（かつ）、or（または）、not（否定）

{% hint style="warning" %}
aとbが等しいかどうかを確認するのはa == bというふうに=が2個あることに注意してください。
{% endhint %}

## 6 条件文（if文）

#### if文の基本構造

```python
if 条件式:
    処理①
```

条件式が「Ture」のとき、処理①が実行されます。

#### if-else文

```python
if 条件式:
    処理①
else:
    処理②
```

条件式が「Ture」のとき、処理①が実行されます。

条件式が「False」のとき、処理②が実行されます。

#### if-elif-else文

```python
if 条件式A:
    処理①
elif 条件式B:
    処理②
else:
    処理③
```

条件式Aが「Ture」のとき、処理①が実行されます。

条件式Aが「False」、かつ条件式Bが「Ture」のとき、処理②が実行されます。

条件式Aが「False」、かつ条件式Bが「False」のとき、処理③が実行されます。

elifは何個も追加することができます。

複数の条件文ですべて「False」になったときに、elseの処理が実行されます。

```python
age = 20

if age > 30:
    print("ageは30より大きい")
elif age > 20:
    print("ageは20より大きく、30以下")
elif age > 10:
    print("ageは10より大きく、20以下")
else:
    print("ageは10以下")

# 出力結果
# ageは10より大きく、20以下
```



## 7 繰り返し（for文とwhile文）

同じ処理を繰り返す場合は、for文とwhile文を使用します。

### 7.1. for文の基本構造

```python
for 変数 in オブジェクト:
    処理
```

オブジェクトにはrange関数やリストなどを使用します。

```python
# range関数を使用
for i in range(5):
    print(i)

# リストを使用
fruits = ["apple", "banana", "cherry"]

for fruit in fruits:
    print(fruit)
```

### 7.2. while文の基本構造

```python
while 条件式:
    処理
```

while文では、指定した条件が「True」である間処理を繰り返します。

条件式が「False」になるタイミングがないと、処理が無限ループしてしまうので注意してください。

```python
# カウンタが5に達するまでループ
counter = 0

while counter < 5:
    print(counter)
    counter += 1
```

### 7.3. 繰り返しの制御（breakとcontinue）

繰り返しを制御する方法として、breakとcontinueがあります。

breakは繰り返しを抜けることができます。

```python
# 1から10までの数を印刷し、5で停止
for i in range(1, 11):
    if i == 5:
        break
    print(i)

# 出力結果
# 1
# 2
# 3
# 4
```

continueはcontinue以降の処理をスキップして、繰り返しの先頭に戻ることができます。

```python
# 1から10までの数を印刷し、5をスキップ
for i in range(1, 11):
    if i == 5:
        continue
    print(i)

# 出力結果
# 1
# 2
# 3
# 4
# 6
# 7
# 8
# 9
# 10
```



## 8 関数

### 8.1. 関数の基本構造

```python
def 関数名(引数1, 引数2):
    処理
    return 戻り値
```

### 8.2. 引数と戻り値

引数とは、関数に渡される値やデータのことです。

関数内では、この引数を使用して処理を行います。

戻り値とは、関数が処理を完了した後に返すデータのことです。

returnを使用して戻り値を返します。

特に戻り値が必要ない場合は「None」を返します。

```python
# 引数として 2 つの数値を取り、その和を返す関数
def add(a, b):
    return a + b

# 関数を呼び出し、結果を印刷
result = add(5, 3)
print(result)

# 出力結果
# 8
```



## 9 リストの使い方

要素へのアクセス: リストの要素には、インデックス（<mark style="color:red;">**0から始まる**</mark>）を使用してアクセスします。

1. **要素の追加：**&#x61;ppend() メソッドでリストの最後に要素を追加します。
2. **要素の削除：**&#x72;emove() メソッドで特定の要素を削除、または del ステートメントで指定したインデックスの要素を削除します。
3. **リストの長さ：**&#x6C;en() 関数でリストの長さ（要素数）を取得します。
4. **リストの反復処理：**&#x66;or ループを使用してリストの各要素に対して操作を行うことができます。

```python
# リストの作成
fruits = ["apple", "banana", "cherry"]

# リストの長さを取得
print(len(fruits)) # 出力: 3

# リストの最後に要素を追加
fruits.append("orange")

# 特定の要素にアクセス
print(fruits[1]) # 出力: banana

# リストの要素を反復処理
for fruit in fruits:
    print(fruit)
```



## 10 タプル

### 10.1. タプルとは

タプルとは、順序付けられたデータのまとまりのことです。

リストとの違いはデータを自由に変更することができない点です。

タプルはカンマ , で区切られた要素を丸括弧 () で囲んで定義します。

丸括弧なしで要素をカンマで区切るだけでもタプルとして指定することもできます。

```python
# 空のタプル
empty_tuple = ()

# 要素を持つタプル
number_tuple = (1, 2, 3, 4, 5)

# 括弧なしでもタプル
another_tuple = 1, 2, 3

# 要素が1つのタプル
single_element_tuple = (1,)
```

### 10.2. タプルの使い方

要素へのアクセス: タプルの要素にはインデックス（0から始まる）を使用してアクセスします。

1. **タプルの長さ：**&#x6C;en() 関数でタプルの長さ（要素数）を取得します。
2. **タプルの反復処理：**&#x66;or ループを使用してタプルの各要素に対して操作を行うことができます。

```python
# タプルの作成
fruits = ("apple", "banana", "cherry")

# タプルの長さを取得
print(len(fruits)) # 出力: 3

# 特定の要素にアクセス
print(fruits[1]) # 出力: banana

# タプルの要素を反復処理
for fruit in fruits:
    print(fruit)
```



## 11 辞書

### 11.1. 辞書とは

辞書とは、キーと値のペアで構成されるデータのまとまりのことです。

辞書内では同じキーを2回使用することができません。

辞書は波括弧 {} を使用して定義され、キーと値は : で区切られます。各キーと値のペアはカンマ , で区切られます。

```python
# 空の辞書
empty_dict = {}

# キーと値を持つ辞書
person = {"name": "John", "age": 30, "city": "New York"}
```

### 11.2. 辞書の使い方

1. **値へのアクセス:** 辞書の値にアクセスするには、対応するキーを角括弧 \[] の中に指定します。
2. **要素の追加・変更:** 新しいキーを角括弧 \[] の中に指定し、値を代入することで、要素を追加または変更できます。
3. **要素の削除：**&#x64;el ステートメントを使用して特定のキーとその値を削除できます。
4. **キーの存在確認：**&#x69;n キーワードを使用して、キーが辞書内に存在するか確認できます。

```python
# 辞書の作成
person = {"name": "John", "age": 30, "city": "New York"}

# 特定の値にアクセス
print(person["name"]) # 出力: John

# 新しいキーと値を追加
person["email"] = "john@example.com"

# キーの存在を確認
if "age" in person:
    print("Age is present")

# キーと値のペアを削除
del person["city"]

# 辞書のキーと値を反復処理
for key, value in person.items():
    print(key, value)
```



## 12 ライブラリ

ライブラリとは、プログラムでよく使われる機能（関数やパッケージ）がまとめられたものを言います。

ライブラリを使用する際は、インポートしてから使用します。

インポートはファイルの最初にまとめて記述しましょう。

```python
import time
import pandas as pd
```

{% hint style="success" %}
生成AIを組み込んだアプリを開発する際にPythonが選ばれるのはこのライブラリの豊富さです。多くの生成AIサービスはPythonで書かれたライブラリがあり、importするだけでその生成AIサービスがアプリの中で使えるのです。
{% endhint %}

いかにChatGPTで知られるOpenAIのライブラリを使ったPythonコードを紹介します。

```python
from openai import OpenAI
client = OpenAI()

completion = client.chat.completions.create(
    model="gpt-4o",
    messages=[
        {"role": "developer", "content": "You are a helpful assistant."},
        {
            "role": "user",
            "content": "Write a haiku about recursion in programming."
        }
    ]
)

print(completion.choices[0].message)
```

このように、すでに作られたOpenAIのライブラリをインポートすることで、簡単に生成AIが使用できるのです。

{% embed url="https://platform.openai.com/docs/guides/text-generation" %}
OpenAIのAPIの公式ドキュメント
{% endembed %}

{% hint style="success" %}
上のサイトのように実際にどのようにライブラリを使うのかが分かりやすくまとまっています。読んでみると楽しいと思います☺️

画像生成AIや、AI音声生成、テキスト生成など様々なAIサービスが簡単に使えるのが楽しいですね。
{% endhint %}



## 13 組み込み関数

組み込み関数とは、Pythonですでに用意されている関数のことです。

よく使用する組み込み関数を紹介します。

{% embed url="https://docs.python.org/ja/3/library/functions.html" %}

1. **数値系**

| **組み込み関数** | **処理内容**         |
| ---------- | ---------------- |
| sum()      | すべての要素の合計を返す     |
| max()      | 複数要素の中から最大値を返す   |
| min()      | 複数要素の中から最小値を返す   |
| round()    | 数値の指定した桁数で四捨五入する |
| abs()      | 数値の絶対値を返す        |

```python
# 数値系組み込み関数
numbers = [1, 2, 3, 4, 5]

# sum() - すべての要素の合計を返す
print("sum():", sum(numbers))  # 出力結果: 15

# max() - 最大値を返す
print("max():", max(numbers))  # 出力結果: 5

# min() - 最小値を返す
print("min():", min(numbers))  # 出力結果: 1

# round() - 四捨五入
num = 3.14159
print("round():", round(num, 2))  # 出力結果: 3.14

# abs() - 絶対値を返す
num = -10
print("abs():", abs(num))  # 出力結果: 10
```



2. **型宣言系**

| **組み込み関数** | **処理内容**      |
| ---------- | ------------- |
| int()      | データ型を整数に変換する  |
| str()      | データ型を文字列に変換する |
| type()     | データ型を返す       |

```python
# 型宣言系組み込み関数
value = "123"

# int() - 整数に変換
print("int():", int(value))  # 出力結果: 123

# str() - 文字列に変換
num = 456
print("str():", str(num))  # 出力結果: "456"

# type() - データ型を返す
print("type():", type(num))  # 出力結果: <class 'int'>
```



3. **処理系**

| **組み込み関数**  | **処理内容**                              |
| ----------- | ------------------------------------- |
| enumerate() | リストなどの要素にカウンタを追加して返す                  |
| len()       | リストなどの要素数を返す                          |
| print()     | 出力する                                  |
| input()     | ユーザーからの入力を文字列として取得する                  |
| range()     | 指定された開始点から終了点までの数値を持つリスト（のようなもの）を生成する |

```python
# 処理系組み込み関数
items = ["apple", "banana", "cherry"]

# enumerate() - 要素にカウンタを追加
for index, item in enumerate(items):
    print(f"enumerate(): Index {index}, Item {item}")
# 出力結果:
# enumerate(): Index 0, Item apple
# enumerate(): Index 1, Item banana
# enumerate(): Index 2, Item cherry

# len() - 要素数を返す
print("len():", len(items))  # 出力結果: 3

# print() - 出力する
print("print(): Hello, World!")  # 出力結果: Hello, World!

# input() - ユーザー入力 (実行時に入力が必要)
# user_input = input("Enter something: ")
# print("input():", user_input)  # 出力結果: (入力した内容)

# range() - 数値範囲を生成
print("range():", list(range(1, 6)))  # 出力結果: [1, 2, 3, 4, 5]
```

