---
title: netlify - freenom
date: "2019-10-27"
description: netlify 사이트에 도메인 연결(freenom).
---

## 의문

구글 검색에 내 블로그가 안나온다.

보니까 netlify 사이트 설정이 완료가 되지 않은 상태였다.
3단계 중 1단계만 완료.
2. set up a custom domain

3. secure your site with https

netlify가 준 랜덤한 주소 그대로 쓰려고 했으나,(https://sad-lamarr-6225f8.netlify.com)
도메인 등록은 선택이 아닌 필수인듯?

## 도메인 구매 (무료)
https://my.freenom.com/clientarea.php?action=domaindetails

여기서 도메인을 등록한다.

tk 가 제일 유명한? 도메인이라고 한다. 이걸 쓰겠다.

근데 이유 없이 등록이 완료 되지 않았다.
tk 서버가 느려서라고 한다.

어떻게 하다보니 됐다.. 
도메인 연결 후 사용에는 문제가 없다고 한다.

## netlify에서 도메인 등록

dns 설정 확인하라는 메시지

set up netlify

네임서버를 업데이트하라고 한다.
dns1.p05.nsone.net
dns2.p05.nsone.net
dns3.p05.nsone.net
dns4.p05.nsone.net

## freenom에서 네임서버 업데이트

management tools - nameservers - use custom nameservers

netlify에서 연결하라고 한 네임서버 연결

연결에 좀 시간이 걸린다.

완료 되면 노란 워닝이 없어짐.

## verify https

## justinaus.tk 접속


아직은 구글 검색에 안나옴 시간이 좀 걸리는지, 뭔가 잘못됐는지.






