---
title: "간편한 마크업 블로그 : 깃 허브 블로그"
date: 2018-09-03 19:48:33 -0400
categories: github blog jekyll
---

# 간편한 마크업 블로그 : 깃 허브 블로그
* 개발자를 위한 마크업 블로그
* jekyll(ruby) + github 의 조합

## 장점
* 무설치 가능
 > 포스트만이 목적이라면 설치하지 않고 개인 블로그 개설 가능
* 깃 허브 페이지 소스 컨트롤
 > 히스토리 관리
 > 저장소
* 커스터 마이징 가능
 > 리소스 풍부 ( 테마, 템플릿, 기능 )
 > 심도 깊은 웹페이지 개발을 원한다면 jekyll 설치
* 호스팅 서버 필요 없음
 > 깃 허브 주소가 호스팅 주소
 >> "#{userName}.giothub.io
 > baseurl을 통해 프로젝트 별 페이지도 구분 가능

## 적용 방법 및 트러블 슈팅
1. jekyll theme 검색
 > minimal-mistakes
2. 해당 테마 github 페이지 접속
 > https://github.com/mmistakes/minimal-mistakes
3. Readme.md 를 읽고 install 따라하기
 > 무설치를 위한 github pages method를 따라 함
 >> github repogit 생성
 >> gemfile 생성
 >> _config.yml 복사 후 커스터마이징
 >>> **remote_theme: "mmistakes/minimal-mistakes"?**
 >> index.html 복사 후 내용의 대상 파일 추가 복사
 >>> _layouts/home.html 복사
4. 테스트
 > https://ilhaeye.github.io 접속
 > index.html 페이지 정상 동작 확인
5. 게시글 작성
 > _posts/2018-09-03-post-name.md
 >> 마크업 언어로 게시글 작성
 ```
 ---
 title: "게시글 제목"
 date: 2000-01-01 00:00:00 -0400
 categories: cate1 cate2
 ---
 content 작성
 ```
