---
title: Unsigned 정수
author: 박경덕
date: 2021-03-02 17:32:00 +0900
categories: [언어, Java]
---

자바는 char를 제외하면 unsigned 정수타입을 지원하지 않는다.

그로 인해 발생하는 문제가 크게 2개가 있다.

### 1. 음수가 될 수 없는 값에 대해 한번 더 체크해줘야함.

```java
if (age < 0) {
    // do something
}
```
나이가 음수가 될 일은 존재하지 않으므로 애초에 unsigned int를 쓰면

불필요한 검증을 생략할 수 있다.

하지만 반대로 unsigned int는

```java
int age = 0;
age--;
```

saveAge(age);

라는 상황에서 값이 오버플로우 됨에 따라 이상한 값이 들어가게 될텐데 이걸 걸러줄 기준이 애매해진다..

이때는 "나이가 몇 살 이하일 경우"로 체킹해야하는가? 그걸 몇 살로 할지, 나이가 아니라 금액이라면?

반대로 signed int의 경우 음수체킹하면 간단하게 넘어갈 수 있다. 왜냐면 나이가 음수인 경우는 없기때문에.

따라서 이 부분은 좀 애매하다고 할 수 있겠다.

### 2. 일반적인 데이터들이 unsigned 기준으로 맞춰져있다.

색상 정보를 나타내는 RGB값의 범위는 각각 0 - 255 이다.

따라서 다른 언어의 경우 byte를 사용해서 나타냄.

자바의 경우 호환을 위해 byte를 short으로 변환하는 과정이 추가로 필요함.
