# 설치 가이드 📦

## Claude Code 설치

### 1. Claude Code 다운로드
- [claude.ai/code](https://claude.ai/code)에서 다운로드
- Windows/Mac 지원

### 2. 로그인
```
claude login
```

## MCP 서비스 연결

### 필수 연결 서비스
워크숍에서 사용할 서비스들을 미리 연결해주세요.

#### Gmail
1. [claude.ai/settings/connectors](https://claude.ai/settings/connectors) 접속
2. Gmail 연결 버튼 클릭
3. Google 계정 인증

#### Slack  
1. 개인 workspace 또는 회사 workspace 연결
2. 회사 제한이 있는 경우 개인 workspace 사용

#### Google Calendar
1. Gmail과 동일한 Google 계정으로 연결
2. 캘린더 읽기 권한 허용

### 연결 확인
```bash
/mcp
```
- Gmail, Slack, Calendar가 모두 연결되어 있는지 확인

## 스킬 설치

### 워크숍 스킬
```bash
npx skills add skills-workshop
```

### Monday-Checklist 스킬  
```bash
npx skills add monday-checklist
```

## 문제 해결

### 스킬 설치 실패
```bash
# 캐시 클리어 후 재시도
npx clear-npx-cache
npx skills add skills-workshop
```

### MCP 연결 실패
1. 브라우저에서 로그아웃 후 재로그인
2. 권한 설정 다시 확인
3. `/mcp` 명령어로 연결 상태 재확인

### 권한 오류
```bash
# Claude Code 재시작
claude logout
claude login
```

## 워크숍 시작
모든 설치가 완료되면:
```bash
/skills-workshop
```

🎉 **준비 완료!** 이제 "내 일 편하게 하기" 여정을 시작하세요!