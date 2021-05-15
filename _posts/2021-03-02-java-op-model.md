---
title: 자바의 실행모델
author: 박경덕
date: 2021-03-02 15:09:00 +0900
categories: [언어, Java]
tags: [compile, low-level, cs]
---

## 전통적인 컴파일 방식 (ex. C, C++)

### 1. 전처리기
* 주석 제거
* include 파일 선언 복사
* define 치환

### 2. 컴파일러
* 소스 코드를 어셈블리어로 변환

### 3. 어셈블러
* 어셈블리어를 기계어, 바이너리 코드로 변환

### 4. 링커
* 함수 선언을 정의(내용)와 연결함

## 자바의 컴파일 방식
* 컴파일 시 JVM이 이해하는 바이트 코드(Byte Code)로 변환.
* JVM은 각 플랫폼(Windows, Linux, Mac..)마다 다르다.
