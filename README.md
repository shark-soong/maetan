# 🐍 파이썬 기초 실습

> **학습 목표**  
> 집합(Set) / 딕셔너리(Dictionary) 복습 → 조건문(`if/elif/else`) → 반복문(`for/while`) → 응용 예제 → Monte Carlo Simulation

---

## 📚 실습 안내

이 저장소는 파이썬 기초 문법을 직접 따라하면서 익히기 위한 실습 자료입니다.

- 설명을 읽고
- 예제 코드를 실행해보고
- 연습 문제를 직접 풀어보세요.
- 빈칸이 있는 문제는 스스로 완성하는 것이 목표입니다.

---

## 📌 Part 1. 집합(Set) & 딕셔너리(Dictionary) 복습

### 1-1. 집합 (Set)

- `set()`으로 생성합니다.
- **중복을 허용하지 않습니다.**
- **순서가 없습니다.**

### 예제: 집합 생성과 연산

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

### ✏️ 연습 1-1

아래 리스트에서 **중복을 제거**한 집합을 만들고, 원소의 개수를 출력해보세요.

```python
numbers =[1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

# 여기에 코드를 작성하세요
```

---

### 1-2. 딕셔너리 (Dictionary)

- **키(key)** 와 **값(value)** 을 한 쌍으로 가지는 자료형입니다.

### 예제: 딕셔너리 생성과 수정

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

### ✏️ 연습 1-2

자신의 정보를 딕셔너리로 만들고, `for` 루프로 모든 키와 값을 출력해보세요.

```python
my_info = {
    '이름': '',          # 이름 입력
    '나이': 0,           # 나이 입력
    '좋아하는 언어': ''   # 언어 입력
}

# for key, value in my_info.items(): 를 활용해 출력해보세요
```

---

## 📌 Part 2. 조건문 (if / elif / else)

### 2-1. 기본 if - else

```python
if 조건:
    # 조건이 참일 때 실행
else:
    # 조건이 거짓일 때 실행
```

### 예제: 아이스크림 구매하기

```python
money = int(input("지갑에 있는 돈을 입력하세요 (원): "))

if money >= 1200:
    print("월드콘을 살 수 있어요! 🍦")
else:
    print("돈이 부족해요. 😢")
```

---

### 2-2. if - elif - else

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

---

### ✏️ 연습 2-2 — BMI 계산기

> BMI = 체중(kg) / 신장(m)²
>
- 저체중: 20 미만
- 정상: 20~25
- 과체중: 25~29.9
- 비만: 30~40
- 고도비만: 40.1 이상

```python
weight = float(input("체중(kg)을 입력하세요: "))
height = float(input("신장(cm)을 입력하세요: "))

height_m = height / 100  # cm → m 변환
bmi = weight / (height_m ** 2)
print(f"BMI: {bmi:.2f}")

# 아래에 조건문으로 판정 결과를 출력하세요
```

---

### ✏️ 연습 2-3 — 사칙연산 계산기

두 수와 연산자(`+`, `-`, `*`, `/`)를 입력받아 결과를 출력하세요.

```python
num1 = float(input("첫 번째 숫자: "))
op = input("연산자 (+, -, *, /): ")
num2 = float(input("두 번째 숫자: "))

# 여기에 코드를 작성하세요
```

---

## 📌 Part 3. 반복문 (for / while)

### 3-1. for 반복문 & range()

```python
for 변수 in 리스트/튜플/range():
    반복할 코드
```

### 예제 1: 리스트 순회

```python
fruits = ['사과', '바나나', '체리']

for fruit in fruits:
    print(fruit)
```

### 예제 2: 1부터 10까지 합 구하기

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
length = len(s) - 1

# for 문을 이용해 거꾸로 출력하세요
```

---

### 3-2. while 반복문

```python
while 조건:
    반복할 코드
```

### 예제: 카운트다운

```python
count = 5

while count > 0:
    print(count)
    count -= 1

print("발사! 🚀")
```

---

### 3-3. break & continue

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

원하는 단(`n`)을 입력받아 **while 문**으로 구구단을 출력하세요.

```python
num = int(input("구구단 몇 단을 출력할까요? "))

