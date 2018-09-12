---
title: "(문제해결)XCode 커맨드라인 툴 설정 문제"
date: 2018-09-03 20:57:12 -0400
categories: xcode trouble-shooting unreal
---

## 문제 상황
XCode 업데이트 이후, 언리얼 엔진 에디터가 정상동작하지 않는다.  
언리얼 엔진에서는 XCode가 오래된 버전이므로 업데이트를 요구하고 있었지만 내 XCode는 이미 최신버전이다.  
그 후 에디터에서 컴파일은 커녕, 클래스 생성조차 되지 않는다.  
```
Compile error
ERROR: Invalid SDK MacOSX.sdk, not found in /Library/Developer/CommandLineTools/Platforms/MacOSX.platform/Developer/SDKs
```

## 원인 파악
아마 Brew 설치 후 환경에 따라 xcode command line tools 경로에 문제가 생긴 것으로 보인다.  
구글링 결과 xcode command line tools 가 정상적으로 설정되어 있지 않았다는 내용을 발견하였다.  
XCode의 Xcode > Preferences > Locations을 열어 보았더니 아래 이미지와 같이 Command Line Tools가 비어 있음을 확인하였다.[^1]  
![Empty Command Line Tools]({{ "/assets/ts-command-line-tool.png" | absolute_url }})  

## 해결
기본적으론 콤보박스를 선택하여 커맨드 라인 툴의 버전을 선택하면 설정이 되지만 내 XCode는 반응하지 않았다.  

XCode 커맨드 툴 라인 설정 방법을 찾아본 결과 아래와 같이 해결하였다.[^2]  
``` 
터미널을 활성화 한다.
"sudo xcode-select -r" 입력
```
xcode-select를 이용하여 커맨드 라인 툴 경로를 초기화하여 해당 문제를 해결하였다.  

## 참고 페이지
[^1]: https://community.gamedev.tv/t/ue4-editor-error-when-creating-new-project-on-mac/16311  
[^2]: https://answers.unrealengine.com/questions/470427/i-cant-create-a-c-project-on-my-os-x.html  

