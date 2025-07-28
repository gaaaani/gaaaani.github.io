---
layout: post
title: "GitHub Pages + Jekyll 블로그 만들기"
subtitle: "개발 블로그 구축기"
author: Gaaaani
categories: [Projects]
tags: [GitHubPages, Jekyll, YAT]
banner:
  image: /assets/images/blog-setup-banner.jpg
  height: "50vh"
sidebar: []
---

개발 공부와 프로젝트 기록을 남기기 위한 기록용으로  
**GitHub Pages + Jekyll + YAT 테마** 조합의 블로그를 구축했다.  

---

## 💡 사용한 기술

- GitHub Pages  
- Jekyll  
- YAT 테마

---

## 🧭 구축 순서

### 1. GitHub 저장소 생성

- `닉네임.github.io` 형식으로 새 저장소 생성  
- 웹에서 접속 시 자동으로 GitHub Pages로 인식됨

<div style="display: flex; gap: 16px;">
  <div style="flex: 1; text-align: center;">
    <img src="/assets/images/setup/repo.jpeg" alt="레포 생성" style="height: 200px; object-fit: cover; border-radius: 8px;">
    <p>레포 생성</p>
  </div>
  <div style="flex: 1; text-align: center;">
    <img src="/assets/images/setup/repo1.jpeg" alt="io 확인" style="height: 200px; object-fit: cover; border-radius: 8px;">
    <p>io 확인</p>
  </div>
</div>


---

### 2. 개발 환경 설정

#### 💎 Ruby 설치

- [RubyInstaller](https://rubyinstaller.org/downloads/) 에서 최신 버전 설치

#### 📦 Jekyll 설치

```bash
gem install jekyll
```

#### 📦 Bundler 설치

```bash
gem install bundler
```

- Bundler는 Ruby의 의존성 관리 도구로, gem을 버전별로 관리할 수 있게 해줌

---

### 3. Jekyll 테마 설정

- YAT 테마를 클론하거나 압축 해제 후 프로젝트 루트에 파일 복사  
- `_config.yml`에서 `title`, `author`, `email`, `url` 등 정보 수정  
- 테마가 잘 적용되는지 확인

```bash
bundle install
bundle exec jekyll serve
```

- `http://localhost:4000` 접속 → 로컬 서버 확인 가능  
- `_config.yml` 수정 시에는 반드시 서버 재시작 필요

---

### ❗ 발생했던 이슈와 해결 방법

#### Jekyll 파일 위치
- Jekyll은 빌드 시 아래와 같은 구조를 찾고 자동으로 실행하는데, 루트 디렉토리에 없다면 제대로 실행이 안될 수도 있음
    ```
    .
    ├── _config.yml        ✅ 전역 설정 파일
    ├── _posts/            ✅ 글 모음 폴더
    ├── _layouts/          ✅ 레이아웃 정의
    ├── index.html         ✅ 메인 페이지
    └── 기타 리소스
    ```

#### 🔸 `bigdecimal` LoadError
- 오류 메시지:
  ```
  cannot load such file -- bigdecimal
  ```
- 해결 방법:
```bash
gem install bigdecimal
```

#### 🔸 `logger` warning (Ruby 3.5 대비)
- 경고 메시지:
  ```
  logger was loaded from the standard library, but will no longer be part of the default gems
  ```
- 해결 방법: `Gemfile`에 아래 내용 추가
```ruby
gem "logger"
```

#### 🔸 `wdm` 설치 실패 (Windows)
- 에러 메시지:
  ```
  An error occurred while installing wdm
  ```
- 해결 방법: `Gemfile`에서 해당 라인을 주석 처리
```ruby
# gem "wdm", "~> 0.1.1" if Gem.win_platform?
```

> `wdm`은 선택 사항이므로 없어도 서버 실행에는 영향 없음.

~~(이 밖에도 gpt 친구와 함께 하면 설정에는 큰 어려움이 없을 것이다.)~~

--- 

### 4. 내용 커스터마이즈

#### 📌 header 설정

- `_config.yml`에 `header_pages` 옵션으로 상단 메뉴 구성

```yaml
header_pages:
  - index.html
  - about.md
  - projects.md
  - categories.html
  - tags.html
```

#### 📌 기본 배너 설정

- `_config.yml`의 `defaults` 설정으로 홈 배너 및 문구 설정

```yaml
defaults:
  - scope:
      path: ""
      type: "home"
    values:
      heading: "환영합니다!"
      subheading: "Gaaaani의 개발 블로그입니다 ✨"
      banner: "default"
```

---

### 5. 첫 포스트 작성

- `_posts/` 폴더 안에 아래 형식으로 Markdown 파일 작성
- 아래 예시처럼 글 위에서 형식을 지정해줘야 함!

```markdown
---
layout: post
title: "블로그 첫 글"
subtitle: "Jekyll + YAT 테마 적용 완료!"
author: Gaaaani
categories: [Blog, Dev]
tags: [Jekyll, YAT, GitHubPages]
banner:
  image: /assets/images/banner.jpg
  height: "50vh"
  opacity: 0.8
  background: "rgba(0,0,0,0.4)"
  heading_style: "font-size: 3em; font-weight: bold;"
  subheading_style: "color: #ffcc00;"
top: 1
sidebar: []
---

새로운 포스트! 🎉  

- YAT 테마 적용 완료  
- GitHub Pages 배포 완료  
- 이제부터 개발 공부 기록을 차근차근 올릴 예정!
```

---

### ✅ github.io와 친해지기

Markdown 기반으로 블로그를 구성하니 **글 작성과 관리가 간편**하고,  
노션과도 비슷한 느낌이라 접근 하기 좋고, github를 활용하면서 **멋진 경험**을 할 수 있는 장점이 있는 것 같다.    
특히 커스터마이징이 자유로워 나만의 블로그로 꾸미기 좋다. 😉  
~~(앞으로 활용하면서 알게되겠지만..)~~    
이제부터는 꾸준한 기술 정리, 프로젝트 아카이빙을 이 블로그를 통해 이어갈 계획이다. ✨  


---

## 🔗 참고 자료

- 위키독스 GitHub 블로그 만들기: [https://wikidocs.net/278085](https://wikidocs.net/278085)  
- YAT 테마: [https://github.com/jeffreytse/jekyll-theme-yat](https://github.com/jeffreytse/jekyll-theme-yat)
