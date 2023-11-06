# 파이썬
## 파이썬 문법
### 들여쓰기(Indent)

파이썬의 대표적인 특징 중 하나는 코드 블록을 들여쓰기로 구분한다는 것입니다. 이 들여쓰기 규칙은 PEP 8 (Python Enhancement Proposal 8)에서 제공하는 공식 가이드에 따라서 4칸의 공백을 원칙으로 합니다. 들여쓰기는 코드 블록의 시작을 나타내고, 같은 레벨의 코드 블록은 동일한 들여쓰기 수준을 가져야 합니다.

아래는 들여쓰기의 예시입니다.
```python
def main():
    if True:
        print("조건이 참입니다.")
        for i in range(3):
            print("반복문 안의 코드입니다.")
        print("반복문 종료")
    else:
        print("조건이 거짓입니다.")
    
    print("함수 종료"
```
이 예시에서 볼 수 있듯이, 각 코드 블록은 4칸씩 들여쓰기되어 있으며, 코드 블록의 시작과 끝이 들여쓰기로 명확하게 구분되어 있습니다. 이렇게 들여쓰기를 사용하여 파이썬은 코드의 구조를 파악하고 실행합니다.

들여쓰기 규칙을 잘 따르면 코드의 가독성이 향상되며, 문법 오류를 방지할 수 있습니다. 그러므로 파이썬 코드를 작성할 때는 항상 PEP 8 가이드에 따른 인덴트 규칙을 준수하는 것이 좋습니다.
### 네이밍 컨벤션
파이썬은 네이밍 컨벤션 측면에서 스네이크 케이스(Snake Case)를 따릅니다. 스네이크 케이스는 변수, 함수, 메서드, 모듈 등의 이름을 작성할 때 단어들을 모두 소문자로 쓰고 단어 사이를 언더스코어(_)로 구분하는 방식입니다. 이는 파이썬의 PEP 8 스타일 가이드에 포함되어 있으며, 파이썬 커뮤니티에서 권장하는 규칙 중 하나입니다.
```
변수 이름: my_variable
함수 이름: calculate_average_score()
모듈 이름: my_module
```
파이썬 커뮤니티는 코드의 일관성과 가독성을 높이기 위해 스네이크 케이스를 선호하며, PEP 8과 파이썬의 철학인 파이썬다운(Pythonic) 코드 작성 방식을 따르는 것이 중요합니다.
### 타입 힌트
파이썬은 동적 타이핑 언어로 유명하지만, PEP 484부터는 타입 힌트(type hint)를 지원하게 되었습니다. 이를 통해 개발자는 변수, 함수 매개변수, 함수 반환값 등에 대한 타입 정보를 제공하고, 이 정보를 통해 타입 검사 도구와 IDE 등이 타입 체크와 코드 자동 완성을 지원할 수 있게 되었습니다. 파이썬 3.5 버전부터 이 타입 힌트를 사용할 수 있으며, 이를 활용하여 코드의 가독성과 안정성을 높일 수 있습니다.

타입 힌트의 예시:
```python
def add_numbers(a: int, b: int) -> int:
    return a + b

result = add_numbers(3, 5)
```

위의 코드에서 함수 add_numbers의 매개변수 a와 b, 그리고 반환값이 int 타입으로 타입 힌트가 제공되었습니다.

타입 힌트의 중요한 이유:

- 가독성 향상: 타입 힌트를 사용하면 코드를 읽는 사람들이 변수나 함수의 의도된 타입을 쉽게 이해할 수 있습니다. 이로써 코드의 가독성이 향상되며, 다른 개발자들과의 협업이 더 쉬워집니다.

- 타입 체크 도구 지원: 타입 힌트를 사용하면 타입 검사 도구, 예를 들어 mypy와 같은 도구를 활용하여 코드의 타입 안정성을 검증할 수 있습니다. 이를 통해 런타임 오류를 사전에 방지할 수 있습니다.
### 리스트 컴프리핸션
리스트 컴프리헨션은 Python에서 리스트를 생성하거나 변형하는 간결한 방법을 제공합니다. map 및 filter 함수와 비교했을 때, 리스트 컴프리헨션은 코드의 가독성을 높일 뿐만 아니라 코드를 간결하게 유지할 수 있습니다.
1에서 10까지의 제곱을 포함하는 리스트 생성 예제:
```python
squares = [x**2 for x in range(1, 10 + 1)]
print(squares)
#[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
### 제너레이터
제너레이터(Generator)는 반복(iteration)을 지원하는 파이썬의 특별한 종류의 함수입니다. 제너레이터는 값을 만들어 내는 함수로, 값을 생성하고 호출자에게 하나씩 반환하는 동안 중간 상태를 유지합니다. 이를 통해 메모리를 효율적으로 사용할 수 있으며, 큰 데이터 집합을 처리할 때 유용합니다. 제너레이터 함수에서 yield 키워드를 사용하여 값을 반환합니다. 이 yield 키워드는 함수의 실행 상태를 일시 중지하고 호출자에게 값을 반환하며, 다음 호출 시 이전 상태를 유지한 채로 계속 실행됩니다.
```python
def number_generator(n):
    for i in range(n):
        yield i

# 제너레이터 생성
gen = number_generator(100000000)

# 반복문을 통해 제너레이터의 값을 하나씩 얻어옴
for num in gen:
    print(num)