i = 1
while i <= 9:
    # 출력 코드를 완성하세요
    i += 1
```

---

## 🔥 Part 4. 응용 예제 (난이도 ★★☆)

> 지금까지 배운 조건문 + 반복문 + 자료형을 **함께** 활용해봅니다.

### 🎯 응용 4-1 — 소수(Prime Number) 판별기

1보다 큰 자연수 `n`을 입력받아, 소수인지 판별하세요.

- 힌트: 2부터 `n-1`까지 나누어지는 수가 있으면 소수가 아닙니다.
- `is_prime` 플래그 변수와 `for` + `break`를 활용하세요.

```python
n = int(input("자연수를 입력하세요: "))

is_prime = True

if n < 2:
    is_prime = False
else:
    for i in range(2, n):
        if n % i == 0:
            is_prime = # ← 이 줄을 직접 작성해보세요
            break

if is_prime == True:                  
    print(f"{n}은(는) 소수입니다! ✅")
else:
    print(f"{n}은(는) 소수가 아닙니다. ❌")
```

---

### 🎯 응용 4-2 — 숫자 맞추기 게임

컴퓨터가 1~100 사이 임의의 수를 정하고, 사용자가 맞출 때까지 힌트를 줍니다.

- 입력한 수가 정답보다 **크면** → `"📉 더 작은 수를 입력하세요."`
- 입력한 수가 정답보다 **작으면** → `"📈 더 큰 수를 입력하세요."`
- 최대 **7번** 안에 맞추면 성공, 실패하면 정답을 알려줍니다.

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

---

### 🎯 응용 4-3 — 성적 분석기

학생 이름과 점수를 딕셔너리로 저장하고, 평균·최고점·최저점을 구하세요.

- 점수에 따라 등급을 자동 부여합니다: `A(90↑)` / `B(80↑)` / `C(70↑)` / `D(60↑)` / `F`
- `max()`, `min()`, `sum()` 내장 함수를 활용하세요.

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
scores = {}
n = int(input("학생 수를 입력하세요: "))

for i in range(n):
    name = input(f" 학생 {i+1} 이름: ")
    score = int(input(f" {name}의 점수: "))
    scores[name] = score

print("\n📊 성적 결과")
print("-" * 25)
for name, score in scores.items():
    if score >= :                   #score >= 에 들어갈 숫자를 적어보세요!
        grade = 'A'
    elif score >= :
        grade = 'B'
    elif score >= :
        grade = 'C'
    elif score >= :
        grade = 'D'
    else:
        grade = 'F'
    print(f"{name:10s}: {score:3d}점 ({grade})")

print("-" * 25)
print(f"평균: {sum(scores.values()) / len(scores):.1f}점")
print(f"최고: {max(scores, key=scores.get)} {max(scores.values())}점")
print(f"최저: {min(scores, key=scores.get)} {min(scores.values())}점")
    print(f"{name:10s}: {score:3d}점 ({grade})")

print("-" * 25)
print(f"평균: {sum(scores.values()) / len(scores):.1f}점")
print(f"최고: {max(scores, key=scores.get)} {max(scores.values())}점")
print(f"최저: {min(scores, key=scores.get)} {min(scores.values())}점")
```

---

### 🎯 응용 4-4 — 피라미드 패턴 출력

`n`을 입력받아 아래와 같은 별(`*`) 피라미드를 출력하세요.

```
    *
   ***
  *****
 *******
*********
```

- 힌트: 공백 수 = `n - i`, 별 수 = `2*i - 1`

```python
n = int(input("피라미드 높이를 입력하세요: "))

for i in range(1, n + 1):
    spaces = ' ' * (n - i)
    stars = '*' * (2 * i - 1)
    print(spaces + stars)
```

---

### 🎯 응용 4-5 — 단어 빈도 분석기 (딕셔너리 + 반복문)

문장을 입력받아 각 단어가 몇 번 등장하는지 딕셔너리로 카운트하고, **빈도 높은 순**으로 출력하세요.

- `.lower()`로 대소문자를 통일하고, `.split()`으로 단어를 분리하세요.

