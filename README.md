# Archilog

프로젝트에서 마주한 작은 고민과 기술적 선택을 기록하는 GitHub Pages 기반 기술 블로그입니다.

## 운영 흐름

```mermaid
flowchart LR
  A[Actions에서 초안 생성] --> B[Draft PR]
  B --> C[내용 작성과 검토]
  C --> D[Ready for review]
  D --> E[main 병합]
  E --> F[GitHub Pages 자동 배포]
```

### 새 글 작성

1. **Actions → Create Archilog Draft PR → Run workflow**를 선택합니다.
2. 영문 `slug`, 제목, 부제목, 카테고리를 입력합니다.
3. 자동 생성된 Draft PR의 `_posts/YYYY-MM-DD-slug.md`를 수정합니다.
4. 체크리스트를 완료하고 **Ready for review**로 전환합니다.
5. `main`에 병합하면 GitHub Pages가 자동 배포됩니다.

초안의 기본 문장 구조는 `_drafts/article-template.md`에서 관리합니다.

## 로컬 실행

```bash
bundle install
bundle exec jekyll serve
```

기본 주소는 `http://localhost:4000/archilog/`입니다.

## 최초 GitHub 설정

1. 저장소 **Settings → Pages → Build and deployment**에서 Source를 **GitHub Actions**로 선택합니다.
2. 저장소 **Settings → Actions → General → Workflow permissions**에서 **Read and write permissions**를 선택하고, **Allow GitHub Actions to create and approve pull requests**를 활성화합니다.
3. `main` 브랜치에 푸시된 `Deploy GitHub Pages` 작업이 성공하는지 확인합니다.

## 개인 도메인

`domain/README.md`에 DNS 및 GitHub Pages 연결 절차가 정리되어 있습니다. 도메인이 확정될 때까지는 `CNAME`을 생성하지 않습니다.

