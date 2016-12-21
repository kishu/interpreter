<!-- $theme: default -->

CPU Instruction
===

![40%](https://upload.wikimedia.org/wikipedia/commons/thumb/e/ea/MIPS_Architecture_(Pipelined).svg/1280px-MIPS_Architecture_(Pipelined).svg.png)

---

# Instruction
- CPU를 동작하게 하는 명령
- CPU가 어떠한 동작을 실행하는데 필요한 정보
- 연산자(연산코드) **Operation(OP-Code)** 와
피연산자 **Operand**로 구성

  <table>
  <tr><td rowspan="2">Operation<br>(OP-Code)</td><td colspan="2">Operand</td></tr>
  <tr><td>MOD</td><td>Address</td></tr>
  </table>
  
---

# Operation
- CPU의 동작을 코드(bit)로 표현
- 연산자 종류, 명령어 형식, 데이터 종류 등 표현

> CPU가 32개의 명령을 사용한다면 Operation은 몇 bit여야 하는가?

---

# Operand

## mod
- 피연산자를 지정하는 방식. 직접주소 혹은 간접주소

## Address
- 처리할 피연산자가 저장된 메모리(혹은 레지스터)의 주소
- 또는 처리한 결과를 저장할 메모리(혹은 레티스터)의 주소

---

# Operation의 기능
- Functional Operation: 산술연산 및 논리연산, 시프트연산
- Transfer Operation: 레지스터 사이의 데이터 이동<br>또는 CPU - 메모리 사이 데이터 이동
- Control Operation: 명령어 해독, 수행순서 제어
- I/O Operation: I/O 장치 - 메모리간 데이터 이동

---

## Functional Operation
### 산술 연산
- ADD, SUB, MUL, DIV, INC, DEC ...
### 논리 연산
- AND, OR, XOR ...
### 시프트 연산
- 산술시프트, 논리시프트, ROTATE ...

---
## Transfer Operation
- LOAD
- STORE
- MOVE
- PUSH, POP
- INPUT
- OUTPUT

---
## Control Operation
- JUMP, SKIP
- CALL, RETURN
- HALT
- ... 

---

Instruction 형식
===
- Operand Address 수에 따라

---

# 0-주소 명령어
|Operation|
|:-:|
- Operation만 있고 Operand가 없다
- 스택 구조 CPU에서 사용
- 스택의 두 값을 POP해서 연산 수행 후 다시 스택에 PUSH
- 원래의 데이터를 모두 잃어버림

> `x = A + B * C`를 스택(후위연산 사용)을 이용해 계산해 보거라.

---

# 1-주소 명령어
|Operation|Operand|
|:-:|:-:|
- Operation과 1개의 Operand로 구성
- 누산기(ACCumulator) 필요
- 피연산자를 누산기에 저장하고 연산 결과를 다시 누산기에 저장

> `x = A + B * C`
> LOAD B -> MUL C -> ADD A -> STORE X

---

# 2-주소 명령어
|Operation|Operand|Operand|
|:-:|:-:|:-:|
- Operation과 2개의 Operand로 구성
- Operand가 지정한 2개의 데이터를 연산하고 첫번째 Operand에 저장

> `x = A + B * C`
> MUL B C -> ADD A B -> STORE X A








