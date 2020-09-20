---
title: "[jqGrid] addJSONData()"
layout: single
date: 2020-09-20 23:36:30 +0900
author: 최수호
toc: true  
toc_sticky: true 
published : true
categories: 
  - jqGrid
tags:
  - addJSONData
  - jqGrid
  - JSON
---
# 1. jqGrid에 JSON 타입으로 데이터 한번에 넣기
## 01) JSON 데이터 (복뿟)
```javascript
var addJsonData = [
	{ID : '1', ITEM : '값1', RESULTVALUE : 'val01', typeval:"nomal"},
	{ID : '2', ITEM : '값2', RESULTVALUE : 'val02', typeval:"nomal"},
	{ID : '3', ITEM : '값3', RESULTVALUE : 'val03', typeval:"nomal"},
	{ID : '4', ITEM : '값4', RESULTVALUE : 'val04', typeval:"nomal"},
	{ID : '5', ITEM : '값5', RESULTVALUE : 'val05', typeval:"nomal"},
	{ID : '6', ITEM : '값6', RESULTVALUE : 'val06', typeval:"nomal"},
	{ID : '7', ITEM : '값7', RESULTVALUE : 'val07', typeval:"nomal"}
];
```


## 02) addJSONData() 사용 (복뿟)
```javascript
$("#jqGridId)[0].addJSONData(addJsonData);
```


<script src="https://utteranc.es/client.js"
    repo="apt-get-install/apt-get-install.github.io"
    issue-term="title"
    theme="github-light"
    crossorigin="anonymous"
    async>
</script>