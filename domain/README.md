# 개인 도메인 연결

도메인이 결정되면 다음 순서로 연결합니다.

1. `domain/CNAME.example`의 내용을 실제 도메인으로 바꾸고 저장소 루트에 `CNAME` 파일로 복사합니다.
2. 서브도메인 사용 시 DNS에 `CNAME` 레코드를 추가합니다.
   - 이름: `blog` 또는 원하는 서브도메인
   - 대상: `daxuan0101.github.io`
3. GitHub 저장소의 **Settings → Pages → Custom domain**에 같은 도메인을 입력합니다.
4. DNS 검증이 끝난 후 **Enforce HTTPS**를 활성화합니다.
5. `_config.yml`을 아래처럼 변경합니다.

```yml
url: "https://blog.example.com"
baseurl: ""
```

루트 도메인(`example.com`)을 사용한다면 GitHub Pages 공식 IP에 대한 `A`/`AAAA` 레코드가 필요합니다. IP는 변경 가능성이 있으므로 연결 시점의 GitHub 공식 문서를 기준으로 등록합니다.

> 실제 도메인이 정해지기 전에는 `CNAME` 파일을 만들지 않습니다. 예시 파일만으로는 Pages 배포에 영향을 주지 않습니다.

