## 문제
- 구글 TTS를 사용하기 위해 /var/lib/asterisk/agi-bin/propolys-tts.agi 파일 변경함
- FreePBX에 다음과 같은 경고가 뜸

  ![Security Warning](https://wiki.freepbx.org/download/attachments/24052326/red_expand.png?version=1&modificationDate=1400618104000&api=v2)

  ![Dashboard](https://wiki.freepbx.org/download/attachments/24052326/WrNbBzr.png?version=1&modificationDate=1412813747000&api=v2)

## Security Warning 없애는 방법
- telnet에서 다음 명령 실행
```
> fwconsole chown
> fwconsole ma refreshsignatures
> fwconsole reload
```
- FreePBX에서 새로고침 후 없어진것 확인

## 경고 이유
- 문서에 있는 설명: FreePBX는 모든 공식 모듈에 내장 된 서명 검증 시스템을 갖췄다. 
이는 최종 사용자가 예기치 않게 모듈이 예기치 않게 수정되었는지 (예 : 보안 취약성 또는 악의적 인 모듈) 쉽게 알 수 있도록 하기 위한 것이다.
  

> 참조 링크: [Module Signing](https://wiki.freepbx.org/display/F2/Module+Signing#ModuleSigning-Upgradingfrom2.11andhaveunsignedmodules?), [fwconsole commands](https://wiki.freepbx.org/pages/viewpage.action?pageId=37912685#fwconsolecommands(13+)-Reload)
