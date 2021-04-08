---
title: "[Oracle] NVL(), NVL2()"
layout: single
date: 2021-04-07 20:00:00 +0900
author: 최수호
toc: true  
toc_sticky: true 
published : true
categories: 
  - orcale
tags:
  - NVL
  - nvl
  - NVL2
  - nvl2
  - 오라클 Null
---
# 1. Null값 처리 함수
## 01) NVL()
NVL(expr1, expr2) : expr1이 null값일 경우, expr2를 반환한다.

```sql
SELECT NAME, SCROE FROM STUDENT_SCORE;
```
![RANK() 결과](/assets/images/posts/oracle-nvl-function-result-01.jpg)

```sql
SELECT NAME, NVL(SCROE, '채점중') FROM STUDENT_SCORE;
```
![RANK() 결과](/assets/images/posts/oracle-nvl-function-result-02.jpg)

## 02) NVL2()
NVL2(expr1, expr2, expr3) : expr1이 null값일 경우, expr3을 반환하고, expr1이 null이 아닐경우 expr2를 반환한다.

```sql
SELECT NAME, SCROE FROM STUDENT_SCORE;
```
![RANK() 결과](/assets/images/posts/oracle-nvl-function-result-01.jpg)

```sql
SELECT NAME, NVL2(SCROE, '채점완료', '채점중') FROM STUDENT_SCORE;
```
![RANK() 결과](/assets/images/posts/oracle-nvl-function-result-03.jpg)


# 2. 예시 및 소스 (복뿟)
## 01) 테이블 생성
```sql
CREATE TABLE STUDENT_SCORE (
        NAME VARCHAR2(20) NOT NULL,
       SCORE VARCHAR2(20) NULL
);
```

## 02) 데이터 삽입
```sql
INSERT INTO STUDENT_SCORE (NAME, SCORE)
SELECT '김철수', 100   FROM DUAL
UNION ALL
SELECT '이만수', 95    FROM DUAL
UNION ALL
SELECT '김지영', 95    FROM DUAL
UNION ALL
SELECT '양수민', null  FROM DUAL
UNION ALL
SELECT '꽈뚜룹', null  FROM DUAL
UNION ALL
SELECT '응우엔', 70    FROM DUAL
UNION ALL
SELECT '외계인', 5     FROM DUAL
UNION ALL
SELECT '민정수', 20    FROM DUAL
;
```

## 03) 실행 쿼리
```sql
SELECT NAME, SCROE FROM STUDENT_SCORE;
SELECT NAME, NVL(SCROE, '채점중') FROM STUDENT_SCORE;
SELECT NAME, NVL2(SCROE, '채점완료', '채점중') FROM STUDENT_SCORE;
```

<script src="https://utteranc.es/client.js"
    repo="apt-get-install/apt-get-install.github.io"
    issue-term="title"
    theme="github-light"
    crossorigin="anonymous"
    async>
</script>