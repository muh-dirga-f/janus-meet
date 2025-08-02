# janus-meet

📡 Real-time video meeting app built with Janus Gateway (SFU), WebRTC, React, and Node.js.
Modular monorepo architecture with Git submodules for `backend` and `frontend`.

---

## 📁 Struktur Repositori

```

janus-meet/
├── apps/
│   ├── frontend/     # React + Vite + Zustand + janus.js
│   └── backend/      # Node.js + Express + Prisma + Socket.IO
├── docker-compose.yml
├── .gitmodules
├── package.json      # Optional: monorepo management (yarn/pnpm workspaces)
└── README.md

````

---

## 🚀 Getting Started

### 1. Clone repository beserta submodule

```bash
git clone --recurse-submodules https://github.com/muh-dirga-f/janus-meet.git
cd janus-meet
````

> Jika kamu lupa `--recurse-submodules`, jalankan:
>
> ```bash
> git submodule update --init --recursive
> ```

---

### 2. Install dependencies

Kamu bisa pakai `yarn` (monorepo friendly), atau langsung install di masing-masing app:

```bash
# Jika pakai Yarn workspace:
yarn install

# Atau manual:
cd apps/backend && yarn install
cd ../frontend && yarn install
```

---

### 3. Menjalankan development server

```bash
# Jalankan secara paralel (pakai concurrently dari root)
yarn dev
```

Atau jalankan satu per satu:

```bash
# Backend (port 3000)
cd apps/backend
yarn dev

# Frontend (port 5173)
cd apps/frontend
yarn dev
```

---

### 4. Update submodule (jika ada perubahan baru)

```bash
git submodule update --remote
```

---

## 🐳 Docker Dev (opsional)

Jalankan semua layanan (backend, frontend, DB, Janus Gateway) sekaligus:

```bash
docker compose up --build
```

---

## 📦 Teknologi Utama

| Layer     | Teknologi                                     |
| --------- | --------------------------------------------- |
| Frontend  | React 18, Vite, TypeScript, Zustand, janus.js |
| Backend   | Node.js 18, Express, Prisma, Socket.IO        |
| Signaling | Janus Gateway (via Admin API + WebSocket)     |
| Database  | PostgreSQL                                    |
| Realtime  | WebRTC (via Janus SFU), Chat, ScreenShare     |

---

## 📄 Kontrak API

Tersimpan dan disinkronkan melalui `openapi.yaml` di backend.
Pastikan tidak ada perubahan sepihak — backend & frontend **harus commit bersama.**

---

## 📌 Catatan Tim

* Semua perubahan pada API, WebSocket, dan struktur data harus sinkron di kedua submodule.
* Gunakan branch dan PR yang jelas: `feature/frontend/xxx` atau `fix/backend/yyy`.

---

## 🧩 Repositori Terkait

| Komponen | Repository                                                             |
| -------- | ---------------------------------------------------------------------- |
| Backend  | [janus-meet-backend](https://github.com/muh-dirga-f/janus-meet-backend)   |
| Frontend | [janus-meet-frontend](https://github.com/muh-dirga-f/janus-meet-frontend) |
