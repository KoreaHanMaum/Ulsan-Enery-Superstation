# Ulsan Smart Energy Superstation Predictor

울산 **가상 기상 데이터** → 태양광 발전량 예측 → 에너지 슈퍼스테이션 충전 배분 대시보드 (과제용)

> API 키·기상청 연동 **없음**. 울산 5월 샘플값으로 동작합니다.

---

## Cursor에서 프로젝트 여는 방법

1. **Cursor** 실행
2. 왼쪽 상단 **File** → **Open Folder…** (또는 `Ctrl + K`, `Ctrl + O`)
3. 아래 폴더를 선택 후 **폴더 선택** 클릭:

   `C:\Users\USER\projects\ulsan-energy-superstation`

4. 왼쪽 **탐색기(Explorer)** 에 `backend`, `frontend`, `README.md` 가 보이면 성공

### 터미널 여는 방법

- 메뉴 **Terminal** → **New Terminal**  
- 또는 단축키 **Ctrl + `** (백틱)

터미널이 열리면 아래 **실행 방법**대로 명령을 입력합니다.

---

## 실행 방법 (2개 터미널)

### 터미널 1 — 백엔드

```powershell
cd C:\Users\USER\projects\ulsan-energy-superstation\backend
python -m venv venv
.\venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload --port 8000
```

### 터미널 2 — 프론트엔드

```powershell
cd C:\Users\USER\projects\ulsan-energy-superstation\frontend
npm install
npm run dev
```

### 브라우저

- 대시보드: http://localhost:3000  
- API 확인: http://localhost:8000/docs  

---

## 기능 요약

| 모듈 | 내용 |
|------|------|
| 기상 | 울산 5월 가상 데이터 (기온 18.4°C, 일사량 720 W/m² 등) |
| 발전 예측 | `P = A·η·G·(1 - 0.005(Tcell - 25))` |
| 슈퍼스테이션 | 초급속·무선·로봇 충전기 배분, UAM→버스→EV 우선순위 |
| 시각화 | 발전량·충전기·자급자족률 차트 |

---

## GitHub 올리기 (선택)

```powershell
cd C:\Users\USER\projects\ulsan-energy-superstation
git init
git add .
git commit -m "울산 에너지 슈퍼스테이션 예측 플랫폼"
```

GitHub에서 새 저장소 만든 뒤 `git remote add` / `git push` 하면 됩니다.

---

## 폴더 구조

```
ulsan-energy-superstation/
├── backend/          ← Python FastAPI
├── frontend/         ← Next.js 화면
├── docs/             ← 기획안
└── README.md         ← 이 파일
```

교육용 과제 프로젝트
