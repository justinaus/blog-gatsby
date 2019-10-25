---
title: VirtualBox 자동 종료 막기
date: "2019-10-25"
description: VirtualBox 자동 종료 막기.
---

## 문제

VirtualBox에서 윈도우 환경으로 테스트를 종종 하는데, 일정 시간이 지나면 자동으로 꺼져서 짜증난다.

## 해결책

정확한 이유는 잘 모르겠다. 해결책만 안다.

자세한 내용은 [링크](https://superuser.com/questions/479376/virtualbox-machine-auto-shutting-down-how-do-i-stop-it-from-auto-shutdown) 참고.

관리자 권한으로 프롬프트 열고
```bash
slmgr /rearm
```

## troubleshooting
```
Error: 0xC004F025 Access denied: the requested action requires elevated privileges.
```
프롬프트를 열 때 우클릭 - 관리자 권한으로 실행.

