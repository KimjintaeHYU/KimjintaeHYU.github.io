# NGS Sequencing 입문 — 30분 인터랙티브 수업

대학 학부생(입문~중상급 수준)을 위한 NGS(차세대 염기서열분석) 입문 수업 웹사이트입니다. 정적 HTML/CSS/JS로만 제작되어 빌드 과정 없이 GitHub Pages에서 바로 실행됩니다.

## 구성

| 파일 | 내용 | 소요 시간 |
|---|---|---|
| `index.html` | 코스 개요, 3개 모듈 허브 | — |
| `module1-genome-gene.html` | 유전체·유전자 일반생물학 개론 (DNA 구조, 중심원리) | ~10분 |
| `module2-sanger-ngs.html` | Sanger/Illumina/ONT/PacBio 원리 비교 + 인터랙티브 FASTQ→SAM/BAM 콘솔 | ~10분 |
| `module3-sfts-virus.html` | SFTS 바이러스 생활사·유전체 구조·중개의학적 의미, viremia 샘플 시퀀싱 실습 | ~10분 |

## 로컬에서 미리보기

별도 빌드 도구가 필요 없습니다. 폴더를 통째로 받아 `index.html`을 브라우저로 열거나, 다음처럼 간단한 정적 서버를 띄우면 됩니다.

```bash
python3 -m http.server 8000
# 브라우저에서 http://localhost:8000 접속
```

## GitHub Pages로 배포하기

1. 이 폴더 전체를 GitHub 저장소에 푸시합니다.

   ```bash
   git init
   git add .
   git commit -m "NGS course site"
   git branch -M main
   git remote add origin <저장소 URL>
   git push -u origin main
   ```

2. 저장소의 **Settings → Pages**로 이동합니다.
3. **Branch**를 `main`, 폴더를 `/ (root)`로 설정하고 저장합니다.
4. 잠시 후 `https://<사용자명>.github.io/<저장소명>/`에서 접속할 수 있습니다.

## 인터넷 연결 의존성

본문 텍스트, 다이어그램, 인터랙티브 실습(FASTQ 빌더, 정렬 시뮬레이터, SAM 뷰어, 퀴즈)은 모두 외부 의존성 없이 작동합니다. 다만 `assets/style.css` 상단에서 Google Fonts(JetBrains Mono, Inter)를 CDN으로 불러오므로, 완전히 오프라인인 환경에서는 시스템 폰트로 자동 대체되어 보입니다(기능에는 영향 없음).

## 강의 진행 제안 (30분)

- **0–10분** — Module 1. 이미 일반생물학을 학습한 대상이라면 5분으로 단축 가능
- **10–20분** — Module 2. 원리 설명 후 학생들이 직접 노트북/휴대폰으로 인터랙티브 콘솔을 조작하도록 안내
- **20–30분** — Module 3. SFTS 사례로 "왜 시퀀싱이 임상에 필요한가"라는 질문에 답하고 Q&A

## 라이선스 및 인용

본 자료에 포함된 SFTS 바이러스 유전체 구조 수치(L 6,368nt / M 3,378nt / S 1,744nt 등)는 공개된 학술 문헌(PLOS ONE, PMC 등에 게재된 SFTSV 전체유전체 분석 연구)을 참고해 교육용으로 단순화했습니다. 실제 연구나 임상 의사결정에는 원문 문헌과 최신 가이드라인을 확인하시기 바랍니다.
