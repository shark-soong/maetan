# 🐍 파이썬 기초 실습

> 파이썬을 처음 배우는 고등학생을 위한 복습 사이트입니다.
> 수업에서 배운 내용을 예제로 다시 실행해 보고, 연습 문제를 풀면서 혼자서도 익힐 수 있습니다.

---

## 📚 이 사이트 사용법

1. 설명을 읽고 예제 코드를 **직접 실행**합니다.
2. 코드를 조금씩 바꿔 보면서 결과가 어떻게 달라지는지 확인합니다.
3. 연습 문제를 풉니다. 막히면 `💡 힌트`를 먼저 열어 보세요.
4. 끝까지 풀어 본 다음 `✅ 정답`과 비교합니다. 답이 달라도 실행 결과가 같으면 맞을 수 있습니다.

빈칸(`___`)이 있는 문제는 빈칸을 채운 뒤 실행하세요. 빈칸을 그대로 두고 실행하면 `NameError`가 납니다.

### 코드 실행 방법

설치 없이 Google 계정만 있으면 바로 실행할 수 있습니다.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/shark-soong/maetan/blob/main/python_basics_practice.ipynb)

1. 위 버튼을 눌러 실습 노트북을 엽니다.
2. `파일` → `드라이브에 사본 저장`을 누르면 내 코드를 저장할 수 있습니다.
3. 코드 칸 왼쪽의 ▶ 버튼을 누르거나 `Shift + Enter`를 누르면 실행됩니다.
4. `input()`이 있는 코드는 입력 칸이 나타나면 값을 쓰고 `Enter`를 누릅니다.

노트북 파일을 직접 받고 싶다면 [여기](python_basics_practice.ipynb)에서 받을 수 있습니다.

---

## 🗺️ 학습 순서

