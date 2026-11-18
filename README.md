# 세대이음 사회적협동조합 웹사이트 (sdieum.com)

정적 사이트입니다. 이 저장소에 변경 사항을 푸시하면 Netlify가 자동으로 sdieum.com에 배포합니다.

## 구성
- `index.html`: 메인 페이지
- `recruit.html`: 채용 안내 페이지(`/recruit`). 공고 목록은 `data/jobs.json`에서 불러옵니다.
- `data/jobs.json`: 채용 공고 데이터. **공고를 추가·수정·마감할 때는 이 파일만 고칩니다.**
- `assets/logo.png`: 로고

## 채용 공고 항목
```json
{
  "id": "2026-12-care-teacher",
  "title": "공고 제목",
  "category": "돌봄센터 | 어린이집 | 어르신 돌봄 | 매직우드 강사 | 크루즈 교육 | 사무국",
  "pinned": false,
  "status": "open",
  "posted": "2026-11-18",
  "deadline": "2026-12-05",
  "employmentType": "정규직 / 계약직 / 시간제",
  "location": "근무지",
  "workHours": "근무시간",
  "pay": "급여",
  "headcount": "모집인원",
  "summary": "공고 소개 문단",
  "duties": ["담당 업무"],
  "requirements": ["자격 요건"],
  "preferred": ["우대 사항"],
  "benefits": ["근무 조건·복리후생"],
  "apply": {
    "method": "이메일 접수",
    "email": "sdieum@naver.com",
    "phone": "010-5331-7401",
    "link": "",
    "documents": ["이력서", "자기소개서"]
  },
  "note": "기타 안내"
}
```
- `deadline`이 지나면 자동으로 '마감'으로 표시됩니다. 상시 채용은 `"deadline": "상시"`로 씁니다.
- 일찍 마감하려면 `"status": "closed"`로 바꿉니다.
- 특정 공고 링크는 `https://sdieum.com/recruit#<id>` 형식입니다.