```python
sentence = input("문장을 입력하세요: ").lower()
words = sentence.split()

word_count = {}
for word in words:         # word가 이미 딕셔너리에 있으면 +1, 없으면 1로 초기화
    if word in word_count:
        word_count[word] += 1
    else:
        word_count[word] = 1

# 빈도 높은 순으로 정렬해서 출력
sorted_words = sorted(word_count.items(), key=lambda x: x[1], reverse=True)

print("\n📝 단어 빈도:")
for word, count in sorted_words:
    print(f"  {word}: {count}회")
```

---

## 🎲 Monte Carlo Simulation

난수를 이용해 원주율 π 값을 근사하는 간단한 예제입니다.

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

---

## ✅ 오늘 배운 내용 정리

| 주제 | 핵심 문법 |
|------|-----------|
| 집합 | `set()`, 합집합 `\|`, 교집합 `&`, 차집합 `-` |
| 딕셔너리 | `{}`, `dict[key]`, `del`, `.items()` |
| 조건문 | `if`, `elif`, `else` |
| for 반복문 | `for x in list`, `range()` |
| while 반복문 | `while 조건:`, `break`, `continue` |

---

## 💡 실습 과제 제안

1. 각 연습 문제를 직접 풀어보기
2. 응용 예제 중 1개를 스스로 변형해보기
3. `Monte Carlo Simulation`에서 반복 횟수 `n`을 바꿔가며 결과 비교하기

---

## 💡 정답

<details markdown="1">
<summary>✏️ 연습 1-1 — 중복 제거 정답 보기</summary>

```python
numbers =[1, 2, 2, 3, 3, 3, 4, 4, 4, 4]

unique = set(numbers)
print("중복 제거된 집합:", unique)
print("원소의 개수:", len(unique))
```

</details>

---

<details markdown="1">
<summary>✏️ 연습 1-2 — 딕셔너리 출력 정답 보기</summary>

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

<details markdown="1">
<summary>✏️ 연습 2-1 — 두 수 비교 정답 보기</summary>

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

---

<details markdown="1">
<summary>✏️ 연습 2-2 — BMI 계산기 정답 보기</summary>

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

---

<details markdown="1">
<summary>✏️ 연습 2-3 — 사칙연산 계산기 정답 보기</summary>

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

<details markdown="1">
<summary>✏️ 연습 3-1 — 문자열 거꾸로 출력 정답 보기</summary>

```python
s = input("문장을 입력하세요: ")
length = len(s) - 1

for i in range(length, -1, -1):
    print(s[i], end='')
print()
```

</details>

---

<details markdown="1">
<summary>✏️ 연습 3-2 — while 구구단 출력 정답 보기</summary>

```python
num = int(input("구구단 몇 단을 출력할까요? "))

i = 1
while i <= 9:
    print(f"{num} x {i} = {num * i}")
    i += 1
```

</details>

---

<details markdown="1">
<summary>🎯 응용 4-1 — 소수 판별기 정답 보기</summary>

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

---

<details markdown="1">
<summary>🎯 응용 4-2 — 숫자 맞추기 게임 정답 보기</summary>

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

---

<details markdown="1">
<summary>🎯 응용 4-3 — 성적 분석기 정답 보기</summary>

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
print(f"평균: {sum(scores.values()) / len(scores):.1f}점")
print(f"최고: {max(scores, key=scores.get)} {max(scores.values())}점")
print(f"최저: {min(scores, key=scores.get)} {min(scores.values())}점")
    print(f"{name:10s}: {score:3d}점 ({grade})")

print("-" * 25)
print(f"평균: {sum(scores.values()) / len(scores):.1f}점")
print(f"최고: {max(scores, key=scores.get)} {max(scores.values())}점")
print(f"최저: {min(scores, key=scores.get)} {min(scores.values())}점")
```

</details>

---

<details markdown="1">
<summary>🎯 응용 4-4 — 피라미드 패턴 정답 보기</summary>

```python
n = int(input("피라미드 높이를 입력하세요: "))

for i in range(1, n + 1):
    spaces = ' ' * (n - i)
    stars = '*' * (2 * i - 1)
    print(spaces + stars)
```

</details>

---

<details markdown="1">
<summary>🎯 응용 4-5 — 단어 빈도 분석기 정답 보기</summary>

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
