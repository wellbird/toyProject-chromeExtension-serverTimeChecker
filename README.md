# 개인 토이 프로젝트
## 크롬 확장 기능 개발
### 서버 시간 확인
- 개요
  - 크롬 확장 기능 개발 경험
  - 티켓팅, 수강신청 등에 사용할 수 있는 서버 시간 확인 기능 개발
- 개발 환경
  - TypeScript
  - React
  - styled component
- 목표
  - 확장 프로그램이 실행된 페이지의 도메인 가져오기
  - 도메인에 아무 요청을 보내 받은 응답의 header에 있는 서버 시간 확인
  - performance API를 이용하여 대략적인 응답 전송 시간 확인
    ```
    const resourceEntries = performance.getEntriesByType('resource');
    const resourceEntry = resourceEntries.find(entry => entry.name === url);
    if (resourceEntry) {
      const responseTransferTime = resourceEntry.responseEnd - resourceEntry.responseStart;
      console.log('응답 전송 시간:', responseTransferTime.toFixed(2), '밀리초');
    }
    ```
  - 서버시간에 예상 응답 전송시간을 더하여 사용자에게 보여주기