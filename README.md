<p align="center">
  <a href="https://www.uit.edu.vn/" title="Trường Đại học Công nghệ Thông tin" style="border: none;">
    <img src="https://i.imgur.com/WmMnSRt.png" alt="UIT Logo" width="200">
  </a>
</p>

<h1 align="center"><b>PHÁT TRIỂN ỨNG DỤNG WEB</b></h1>
<h2 align="center">Quản lý Công việc theo mô hình Trello</h2>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Web-blue?style=flat-square" alt="Platform">
  <img src="https://img.shields.io/badge/Frontend-React%20%2B%20Redux-61dafb?style=flat-square&logo=react" alt="React">
  <img src="https://img.shields.io/badge/Backend-Laravel%2012-red?style=flat-square&logo=laravel" alt="Laravel">
  <img src="https://img.shields.io/badge/Realtime-Socket.IO-black?style=flat-square&logo=socket.io" alt="Socket.IO">
  <img src="https://img.shields.io/badge/AI-Gemini-yellow?style=flat-square&logo=google" alt="Gemini">
  <img src="https://img.shields.io/badge/Database-MySQL%208-blue?style=flat-square&logo=mysql" alt="MySQL">
  <img src="https://img.shields.io/badge/Deploy-Docker%20Compose-2496ED?style=flat-square&logo=docker" alt="Docker">
</p>

<p align="center">
  <img src="trelloFE/src/assets/trello.svg" alt="Trello Clone Logo" width="80">
</p>

---

## Thông tin đồ án

| Mục | Nội dung |
|-----|----------|
| **Tên đồ án** | Quản lý Công việc theo mô hình Trello |
| **Môn học** | Phát triển ứng dụng web |
| **Trường** | Đại học Công nghệ Thông tin – ĐHQG TP.HCM |
| **Năm học** | 2025 – 2026 |

---

## Thành viên thực hiện

| Họ và tên | MSSV |
|-----------|------|
| Huỳnh Trần Anh Thư | 23521535 |
| Phạm Thái Sơn | 23521361 |
| Phạm Gia Quyền | 23521323 |
| Đặng Thiên Ân | 23520003 |

---

## Giao diện ứng dụng

<p align="center">
  <img src="trelloFE/src/assets/auth/login-register-bg.jpg" alt="Trello Clone App" width="700">
</p>

---

## Mục tiêu đồ án

Đồ án xây dựng ứng dụng quản lý công việc theo mô hình **Kanban Board** (tương tự Trello), với các mục tiêu chính:

- Xây dựng hệ thống **đăng ký / đăng nhập** với xác thực email và JWT token
- Quản lý **Board, Column, Card** với đầy đủ tính năng: nhãn, checklist, thành viên, ngày hạn, ảnh bìa
- Tích hợp **kéo thả (Drag & Drop)** để sắp xếp card và di chuyển giữa các cột
- Hỗ trợ **cộng tác thời gian thực** qua Socket.IO: thông báo lời mời tham gia board
- Tích hợp **AI Assistant** (Google Gemini) hỗ trợ người dùng sử dụng ứng dụng bằng tiếng Việt
- Quản lý **ảnh đại diện & tệp đính kèm** qua Cloudinary
- Triển khai toàn bộ hệ thống bằng **Docker Compose** với 5 services độc lập

---

## Công nghệ sử dụng

### Frontend

| Công nghệ | Phiên bản | Vai trò |
|-----------|-----------|---------|
| **React** | 18.3.1 | UI Framework (SPA) |
| **Redux Toolkit** | 2.0.1 | Quản lý state toàn cục |
| **Redux Persist** | 6.0.0 | Lưu state vào localStorage |
| **React Router DOM** | 6.21.3 | Điều hướng phía client |
| **Vite** | 5.4.10 | Build tool (SWC Fast Refresh) |
| **Material-UI (MUI)** | 5.13.0 | Thư viện UI components |
| **Axios** | 1.5.1 | HTTP client, interceptors |
| **Socket.IO Client** | 4.8.1 | Nhận thông báo thời gian thực |
| **@dnd-kit** | 6.0.8 | Drag & Drop (cards, columns) |
| **React Hook Form** | 7.49.3 | Quản lý form, validation |
| **@uiw/react-md-editor** | 4.0.3 | Markdown editor cho mô tả card |
| **Lodash** | 4.17.21 | Xử lý dữ liệu, deep clone |
| **React Toastify** | 11.0.2 | Thông báo toast |

**Redux State Slices:**
- `activeBoard` – Trạng thái board đang mở
- `user` – Thông tin người dùng đã đăng nhập
- `activeCard` – Card đang được chọn
- `notifications` – Danh sách thông báo

### Backend

| Công nghệ | Phiên bản | Vai trò |
|-----------|-----------|---------|
| **Laravel** | 12.0 | PHP Framework (RESTful API) |
| **PHP** | 8.2+ | Ngôn ngữ backend |
| **Laravel Sanctum** | 4.2 | Xác thực API token |
| **firebase/php-jwt** | 6.11 | Tạo và xác thực JWT |
| **Eloquent ORM** | – | Truy vấn cơ sở dữ liệu |
| **MySQL** | 8.0 | Cơ sở dữ liệu quan hệ |
| **Cloudinary PHP** | 3.1 | Upload và quản lý ảnh |
| **ramsey/uuid** | 4.9 | Sinh Hex ID kiểu MongoDB |
| **PHPUnit** | 11.5.3 | Unit testing |

