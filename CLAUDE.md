# sdieum.com 운영 안내 (Claude용)

세대이음 사회적협동조합 홈페이지. 정적 사이트이며 `main`에 푸시하면 Netlify가 sdieum.com에 자동 배포한다(빌드 없음).

## 채용 공고 올리기
- 공고는 `data/jobs.json`의 `jobs` 배열에만 추가·수정한다. `recruit.html`(/recruit)이 이 파일을 읽어 표시한다.
- 필드 형식은 README.md와 기존 공고(`2026-anseong-director`)를 따른다. `id`는 `연도-지역-직무` 형태의 영문 소문자.
- 홍보 포스터 이미지는 `assets/jobs/<id>.webp|png|jpg`로 저장하고 `image`에 `/assets/jobs/...` 경로를 넣는다.
- `deadline`은 `YYYY-MM-DD`면 날짜가 지나면 자동 마감. "채용 시 마감", "상시" 같은 문구면 자동 마감되지 않으니 마감 요청 시 `"status": "closed"`로 바꾼다.
- 포스터·원문에 없는 내용(인원, 급여 등)은 지어내지 말고 비워 두거나 사용자에게 확인한다. 연락처가 대표번호(010-5331-7401)와 다르면 확인을 요청한다.
- 수정 후 `python3 -m json.tool data/jobs.json`로 JSON 검증 → 커밋 → `git push origin main`.
- 게시 후 공고 직접 링크: `https://sdieum.com/recruit#<id>`

## 주의
- `index.html`은 이미지가 base64로 들어 있는 1MB+ 파일이다. 통째로 읽지 말고 필요한 부분만 grep/sed로 수정한다.
