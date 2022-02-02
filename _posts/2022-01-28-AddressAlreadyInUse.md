---
title:  "Address already in use 해결방법"
excerpt: "Address already in use : JVM_BIND 에러 해결방법"

categories:
  - Eclipse
tags:
  - [Address already in use, JVM_BIND, Address already in use bind, Address already in use 해결, Address already in use 80, Address already in use JVM_Bind null 8080]

date: 2021-01-28
last_modified_at: 2021-01-28

permalink: /about/
title: "About"
toc: true
toc_sticky: true
toc_label: "MYSELF"
---

> Address already in use : JVM_BIND 에러 해결방법

## 1.  같은 포트를 사용중인 다른 프로젝트 확인 

* __이클립스에서 같은 포트를 사용하는 다른 프로젝트가 있는지 확인__  
두 개의 프로젝트에서 동시에 같은 포트번호를 사용하려고 할 때  
Address already in use : JVM_BIND 에러가 나타난다.

## 2. CMD
 ![AddressAlreadyInUse_01](https://user-images.githubusercontent.com/94930976/151442423-42da0991-0759-47a9-b3c9-7ae0d4f678c9.png)
* 윈도우 사용시 단축키 Window + R 누른 후 cmd를 입력한다

## 3. netstat -ano

![AddressAlreadyInUse_02](https://user-images.githubusercontent.com/94930976/151442435-88f171e5-5cf1-4f23-bbec-123f95ce2399.png)

* 사용중인 포트를 확인할 수 있는 netstat -ano를 입력한다

## 4. PID번호 확인
![AddressAlreadyInUse_03](https://user-images.githubusercontent.com/94930976/151442449-b51499cb-c37f-4321-8083-4c0dc56a8b78.png)
* __내가 사용하고자 하는 포트번호를 찾아 PID(가장 우측번호)번호 확인__  
사용하고자 하는 포트번호는 개인마다 다르니 실행하고자하는 톰캣의 포트번호 확인 필요  
EX) 포트번호 : 5005, PID번호 : 53044

## 5. taskkill /f /pid 피드번호
![AddressAlreadyInUse_05](https://user-images.githubusercontent.com/94930976/151442454-932e99dd-7cb8-43ae-b05d-d70b78c67698.png)
* __명령어 : taskkill /f /pid 피드번호__  
EX) taskkill /f pid 53044  
위 명령어를 실행하면 Address already in use 에러가 나타나지 않는다.

## 번외. Tomcat 포트번호 확인방법
![AddressAlreadyInUse_06](https://user-images.githubusercontent.com/94930976/151444124-f99fdae5-11b4-4ab9-863c-854e8980e1fd.png)
