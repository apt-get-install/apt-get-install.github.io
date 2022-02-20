---
title: "[Oracle] 다 건 삽입(MULTIPLE INSERT) 속도 비교"
layout: single
date: 2020-09-23 20:36:30 +0900
author: 최수호
toc: true  
toc_sticky: true 
published : true
categories: 
  - orcale
tags:
  - INSERT ALL
  - insert all
  - UNION ALL 
  - union all
  - multiple insert
  - multi insert
  - 다중 삽입
  - 다중 인서트
  - 속도 비교
---
# 1. 다 건 삽입(INSERT) 방법
아래 두 가지 방법에 대해 속보 비교를 해보려고 한다.
>결론부터 말하면, UNION ALL 방식이 매우 더 빨랐다.

## 01) INSERT ALL을 사용하는 방법
기본적인 사용 방법은 다음과 같다.

```sql
INSERT ALL 
    INTO [테이블] ( [COLUMN1], [COLUMN2], ...) VALUES ( [VALUE1], [VALUE2], ...)
    INTO [테이블] ( [COLUMN1], [COLUMN2], ...) VALUES ( [VALUE1], [VALUE2], ...)
	...
    INTO [테이블] ( [COLUMN1], [COLUMN2], ...) VALUES ( [VALUE1], [VALUE2], ...)
SELECT * FROM DUAL;
);
```
가장 하단의 SELECT * FROM DUAL이 없으면 오류가 발생한다.
>이유를 아시는분 설명 해주시면 정말 감사히 배우겠습니다.



## 02) UNION ALL을 사용하는 방법
기본적인 사용 방법은 다음과 같다.
```sql
INSERT INTO [테이블] ([COLUMN1], [COLUMN2], ...) 
	SELECT ([VALUE1], [VALUE2], ...) FROM DUAL UNION ALL 
	SELECT ([VALUE1], [VALUE2], ...) FROM DUAL UNION ALL
	...
	SELECT ([VALUE1], [VALUE2], ...) FROM DUAL
);
```

# 2. 속도 비교 결과
1,000건 삽입 기준으로, 다음과 같은 결과가 나왔다.

## 01) INSERT ALL
![INSERT ALL 1000건 삽입 결과](/assets/images/posts/oracle-insert-all-1000.jpg)

1,000건 : **437.865초**

## 02) UNION ALL
![INSERT ALL 1000건 삽입 결과](/assets/images/posts/oracle-union-all-1000.jpg)

1,000건 : **0.06초**

UNION ALL은 추가 테스트로, 10,000건도 진행해 보았다.
![INSERT ALL 10000건 삽입 결과](/assets/images/posts/oracle-union-all-10000.jpg)

10,000건 : **24.635초**


# 3. 예시 및 소스 (복뿟)
## 01) 테이블 생성
```sql
CREATE TABLE TEST (
	A_COM VARCHAR2(20),
	B_COL VARCHAR2(20),
	C_COL VARCHAR2(20)
);
```

## 02) 데이터 삽입
```sql
-- INSERT ALL 방식
INSERT ALL 
	INTO TEST ( A_COM, B_COL, C_COL ) VALUES ('val01','val02','val03')
	INTO TEST ( A_COM, B_COL, C_COL ) VALUES ('val01','val02','val03')
	...
	INTO TEST ( A_COM, B_COL, C_COL ) VALUES ('val01','val02','val03')
SELECT * FROM DUAL;
);

-- UNION ALL 방식
INSERT INTO TEST ( A_COM, B_COL, C_COL )
	SELECT ('val01','val02','val03') FROM DUAL UNION ALL
	SELECT ('val01','val02','val03') FROM DUAL UNION ALL
	...
	SELECT ('val01','val02','val03') FROM DUAL UNION ALL
);
```

<script src="https://utteranc.es/client.js"
    repo="apt-get-install/apt-get-install.github.io"
    issue-term="title"
    theme="github-light"
    crossorigin="anonymous"
    async>
</script>