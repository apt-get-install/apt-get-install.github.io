---
title: "[Oracle] RANK(), DENSE_RANK()"
layout: single
date: 2020-05-24 20:36:30 +0900
author: 최수호
toc: true  
toc_sticky: true 
published : true
categories: 
  - orcale
tags:
  - rank
  - dens_rank
  - 랭크
  - 순위
---
# 1. 순위(랭크) 함수
## 01) RANK()
RANK() : 중복 순위도 카운트

(예: 1, 2, 2, 4, 5...)

![RANK() 결과](/assets/images/posts/oracle-rank-function-result.jpg)


## 02) DENSE_RANK()
DENSE_RANK() : 중복 순위는 밀집하여(DENSE) 카운트

(예: 1, 2, 2, 3, 4...)

![DENSE_RANK() 결과](/assets/images/posts/oracle-dense-rank-function-result.jpg)


# 2. 예시 및 소스 (복뿟)
## 01) 테이블 생성
```sql
CREATE TABLE STUDENT_SCORE (
        NAME VARCHAR2(20) NOT NULL,
       SCORE NUMBER(3)    NOT NULL
);
```

## 02) 데이터 삽입
```sql
INSERT INTO STUDENT_SCORE (NAME, SCORE)
SELECT '김철수', 100 FROM DUAL
UNION ALL
SELECT '이만수', 95  FROM DUAL
UNION ALL
SELECT '김지영', 95  FROM DUAL
UNION ALL
SELECT '양수민', 80  FROM DUAL
UNION ALL
SELECT '꽈뚜룹', 75  FROM DUAL
UNION ALL
SELECT '응우엔', 70  FROM DUAL
UNION ALL
SELECT '외계인', 5   FROM DUAL
UNION ALL
SELECT '민정수', 20  FROM DUAL
;
```

## 03) 실행 쿼리
```sql
SELECT NAME,
       SCORE,
       RANK() OVER (ORDER BY SCORE DESC)             RANK,
       DENSE_RANK() OVER (ORDER BY SCORE DESC) DENSE_RANK
  FROM STUDENT_SCORE
 ORDER BY SCORE DESC;
```

<script src="https://utteranc.es/client.js"
    repo="apt-get-install/apt-get-install.github.io"
    issue-term="title"
    theme="github-light"
    crossorigin="anonymous"
    async>
</script>