```
위의 함수는 1부터 1억까지의 숫자를 생성하는 제너레이터 함수를 정의합니다. 이 함수는 yield를 사용하여 값을 반환하고 함수의 상태를 유지합니다. 반복문을 통해 이 제너레이터를 호출하면, 각 반복마다 다음 값을 반환하게 됩니다. 이러한 방식으로 제너레이터를 사용하면 큰 데이터 집합을 메모리에 한꺼번에 로드하지 않고 필요한 값만 생성하여 효율적으로 처리할 수 있습니다.

### range
대표적인 제너레이터 함수 중 하나가 range() 함수입니다. range() 함수는 숫자의 시퀀스를 생성하는 데 사용됩니다. 아래는 100만개 숫자를 생성하는 두가지 예시입니다.
```python
import sys

a = range(1000000)
sys.getsizeof(a)
# range() 함수를 사용한 경우 메모리 사용량: 48 bytes

b = (n for n in range(1000000))
sys.getsizeof(b)
# 리스트 컴프리핸션을 사용한 경우 메모리 사용량: 8697456 bytes
```
'range()' 함수는 더 효율적으로 메모리를 사용하는 것을 보여줍니다. 리스트 컴프리헨션을 사용하면 모든 값을 한 번에 생성하여 메모리 사용량이 가장 높습니다.
### enumerate
enumerate() 함수는 파이썬에서 자료형(리스트, 집합, 튜플)을 인덱스와 함께 열거하는 데 사용되는 함수입니다. 이 함수는 열거 객체(enumerate object)를 생성하며, 각 요소와 해당 인덱스를 포함합니다. 주로 반복문에서 요소와 인덱스를 함께 사용할 때 편리하게 활용됩니다.
예시:
```python
a = ['apple', 'banana', 'cherry']
for i, v in enumerate(a):
    print(f"인덱스 {i}: {v}")
```
결과:
```yaml
인덱스 0: apple
인덱스 1: banana
인덱스 2: cherry
```
### // 나눗셈 연산자

파이썬 2 이하에서는 기본 나눗셈 연산자 / 는 타입을 유지합니다. 따라서 정수를 정수로 나누어도 정수 형태의 결과를 반환합니다. 예를 들어, 5 / 3을 실행하면 결과는 1이 됩니다.

그러나 파이썬 3 이상에서는 나눗셈 연산자 동작 방식이 변경되었습니다. PEP 238에서 이 변경이 제안되었고, 파이썬 3 이상에서는 / 연산자를 사용하여 나눗셈을 하면 항상 부동 소수점 형태의 결과가 반환됩니다. 즉, 5 / 3을 실행하면 결과는 1.6666666666666667과 같은 부동 소수점 숫자가 반환됩니다.

이와는 별도로, 파이썬 3 이상에서는 정수형을 나눗셈할 때 몫을 구하기 위해 // 연산자를 사용할 수 있습니다. // 연산자는 나눗셈 결과의 소수 부분을 버리고 정수 몫만 반환합니다. 예를 들어, 5 // 3을 실행하면 결과는 1이 됩니다.

나머지를 구하기 위해서는 % 연산자를 사용하고, 몫과 나머지를 함께 구하기 위해 divmod() 함수를 사용할 수 있습니다.
```python
# 파이썬 2 이하에서 나눗셈 연산
result = 5 / 3
print(result)  # 출력: 1

# 파이썬 3 이상에서 나눗셈 연산
result = 5 / 3
print(result)  # 출력: 1.6666666666666667

# 정수 몫을 구하기 위해 // 연산자 사용
integer_quotient = 5 // 3
print(integer_quotient)  # 출력: 1

# 나머지를 구하기 위해 % 연산자 사용
remainder = 5 % 3
print(remainder)  # 출력: 2

# 몫과 나머지를 함께 구하기 위해 divmod() 함수 사용
quotient, remainder = divmod(5, 3)
print(quotient)  # 출력: 1
print(remainder)  # 출력: 2
```

### print
디버깅을 위해 print() 함수를 사용하는 것은 매우 일반적입니다. 아래에 몇 가지 print() 함수를 사용한 예시입니다.

1. 콤마(,)로 값을 구분하여 출력하는 방법:
```python
x = 10
y = 20
print("x:", x, "y:", y)
# 출력: x: 10 y: 20
```
2. `sep` 파라미터를 사용하여 구분자를 지정하는 방법:
```python
x = 10
y = 20
print(x, y, sep=', ')
# 출력: 10, 20
```
3. `end` 파라미터를 사용하여 줄 바꿈을 제한하는 방법:
```python
for i in range(5):
    print(i, end=' ')
# 출력: 0 1 2 3 4
```
4. 리스트를 출력할 때 `join()`을 사용:
```python
my_list = [1, 2, 3, 4, 5]
print(', '.join(map(str, my_list))
# 출력: 1, 2, 3, 4, 5
```
5. 인덱스와 값을 함께 출력하는 예시:
```python
fruits = ["apple", "banana", "cherry"]
for index, fruit in enumerate(fruits):
    print("Index {} - {}".format(index + 1, fruit))
# 출력:
# Index 1 - apple
# Index 2 - banana
# Index 3 - cherry

```
6. f-string을 사용한 예시(파이썬 3.6+):
```python
name = "Sungbin"
age = 26
print(f"My name is {name} and I am {age} years old.")
# 출력: My name is Sungbin and I am 26 years old.
```
### pass

### locals

## 코딩 스타일

### 변수명과 주석

####