**Các Controller chính:**
- `UserController` – Đăng ký, xác thực email, đăng nhập, đăng xuất, cập nhật hồ sơ
- `BoardController` – CRUD board
- `ColumnController` – CRUD cột, sắp xếp lại card
- `CardController` – CRUD card, bình luận, thành viên, nhãn, checklist
- `InvitationController` – Mời thành viên vào board

### Realtime & AI Service

| Công nghệ | Vai trò |
|-----------|---------|
| **Node.js + Express 5** | Server xử lý Socket.IO và AI |
| **Socket.IO** | Phát thông báo lời mời board thời gian thực |
| **Google Gemini 2.5 Flash** | AI Assistant trả lời câu hỏi về ứng dụng bằng tiếng Việt |

### Database Schema

| Bảng | Mô tả |
|------|-------|
| `users` | Tài khoản người dùng, xác thực email |
| `boards` | Board với `column_order_ids` (JSON) |
| `board_user` | Pivot – thành viên của board |
| `board_columns` | Cột với `card_order_ids` (JSON) |
| `cards` | Card: tiêu đề, mô tả, ảnh bìa, ngày hạn |
| `card_user` | Pivot – thành viên được gán vào card |
| `card_labels` | Nhãn trên card |
| `card_checklists` | Checklist trên card |
| `checklist_items` | Các mục trong checklist |
| `card_comments` | Bình luận / hoạt động trên card |
| `invitations` | Lời mời tham gia board |
| `personal_access_tokens` | Sanctum API tokens |

---

## Kiến trúc hệ thống

```
┌─────────────────────────────────────────────────────────┐
│                     CLIENT (Port 8080)                   │
│           React 18 + Redux Toolkit + MUI                 │
│         Drag & Drop (dnd-kit) | Socket.IO Client         │
└──────────────┬──────────────────────────┬───────────────┘
               │ REST API                 │ WebSocket
               ▼                          ▼
┌──────────────────────┐    ┌─────────────────────────────┐
│  Laravel 12 API      │    │  Node.js Socket Server      │
│  (Port 8000)         │    │  (Port 3000)                │
│  Sanctum Auth        │    │  Socket.IO + Gemini AI      │
│  Eloquent ORM        │    │  REST: POST /api/assistant  │
└──────────┬───────────┘    └─────────────────────────────┘
           │
           ▼
┌─────────────────────┐    ┌──────────────────────┐
│  MySQL 8 (Port 3307)│    │  Cloudinary          │
│  16 migrations      │    │  (Image Storage)     │
└─────────────────────┘    └──────────────────────┘
```

---

## Tính năng chính

- **Xác thực:** Đăng ký, đăng nhập, xác thực email, cập nhật hồ sơ & avatar
- **Board:** Tạo, xem, chỉnh sửa, xóa board; quản lý thành viên
- **Column:** Thêm, sửa, xóa cột; sắp xếp thứ tự
- **Card:** Tạo card với tiêu đề, mô tả (Markdown), ảnh bìa, ngày bắt đầu/hạn, nhãn, checklist, bình luận, thành viên
- **Drag & Drop:** Kéo thả card trong cột và giữa các cột
- **Thời gian thực:** Thông báo lời mời tham gia board qua Socket.IO
- **AI Assistant:** Chat với Gemini AI để được hỗ trợ sử dụng ứng dụng
- **Lưu trữ ảnh:** Upload ảnh bìa card & avatar qua Cloudinary

---

## Cài đặt & Chạy dự án

### Yêu cầu

- Docker & Docker Compose
- Node.js 18+
- PHP 8.2+ & Composer (nếu chạy thủ công)

### Chạy bằng Docker Compose

```bash
# Clone repository
git clone <repo-url>
cd Trello_Clone

# Tạo file môi trường
cp trelloPHP/.env.example trelloPHP/.env
cp trello_socket_server/.env.example trello_socket_server/.env
# Điền GEMINI_API_KEY vào trello_socket_server/.env

# Khởi động toàn bộ hệ thống
docker compose up -d --build
```

| Service | URL |
|---------|-----|
| Frontend | http://localhost:8080 |
| Laravel API | http://localhost:8000 |
| Socket Server | http://localhost:3000 |
| phpMyAdmin | http://localhost:9000 |

### Chạy thủ công (Development)

```bash
# Frontend
cd trelloFE
npm install
npm run dev

# Backend
cd trelloPHP
composer install
cp .env.example .env
php artisan key:generate
php artisan migrate
php artisan serve

# Socket + AI Server
cd trello_socket_server
npm install
node index.js
```

---

## Cấu trúc thư mục

```
Trello_Clone/
├── trelloFE/                  # React + Redux Frontend
│   ├── src/
│   │   ├── pages/             # Boards, BoardDetail, Auth pages
│   │   ├── components/        # AppBar, Modal, Card, Column...
│   │   ├── redux/             # Store, slices (activeBoard, user...)
│   │   ├── apis/              # Axios API calls
│   │   └── utils/             # Helpers, constants
│   └── package.json
├── trelloPHP/                 # Laravel 12 Backend API
│   ├── app/
│   │   ├── Http/Controllers/  # Board, Card, Column, User, Invitation
│   │   ├── Models/            # Eloquent models
│   │   └── Services/          # Business logic
│   ├── database/migrations/   # 16 migration files
│   └── routes/api.php         # API routes
├── trello_socket_server/      # Node.js Socket + AI
│   └── index.js               # Express + Socket.IO + Gemini
└── docker-compose.yml         # 5 services orchestration
```

---

## Liên hệ

Mọi thắc mắc vui lòng liên hệ nhóm thực hiện qua Issues của repository.

---

<p align="center">
  <b>© 2026 – UIT Web Development Project · Phát triển ứng dụng web · ĐHQG TP.HCM</b>
</p>