| 단계 | 내용 | 문제 |
|---|---|---|
| [Part 0. 시작하기](#part0) | 출력, 변수, 연산, 입력, 리스트 | 연습 2개 |
| [Part 1. 집합과 딕셔너리](#part1) | 중복 없는 묶음, 이름표가 있는 묶음 | 연습 2개 |
| [Part 2. 조건문](#part2) | `if`, `elif`, `else` | 연습 3개 |
| [Part 3. 반복문](#part3) | `for`, `while`, `break`, `continue` | 연습 3개 |
| [Part 4. 응용 문제](#part4) | 배운 내용 함께 쓰기 | 응용 5개 |
| [Monte Carlo Simulation](#monte-carlo) | 난수로 원주율 구하기 | 실험 1개 |
| [막혔을 때](#help) | 자주 만나는 에러 해결 | |
| [배운 내용 정리](#summary) | 핵심 문법 모아 보기 | |

---

<a id="part0"></a>

## 🌱 Part 0. 시작하기

뒤에 나오는 모든 코드에서 쓰는 기본 문법입니다.

### 0-1. 출력하기와 주석

`print()`는 괄호 안의 내용을 화면에 보여 줍니다. `#` 뒤에 쓴 글은 **주석**이라 실행되지 않습니다.

```python
# 이 줄은 주석입니다. 실행되지 않아요.
print("안녕하세요!")
print(3 + 4)
```

### 0-2. 변수와 자료형

**변수**는 값에 붙이는 이름입니다. `=`는 "같다"가 아니라 "오른쪽 값을 왼쪽 이름에 저장한다"는 뜻입니다.

```python
name = "김아주"
age = 17
height = 170.5
is_student = True

print(name, age, height, is_student)
print(type(age))
```

| 자료형 | 뜻 | 예시 |
|---|---|---|
| `int` | 정수 | `17` |
| `float` | 소수 | `170.5` |
| `str` | 문자열 | `"김아주"` |
| `bool` | 참과 거짓 | `True`, `False` |

### 0-3. 계산하기

| 연산자 | 뜻 | 예시 | 결과 |
|---|---|---|---|
| `+` `-` `*` | 더하기, 빼기, 곱하기 | `2 * 3` | `6` |
| `/` | 나누기 | `7 / 2` | `3.5` |
| `//` | 나눈 몫 | `7 // 2` | `3` |
| `%` | 나눈 나머지 | `7 % 2` | `1` |
| `**` | 거듭제곱 | `2 ** 3` | `8` |

### 0-4. 입력받기와 f-string

`input()`은 키보드로 입력한 값을 **항상 문자열로** 가져옵니다. 숫자로 계산하려면 `int()`나 `float()`로 바꿔야 합니다.

문자열 앞에 `f`를 붙이면 `{ }` 안에 변수나 계산식을 넣을 수 있습니다. 이것을 **f-string**이라고 합니다.

```python
name = input("이름을 입력하세요: ")
age = int(input("나이를 입력하세요: "))

print(f"{name}님은 내년에 {age + 1}살입니다.")
```

### 0-5. 리스트와 인덱스

**리스트**는 여러 값을 순서대로 담습니다. 위치 번호인 **인덱스는 0부터** 시작하고, `-1`은 맨 뒤를 뜻합니다. 문자열도 같은 방법으로 글자를 꺼낼 수 있습니다.

```python
fruits = ['사과', '바나나', '체리']
print(fruits[0])
print(len(fruits))   # len()은 개수나 길이를 알려 줍니다

word = "python"
print(word[0])
print(word[-1])
```

### ✏️ 연습 0-1 — 자기소개 문장 만들기

이름과 학년을 입력받아 `OOO 학생은 O학년입니다.`를 출력하세요.

```python
name = input("이름을 입력하세요: ")
grade = int(input("학년을 입력하세요: "))

# 여기에 코드를 작성하세요
```

실행 예시:

```text
이름을 입력하세요: 김아주
학년을 입력하세요: 2
김아주 학생은 2학년입니다.
```

<details markdown="1">
<summary>💡 힌트</summary>

0-4의 f-string처럼 `{name}`과 `{grade}`를 문장 안에 넣어 보세요.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
name = input("이름을 입력하세요: ")
grade = int(input("학년을 입력하세요: "))

print(f"{name} 학생은 {grade}학년입니다.")
```

</details>

### ✏️ 연습 0-2 — 두 과목 평균 구하기

국어와 수학 점수를 입력받아 평균을 출력하세요.

```python
korean = int(input("국어 점수: "))
math = int(input("수학 점수: "))

# 여기에 코드를 작성하세요
```

실행 예시:

```text
국어 점수: 80
수학 점수: 95
평균: 87.5
```

<details markdown="1">
<summary>💡 힌트</summary>

곱셈과 나눗셈이 덧셈보다 먼저 계산됩니다. 두 점수를 더하는 부분에 괄호가 필요합니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
korean = int(input("국어 점수: "))
math = int(input("수학 점수: "))

average = (korean + math) / 2
print(f"평균: {average}")
```

</details>

---

<a id="part1"></a>

## 📌 Part 1. 집합(Set)과 딕셔너리(Dictionary)

### 1-1. 집합 (Set)

- `set()`으로 만듭니다.
- **중복을 허용하지 않습니다.**
- **순서가 없습니다.** 그래서 출력 순서가 입력한 순서와 다를 수 있습니다.

| 연산 | 기호 | 뜻 |
|---|---|---|
| 합집합 | <code>&#124;</code> | 둘 중 하나에라도 있는 값 |
| 교집합 | `&` | 둘 다에 있는 값 |
| 차집합 | `-` | 앞에만 있는 값 |

**예제: 집합 생성과 연산**

```python
# 집합 생성
s1 = set([1, 'hello', 434, 2.23, 'wow', 1, 'hello'])  # 중복 포함
print("집합 s1:", s1)

# 집합 연산
a = {1, 2, 3, 4, 5}
b = {3, 4, 5, 6, 7}

print("합집합:", a | b)
print("교집합:", a & b)
print("차집합:", a - b)
```

### ✏️ 연습 1-1 — 중복 제거하기

아래 리스트에서 **중복을 제거**한 집합을 만들고, 원소의 개수를 출력하세요.

```python
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

# 여기에 코드를 작성하세요
```

실행 예시:

```text
중복 제거된 집합: {1, 2, 3, 4}
원소의 개수: 4
```

<details markdown="1">
<summary>💡 힌트</summary>

`set(numbers)`로 집합을 만들고, 0-5에서 배운 `len()`으로 개수를 세어 보세요.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
numbers = [1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

unique = set(numbers)
print("중복 제거된 집합:", unique)
print("원소의 개수:", len(unique))
```

</details>

### 1-2. 딕셔너리 (Dictionary)

- **키(key)**와 **값(value)**을 한 쌍으로 저장합니다.
- 리스트가 위치 번호로 값을 찾는다면, 딕셔너리는 **이름표(키)**로 값을 찾습니다.

**예제: 딕셔너리 생성과 수정**

```python
# 딕셔너리 생성
hi = {'이름': '김아주', '나이': 20, '학교': '파이썬대학교'}
print(hi)

# 값 접근
print("이름:", hi['이름'])
print("나이:", hi['나이'])

# 키-값 쌍 추가 / 수정 / 삭제
hi['학번'] = '20260001'
del hi['학교']

print("수정 후:", hi)
```

### ✏️ 연습 1-2 — 내 정보 딕셔너리

자신의 정보를 딕셔너리에 채우고, 키를 이용해 값을 하나씩 출력하세요.

```python
my_info = {
    '이름': '',          # 이름 입력
    '나이': 0,           # 나이 입력
    '좋아하는 언어': ''   # 언어 입력
}

# 여기에 코드를 작성하세요
```

실행 예시:

```text
이름: 홍길동
나이: 20
좋아하는 언어: Python
```

<details markdown="1">
<summary>💡 힌트</summary>

`my_info['이름']`처럼 대괄호 안에 키를 쓰면 값을 꺼낼 수 있습니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
my_info = {
    '이름': '홍길동',
    '나이': 20,
    '좋아하는 언어': 'Python'
}

print("이름:", my_info['이름'])
print("나이:", my_info['나이'])
print("좋아하는 언어:", my_info['좋아하는 언어'])
```

</details>

---

<a id="part2"></a>

## 📌 Part 2. 조건문 (if / elif / else)

조건이 맞는지에 따라 실행할 코드를 고릅니다.

### 2-1. 기본 if - else

```text
if 조건:
    조건이 참일 때 실행할 코드
else:
    조건이 거짓일 때 실행할 코드
```

> ⚠️ `if` 줄 끝의 콜론(`:`)과 다음 줄의 **들여쓰기(스페이스 4칸)**를 빠뜨리면 에러가 납니다.

조건에는 아래 연산자를 씁니다.

| 연산자 | 뜻 | 예시 |
|---|---|---|
| `==` | 같다 | `a == 3` |
| `!=` | 다르다 | `a != 3` |
| `>` `<` | 크다, 작다 | `a > 3` |
| `>=` `<=` | 크거나 같다, 작거나 같다 | `a >= 3` |
| `and` | 둘 다 참이면 참 | `a > 1 and b > 1` |
| `or` | 하나라도 참이면 참 | `a > 1 or b > 1` |
| `not` | 참과 거짓을 반대로 | `not a > 1` |

> ⚠️ `=`는 저장이고 `==`는 비교입니다. 조건에는 `==`를 씁니다.

**예제: 아이스크림 구매하기**

```python
money = int(input("지갑에 있는 돈을 입력하세요 (원): "))

if money >= 1200:
    print("월드콘을 살 수 있어요! 🍦")
else:
    print("돈이 부족해요. 😢")
```

### 2-2. if - elif - else

조건이 여러 개일 때 씁니다. 위에서부터 차례로 검사하고, **처음으로 참인 부분 하나만** 실행합니다.

```python
money = int(input("지갑에 있는 돈을 입력하세요 (원): "))

if money >= 1200:
    print("월드콘을 사 먹자! 🍦")
elif money >= 600:
    print("메로나를 사 먹자! 🟩")
else:
    print("돈이 부족해요. 😢")
```

### ✏️ 연습 2-1 — 두 수 비교

변수 `a`와 `b`를 입력받아 아래 조건에 맞는 문장을 출력하세요.

1. 둘 다 100 이상 → `"Both Big Enough"`
2. 하나만 100 이상 → `"Only One Big Enough"`
3. 둘 다 100 미만 → `"Not Big Enough"`

```python
a = int(input("a 값을 입력하세요: "))
b = int(input("b 값을 입력하세요: "))

# 여기에 코드를 작성하세요
```

실행 예시:

```text
a 값을 입력하세요: 120
b 값을 입력하세요: 50
Only One Big Enough
```

<details markdown="1">
<summary>💡 힌트</summary>

"둘 다"를 `and`로 먼저 검사하고, 그다음 "하나라도"를 `or`로 검사해 보세요.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
a = int(input("a 값을 입력하세요: "))
b = int(input("b 값을 입력하세요: "))

if a >= 100 and b >= 100:
    print("Both Big Enough")
elif a >= 100 or b >= 100:
    print("Only One Big Enough")
else:
    print("Not Big Enough")
```

</details>

### ✏️ 연습 2-2 — BMI 계산기

체중과 키를 입력받아 BMI를 계산하고, 아래 구간에 맞는 판정을 출력하세요.

> BMI = 체중(kg) / 신장(m)²

- 저체중: 20 미만
- 정상: 20 이상 25 미만
- 과체중: 25 이상 30 미만
- 비만: 30 이상 40 미만
- 고도비만: 40 이상

```python
weight = float(input("체중(kg)을 입력하세요: "))
height = float(input("신장(cm)을 입력하세요: "))

height_m = height / 100  # cm → m 변환
bmi = weight / (height_m ** 2)
print(f"BMI: {bmi:.2f}")   # :.2f 는 소수 둘째 자리까지 표시

# 아래에 조건문으로 판정 결과를 출력하세요
```

실행 예시:

```text
체중(kg)을 입력하세요: 65
신장(cm)을 입력하세요: 170
BMI: 22.49
정상입니다.
```

<details markdown="1">
<summary>💡 힌트</summary>

큰 값부터 `elif`로 검사하면 조건을 짧게 쓸 수 있습니다. 예를 들어 `bmi >= 40`이 아니면서 `bmi >= 30`이면 비만입니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
weight = float(input("체중(kg)을 입력하세요: "))
height = float(input("신장(cm)을 입력하세요: "))

height_m = height / 100
bmi = weight / (height_m ** 2)
print(f"BMI: {bmi:.2f}")

if bmi >= 40:
    print("고도비만입니다.")
elif bmi >= 30:
    print("비만입니다.")
elif bmi >= 25:
    print("과체중입니다.")
elif bmi >= 20:
    print("정상입니다.")
else:
    print("저체중입니다.")
```

</details>

### ✏️ 연습 2-3 — 사칙연산 계산기

두 수와 연산자(`+`, `-`, `*`, `/`)를 입력받아 결과를 출력하세요. 0으로 나누려고 하면 안내 문구를 출력합니다.

```python
num1 = float(input("첫 번째 숫자: "))
op = input("연산자 (+, -, *, /): ")
num2 = float(input("두 번째 숫자: "))

# 여기에 코드를 작성하세요
```

실행 예시:

```text
첫 번째 숫자: 6
연산자 (+, -, *, /): *
두 번째 숫자: 3
결과: 18.0
```

<details markdown="1">
<summary>💡 힌트</summary>

`op == '+'`처럼 연산자 문자열을 비교합니다. 나눗셈 안에서 `num2 == 0`인지 한 번 더 검사해 보세요.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
num1 = float(input("첫 번째 숫자: "))
op = input("연산자 (+, -, *, /): ")
num2 = float(input("두 번째 숫자: "))

if op == '+':
    print("결과:", num1 + num2)
elif op == '-':
    print("결과:", num1 - num2)
elif op == '*':
    print("결과:", num1 * num2)
elif op == '/':
    if num2 == 0:
        print("0으로 나눌 수 없습니다.")
    else:
        print("결과:", num1 / num2)
else:
    print("올바른 연산자를 입력하세요.")
```

</details>

---

<a id="part3"></a>

## 📌 Part 3. 반복문 (for / while)

### 3-1. for 반복문과 range()

정해진 묶음이나 횟수만큼 반복합니다.

```text
for 변수 in 리스트/문자열/range():
    반복할 코드
```

| 코드 | 만들어지는 값 |
|---|---|
| `range(5)` | 0, 1, 2, 3, 4 (끝 숫자는 포함하지 않음) |
| `range(1, 6)` | 1, 2, 3, 4, 5 |
| `range(1, 10, 2)` | 1, 3, 5, 7, 9 (2씩 증가) |
| `range(3, 0, -1)` | 3, 2, 1 (1씩 감소) |

**예제 1: 리스트 순회**

```python
fruits = ['사과', '바나나', '체리']

for fruit in fruits:
    print(fruit)
```

**예제 2: 1부터 10까지 합 구하기**

`total += i`는 `total = total + i`를 줄여 쓴 것입니다.

```python
print("1~10 합계:")
total = 0

for i in range(1, 11):
    total += i

print("합계 =", total)
```

### ✏️ 연습 3-1 — 문자열 거꾸로 출력

`input()`으로 문자열을 입력받아 **for 문**을 이용해 거꾸로 출력하세요.

```python
s = input("문장을 입력하세요: ")
length = len(s) - 1   # 마지막 글자의 인덱스

# for 문을 이용해 거꾸로 출력하세요
```

실행 예시:

```text
문장을 입력하세요: python
nohtyp
```

<details markdown="1">
<summary>💡 힌트</summary>

- `range(length, -1, -1)`은 마지막 인덱스부터 0까지 거꾸로 셉니다.
- `print(값, end='')`는 줄을 바꾸지 않고 이어서 출력합니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
s = input("문장을 입력하세요: ")
length = len(s) - 1

for i in range(length, -1, -1):
    print(s[i], end='')
print()
```

</details>

### 3-2. while 반복문

조건이 참인 동안 계속 반복합니다.

```text
while 조건:
    반복할 코드
```

**예제: 카운트다운**

```python
count = 5

while count > 0:
    print(count)
    count -= 1

print("발사! 🚀")
```

> ⚠️ `count -= 1`처럼 조건을 바꾸는 코드가 없으면 **무한 반복**에 빠집니다. 멈추지 않을 때는 Colab에서 실행 중인 칸의 ■ 버튼을 누르세요.

### 3-3. break와 continue

- `break`: 반복을 완전히 끝냅니다.
- `continue`: 이번 회차만 건너뛰고 다음 회차로 넘어갑니다.

```python
# break: 특정 조건에서 반복 완전 종료
print("=== break 예시 ===")
for i in range(1, 11):
    if i == 5:
        break
    print(i, end=' ')
print()

# continue: 해당 회차만 건너뜀
print("=== continue 예시 (홀수만 출력) ===")
for i in range(1, 11):
    if i % 2 == 0:
        continue
    print(i, end=' ')
```

### ✏️ 연습 3-2 — while 구구단 출력

원하는 단을 입력받아 **while 문**으로 구구단을 출력하세요.

```python
num = int(input("구구단 몇 단을 출력할까요? "))

i = 1
while i <= 9:
    # 출력 코드를 완성하세요
    i += 1
```

실행 예시 (앞부분):

```text
구구단 몇 단을 출력할까요? 3
3 x 1 = 3
3 x 2 = 6
3 x 3 = 9
```

<details markdown="1">
<summary>💡 힌트</summary>

f-string 안에 `{num * i}`처럼 계산식을 바로 넣을 수 있습니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
num = int(input("구구단 몇 단을 출력할까요? "))

i = 1
while i <= 9:
    print(f"{num} x {i} = {num * i}")
    i += 1
```

</details>

### ✏️ 연습 3-3 — 딕셔너리 전체 출력

연습 1-2의 딕셔너리를 이번에는 `for` 문으로 출력하세요. `.items()`를 쓰면 키와 값을 한 쌍씩 꺼낼 수 있습니다.

```python
my_info = {
    '이름': '홍길동',
    '나이': 20,
    '좋아하는 언어': 'Python'
}

# for key, value in my_info.items(): 를 활용해 출력해보세요
```

실행 예시:

```text
이름 : 홍길동
나이 : 20
좋아하는 언어 : Python
```

<details markdown="1">
<summary>💡 힌트</summary>

`print(key, ":", value)`처럼 쉼표로 나누면 값 사이에 공백이 들어갑니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
my_info = {
    '이름': '홍길동',
    '나이': 20,
    '좋아하는 언어': 'Python'
}

for key, value in my_info.items():
    print(key, ":", value)
```

</details>

---

<a id="part4"></a>

## 🔥 Part 4. 응용 문제 (난이도 ★★☆)

지금까지 배운 조건문, 반복문, 자료형을 **함께** 활용합니다. 새로 나오는 문법은 문제마다 설명해 두었습니다. 코드를 읽고 빈칸(`___`)을 채워 완성하세요.

### 🎯 응용 4-1 — 소수(Prime Number) 판별기

자연수 `n`을 입력받아 소수인지 판별하세요. 소수는 1과 자기 자신으로만 나누어지는 1보다 큰 자연수입니다.

- `is_prime`처럼 참과 거짓을 기억하는 변수를 **플래그**라고 합니다.

```python
n = int(input("자연수를 입력하세요: "))

is_prime = True

if n < 2:
    is_prime = False
else:
    for i in range(2, n):
        if n % i == ___:
            is_prime = ___
            break

if is_prime:
    print(f"{n}은(는) 소수입니다! ✅")
else:
    print(f"{n}은(는) 소수가 아닙니다. ❌")
```

실행 예시:

```text
자연수를 입력하세요: 17
17은(는) 소수입니다! ✅
```

<details markdown="1">
<summary>💡 힌트</summary>

나머지가 0이면 나누어떨어진다는 뜻입니다. 2부터 `n-1`까지 중에 나누어떨어지는 수가 하나라도 있으면 소수가 아닙니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
n = int(input("자연수를 입력하세요: "))

is_prime = True

if n < 2:
    is_prime = False
else:
    for i in range(2, n):
        if n % i == 0:
            is_prime = False
            break

if is_prime:
    print(f"{n}은(는) 소수입니다! ✅")
else:
    print(f"{n}은(는) 소수가 아닙니다. ❌")
```

</details>

### 🎯 응용 4-2 — 숫자 맞추기 게임

컴퓨터가 1부터 100 사이의 수를 임의로 정하면, 사용자가 **7번 안에** 맞춥니다.

- 입력한 수가 정답보다 **크면** → `"📉 더 작은 수를 입력하세요."`
- 입력한 수가 정답보다 **작으면** → `"📈 더 큰 수를 입력하세요."`
- 7번 안에 못 맞추면 정답을 알려 줍니다.

**새로 나오는 문법**

- `import random`: 난수 기능을 불러옵니다. `random.randint(1, 100)`은 1 이상 100 이하의 정수를 무작위로 고릅니다.
- `while`에 붙은 `else`: `break` 없이 반복이 끝났을 때, 즉 끝까지 못 맞췄을 때 실행됩니다.

```python
import random

answer = random.randint(1, 100)
max_tries = 7
tries = 0

print("🎮 숫자 맞추기 게임! 1~100 사이의 수를 맞춰보세요.")
print(f"기회는 {max_tries}번입니다.\n")

while tries < max_tries:
    guess = int(input(f"[{tries+1}/{max_tries}] 숫자를 입력하세요: "))
    tries += 1

    if guess == ___:
        print(f"🎉 정답! {tries}번 만에 맞췄습니다!")
        break
    elif guess > ___:
        print("📉 더 작은 수를 입력하세요.")
    else:
        print("📈 더 큰 수를 입력하세요.")
else:
    print(f"😢 실패! 정답은 {answer}이었습니다.")
```

실행 예시 (정답이 42일 때):

```text
🎮 숫자 맞추기 게임! 1~100 사이의 수를 맞춰보세요.
기회는 7번입니다.

[1/7] 숫자를 입력하세요: 50
📉 더 작은 수를 입력하세요.
[2/7] 숫자를 입력하세요: 25
📈 더 큰 수를 입력하세요.
[3/7] 숫자를 입력하세요: 42
🎉 정답! 3번 만에 맞췄습니다!
```

<details markdown="1">
<summary>💡 힌트</summary>

입력한 수 `guess`를 컴퓨터가 정한 수와 비교합니다. 게임을 잘하고 싶다면 남은 범위의 가운데 수를 입력해 보세요.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
import random

answer = random.randint(1, 100)
max_tries = 7
tries = 0

print("🎮 숫자 맞추기 게임! 1~100 사이의 수를 맞춰보세요.")
print(f"기회는 {max_tries}번입니다.\n")

while tries < max_tries:
    guess = int(input(f"[{tries+1}/{max_tries}] 숫자를 입력하세요: "))
    tries += 1

    if guess == answer:
        print(f"🎉 정답! {tries}번 만에 맞췄습니다!")
        break
    elif guess > answer:
        print("📉 더 작은 수를 입력하세요.")
    else:
        print("📈 더 큰 수를 입력하세요.")
else:
    print(f"😢 실패! 정답은 {answer}이었습니다.")
```

</details>

### 🎯 응용 4-3 — 성적 분석기

학생 이름과 점수를 딕셔너리로 저장하고, 등급과 평균, 최고점, 최저점을 출력하세요. 등급 기준은 `A(90 이상)`, `B(80 이상)`, `C(70 이상)`, `D(60 이상)`, 나머지는 `F`입니다.

**새로 나오는 문법**

- `sum()`, `max()`, `min()`: 합계, 최댓값, 최솟값을 구합니다.
- `scores.values()`: 딕셔너리의 값만 꺼냅니다.
- `max(scores, key=scores.get)`: 값이 가장 큰 키, 즉 최고점 학생의 이름을 찾습니다.
- `{name:10s}`, `{score:3d}`, `{값:.1f}`: 글자를 10칸에 맞추기, 숫자를 3칸에 맞추기, 소수 첫째 자리까지 표시하기입니다.

```python
scores = {}
n = int(input("학생 수를 입력하세요: "))

for i in range(n):
    name = input(f" 학생 {i+1} 이름: ")
    score = int(input(f" {name}의 점수: "))
    scores[name] = score

print("\n📊 성적 결과")
print("-" * 25)
for name, score in scores.items():
    if score >= ___:
        grade = 'A'
    elif score >= ___:
        grade = 'B'
    elif score >= ___:
        grade = 'C'
    elif score >= ___:
        grade = 'D'
    else:
        grade = 'F'
    print(f"{name:10s}: {score:3d}점 ({grade})")

print("-" * 25)
if len(scores) == 0:
    print("입력된 학생이 없습니다.")
else:
    print(f"평균: {sum(scores.values()) / len(scores):.1f}점")
    print(f"최고: {max(scores, key=scores.get)} {max(scores.values())}점")
    print(f"최저: {min(scores, key=scores.get)} {min(scores.values())}점")
```

실행 예시:

```text
학생 수를 입력하세요: 2
 학생 1 이름: 김아주
 김아주의 점수: 95
 학생 2 이름: 홍길동
 홍길동의 점수: 70

📊 성적 결과
-------------------------
김아주       :  95점 (A)
홍길동       :  70점 (C)
-------------------------
평균: 82.5점
최고: 김아주 95점
최저: 홍길동 70점
```

<details markdown="1">
<summary>💡 힌트</summary>

`elif`는 위에서부터 검사하므로, 높은 점수 기준부터 차례로 씁니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
scores = {}
n = int(input("학생 수를 입력하세요: "))

for i in range(n):
    name = input(f" 학생 {i+1} 이름: ")
    score = int(input(f" {name}의 점수: "))
    scores[name] = score

print("\n📊 성적 결과")
print("-" * 25)
for name, score in scores.items():
    if score >= 90:
        grade = 'A'
    elif score >= 80:
        grade = 'B'
    elif score >= 70:
        grade = 'C'
    elif score >= 60:
        grade = 'D'
    else:
        grade = 'F'
    print(f"{name:10s}: {score:3d}점 ({grade})")

print("-" * 25)
if len(scores) == 0:
    print("입력된 학생이 없습니다.")
else:
    print(f"평균: {sum(scores.values()) / len(scores):.1f}점")
    print(f"최고: {max(scores, key=scores.get)} {max(scores.values())}점")
    print(f"최저: {min(scores, key=scores.get)} {min(scores.values())}점")
```

</details>

### 🎯 응용 4-4 — 피라미드 패턴 출력

높이 `n`을 입력받아 별(`*`) 피라미드를 출력하세요.

**새로 나오는 문법**

- 문자열에 숫자를 곱하면 그만큼 반복됩니다. `'*' * 3`은 `'***'`입니다.

```python
n = int(input("피라미드 높이를 입력하세요: "))

for i in range(1, n + 1):
    spaces = ' ' * ___
    stars = '*' * ___
    print(spaces + stars)
```

실행 예시:

```text
피라미드 높이를 입력하세요: 5
    *
   ***
  *****
 *******
*********
```

<details markdown="1">
<summary>💡 힌트</summary>

높이가 5일 때 줄마다 공백과 별의 수를 세어 보세요. `i`번째 줄의 공백은 `n - i`개, 별은 `2 * i - 1`개입니다.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
n = int(input("피라미드 높이를 입력하세요: "))

for i in range(1, n + 1):
    spaces = ' ' * (n - i)
    stars = '*' * (2 * i - 1)
    print(spaces + stars)
```

</details>

### 🎯 응용 4-5 — 단어 빈도 분석기

문장을 입력받아 각 단어가 몇 번 나오는지 딕셔너리로 세고, **많이 나온 순서**로 출력하세요.

**새로 나오는 문법**

- `.lower()`: 모든 글자를 소문자로 바꿉니다.
- `.split()`: 공백을 기준으로 문장을 나눠 리스트로 만듭니다.
- `sorted(..., key=lambda x: x[1], reverse=True)`: 각 쌍의 두 번째 값(횟수)을 기준으로 큰 값부터 정렬합니다. `lambda`는 나중에 배우니, 지금은 이 줄을 그대로 써도 됩니다.

```python
sentence = input("문장을 입력하세요: ").lower()
words = sentence.split()

word_count = {}
for word in words:
    if word in word_count:
        word_count[word] += ___   # 이미 있으면 1 늘리기
    else:
        word_count[word] = ___    # 처음 나왔으면 1로 시작

# 빈도 높은 순으로 정렬해서 출력
sorted_words = sorted(word_count.items(), key=lambda x: x[1], reverse=True)

print("\n📝 단어 빈도:")
for word, count in sorted_words:
    print(f"  {word}: {count}회")
```

실행 예시:

```text
문장을 입력하세요: The cat and the dog and the bird

📝 단어 빈도:
  the: 3회
  and: 2회
  cat: 1회
  dog: 1회
  bird: 1회
```

<details markdown="1">
<summary>💡 힌트</summary>

단어가 처음 나왔을 때의 횟수와, 다시 나왔을 때 늘어나는 양을 생각해 보세요.

</details>

<details markdown="1">
<summary>✅ 정답</summary>

```python
sentence = input("문장을 입력하세요: ").lower()
words = sentence.split()

word_count = {}
for word in words:
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

sorted_words = sorted(word_count.items(), key=lambda x: x[1], reverse=True)

print("\n📝 단어 빈도:")
for word, count in sorted_words:
    print(f"  {word}: {count}회")
```

</details>

---

<a id="monte-carlo"></a>

## 🎲 Monte Carlo Simulation

난수를 많이 뽑아 답을 어림하는 방법입니다. 여기서는 원주율 π를 구합니다.

**원리**

1. 한 변이 1인 정사각형 안에 점을 무작위로 찍습니다.
2. 정사각형 넓이는 1이고, 그 안의 사분원(반지름 1) 넓이는 π/4입니다.
3. 그래서 사분원 안에 들어간 점의 비율은 π/4에 가까워집니다.
4. 이 비율에 4를 곱하면 π의 근삿값이 됩니다.

점이 사분원 안에 있는지는 `x*x + y*y <= 1`로 판단합니다. `random.random()`은 0 이상 1 미만의 소수를 무작위로 고르고, `for _ in`의 `_`는 반복 변수를 쓰지 않는다는 표시입니다.

```python
import random

n = 10000
inside = 0

for _ in range(n):
    x = random.random()
    y = random.random()

    if x*x + y*y <= 1:
        inside += 1

pi = 4 * inside / n
print("원주율 근사값:", pi)
```

### 🔬 실험

`n`을 `100`, `10000`, `1000000`으로 바꿔 가며 각각 여러 번 실행해 보세요.

- 실제 원주율 3.14159…에 얼마나 가까워지나요?
- 같은 `n`으로 실행해도 결과가 달라지는 이유는 무엇일까요?

---

<a id="help"></a>

## 🆘 막혔을 때

에러가 나면 **맨 아래 줄**부터 읽어 보세요. 에러 이름과 원인이 적혀 있습니다.

| 에러 메시지 | 뜻 | 확인할 것 |
|---|---|---|
| `SyntaxError: expected ':'` | 콜론이 빠짐 | `if`, `for`, `while` 줄 끝의 `:` |
| `SyntaxError: invalid syntax. Maybe you meant '==' ...` | 조건에 `=`를 씀 | 비교는 `==` |
| `IndentationError: expected an indented block ...` | 들여쓰기가 없음 | `:` 다음 줄의 스페이스 4칸 |
| `NameError: name 'x' is not defined` | 없는 이름을 씀 | 오타, 빈칸(`___`), 변수를 만든 칸을 먼저 실행했는지 |
| `TypeError: can only concatenate str ...` | 문자열과 숫자를 더함 | `input()` 값을 `int()`로 바꿨는지 |
| `ValueError: invalid literal for int() ...` | 숫자가 아닌 값을 `int()`로 바꿈 | 숫자를 입력했는지 |
| `ZeroDivisionError: division by zero` | 0으로 나눔 | 나누는 값이 0이 되는 경우 |
| `IndexError: list index out of range` | 없는 위치를 찾음 | 인덱스는 0부터 `길이 - 1`까지 |
| `KeyError: '이름'` | 딕셔너리에 없는 키를 찾음 | 키의 철자 |

**그래도 안 풀리면**

1. 코드를 몇 줄씩 나눠 실행합니다.
2. 중간에 `print()`를 넣어 변수에 어떤 값이 들어 있는지 확인합니다.
3. `💡 힌트`를 다시 읽고, 그다음 `✅ 정답`을 보며 내 코드와 다른 곳을 찾습니다.

---

<a id="summary"></a>

## ✅ 배운 내용 정리

| 주제 | 핵심 문법 |
|---|---|
| 출력과 입력 | `print()`, `input()`, `int()`, `float()`, f-string |
| 연산 | `+`, `-`, `*`, `/`, `//`, `%`, `**` |
| 리스트 | `[ ]`, 인덱스 `[0]`, `len()` |
| 집합 | `set()`, 합집합 <code>&#124;</code>, 교집합 `&`, 차집합 `-` |
| 딕셔너리 | `{ }`, `dict[key]`, `del`, `.items()` |
| 조건문 | `if`, `elif`, `else`, `==`, `and`, `or` |
| for 반복문 | `for x in list`, `range()` |
| while 반복문 | `while 조건:`, `break`, `continue` |

---

## 💡 더 해 보기

1. 응용 문제 중 1개를 골라 내 마음대로 바꿔 보세요. 예를 들어 숫자 맞추기 게임의 범위와 기회를 바꿔 볼 수 있습니다.
2. 정답을 보지 않고 응용 문제를 처음부터 다시 작성해 보세요.
3. Monte Carlo Simulation에서 점을 찍는 횟수를 바꿔 가며 결과를 표로 정리해 보세요.
