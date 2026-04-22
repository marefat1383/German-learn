# German Learning App

برنامه یادگیری زبان آلمانی با رابط کاربری فارسی

## ساختار پروژه

```
VS/
├── backend/          # Python / FastAPI
│   ├── app/
│   │   ├── api/      # routes: vocab, dialogue, grammar, progress
│   │   ├── core/     # config, database
│   │   ├── models/   # SQLAlchemy models
│   │   ├── schemas/  # Pydantic schemas
│   │   └── services/ # ai_provider, srs, adaptive
│   └── requirements.txt
├── frontend/         # React + TypeScript + Vite
│   └── src/
│       ├── pages/    # LevelSelect, VocabModule, ...
│       ├── components/
│       ├── services/ # API client
│       ├── store/    # Zustand state
│       └── styles/
└── docs/
    └── exploration.md  # سند اکتشافی معماری
```

## راهاندازی بکاند

```bash
cd backend
python -m venv venv
venv\Scripts\activate          # Windows
pip install -r requirements.txt
copy .env.example .env         # سپس API key را وارد کنید
uvicorn app.main:app --reload
```

API docs: http://localhost:8000/docs

## راهاندازی فرانتاند

```bash
cd frontend
npm install
npm run dev
```

App: http://localhost:3000

## تصمیمات باز

- انتخاب ارائهدهنده AI (OpenAI / Google / Anthropic) — تنها `.env` تغییر میکند
- چارچوب رومیزی (Electron / Tauri) — فعلاً وب
- تعداد دقیق واژگان هر سطح — در `exploration.md` مستند شده

## وضعیت پیادهسازی

- [x] معماری پایه بکاند (FastAPI + SQLite)
- [x] سیستم SRS (SM-2)
- [x] موتور سختی تطبیقی
- [x] لایه AI مستقل از ارائهدهنده
- [x] API واژگان، محاوره، دستور زبان، پیشرفت
- [x] ماندگاری جلسه (pause/resume)
- [x] هماهنگسازی اختیاری مبتنیبر حساب
- [x] فرانتاند پایه (انتخاب سطح + ماژول واژگان)
- [ ] ماژول محاوره (UI)
- [ ] ماژول دستور زبان (UI)
- [ ] داشبورد معلم
- [ ] پشتیبانی آفلاین کامل
