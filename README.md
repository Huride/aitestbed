# Vercel 초기 세팅 및 배포 상세 가이드

이 가이드는 Vercel 계정 생성부터 첫 웹페이지 배포까지의 모든 과정을 처음 시작하는 사용자의 관점에서 설명합니다.

---

## 1. Vercel 계정 생성 및 가입 (Sign Up)

Vercel은 GitHub, GitLab, Bitbucket 등과 연동하여 사용하는 것이 가장 강력합니다.

1. [Vercel 공식 홈페이지](https://vercel.com/signup)에 접속합니다.
2. **Continue with GitHub** (추천) 또는 이메일로 가입을 진행합니다.
3. 가입 절차에 따라 이메일 인증 등을 완료합니다.

## 2. 사전 준비 사항 (Prerequisites)

Vercel CLI를 설치하고 실행하기 위해 **Node.js**가 필요합니다.

1. 터미널(Terminal)에서 아래 명령어를 입력해 설치 여부를 확인합니다.
   ```bash
   node -v
   npm -v
   ```
2. 만약 버전이 나오지 않는다면, [Node.js 공식 홈페이지](https://nodejs.org/)에서 LTS 버전을 다운로드하여 설치하세요.

## 3. Vercel CLI 설치

터미널을 열고 아래 명령어를 입력하여 Vercel CLI를 전역(Global)으로 설치합니다.

```bash
npm install -g vercel
```

설치가 완료되었는지 확인하려면 다음 명령어를 입력하세요:
```bash
vercel --version
```

## 4. Vercel CLI 로그인 인증

설치된 CLI를 본인의 Vercel 계정과 연결해야 합니다.

1. 터미널에 아래 명령어를 입력합니다.
   ```bash
   vercel login
   ```
2. 브라우저가 열리면 로그인 방식(GitHub 등)을 선택하여 인증을 완료합니다.
3. 성공하면 터미널에 `Success! Verified [본인의 이메일]` 메시지가 나타납니다.

## 5. 프로젝트 배포하기

이제 배포하고 싶은 웹페이지가 있는 폴더로 이동합니다.

1. 터미널에서 해당 폴더로 이동한 후 다음 명령어를 입력합니다.
   ```bash
   vercel
   ```
2. 배포 과정에서 나오는 질문들에 답합니다 (보통 모두 `Enter`를 눌러 기본값으로 진행해도 무방합니다):
   - `Set up and deploy? [Y/n]`: **Y** (Enter)
   - `Which scope do you want to deploy to?`: **본인의 계정** (Enter)
   - `Link to existing project? [y/N]`: **N** (Enter - 새 프로젝트 생성 시)
   - `What's your project's name?`: (원하는 이름 입력 또는 기본값 사용)
   - `In which directory is your code located?`: **./** (Enter)
   - `Want to modify settings? [y/N]`: **N** (Enter)

3. 잠시 기다리면 **Preview** 배포 링크가 생성됩니다.

## 6. 운영(Production) 배포

기본 `vercel` 명령어는 '검토용(Preview)' 링크를 만듭니다. 실제 서비스 주소(Production)로 배포하려면 다음 명령어를 사용하세요.

```bash
vercel --prod
```

## 7. 주요 팁 (자주 묻는 질문)

### Q. 나중에 코드를 수정하면 어떻게 하나요?
수정 후 다시 `vercel` 또는 `vercel --prod` 명령어만 입력하면 됩니다. 이미 연결된 정보를 바탕으로 알아서 업데이트됩니다.

### Q. 다른 프로젝트에 연결하고 싶어요.
로컬 폴더 내의 숨겨진 `.vercel` 폴더를 삭제하거나, `vercel link` 명령어를 사용하여 다시 연결을 설정할 수 있습니다.

### Q. GitHub 연동이 무엇이 좋은가요?
매번 명령어를 입력할 필요 없이, `git push`만 하면 Vercel이 자동으로 변경 사항을 감지하여 서버에 올려줍니다. (추천 방식)
