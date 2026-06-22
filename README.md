# 🎥 Cloudinary Video Upload Platform

A full-stack video management platform built with **Next.js 16**, **Clerk Authentication**, **Cloudinary**, **Prisma ORM**, and **PostgreSQL**.

Users can securely upload videos, store metadata in a PostgreSQL database, preview uploaded videos, view compression statistics, and download videos directly from the dashboard.

---

# 🚀 Features

✅ User Authentication with Clerk

✅ Video Upload to Cloudinary

✅ PostgreSQL Database Integration

✅ Prisma ORM

✅ Video Gallery Dashboard

✅ Video Preview & Thumbnail Generation

✅ Video Compression Statistics

✅ Download Uploaded Videos

✅ Responsive UI

✅ TypeScript Support

---

# 🛠️ Tech Stack

## Frontend

* Next.js 16
* React
* TypeScript
* Tailwind CSS
* DaisyUI
* Axios
* Day.js

## Backend

* Next.js Route Handlers
* Prisma ORM
* PostgreSQL

## Cloud Storage

* Cloudinary

## Authentication

* Clerk

---

# 📸 Screenshots

## Home Dashboard

<p align="center">
  <img src="./screenshots/home.png" width="900">
</p>

## Video Upload Page

<p align="center">
  <img src="./screenshots/upload.png" width="900">
</p>

## Social Share Generator

<p align="center">
  <img src="./screenshots/social-share.png" width="900">
</p>

---

# 🏗️ Architecture Diagram

<p align="center">
  <img src="./screenshots/architecture.png" width="1000">
</p>

### Editable Draw.io File

The editable diagram is available in:

```text
/diagrams/Untitled Diagram.drawio
```

---

## Architecture Diagram

<p align="center">
  <img src="./screenshot/UntitledDiagram.drawio.png" width="1000">
</p>

---

# 📂 Project Structure

```text
app
│
├── (app)
│   ├── home
│   ├── social-share
│   ├── video-upload
│   │
│   └── api
│       ├── image-upload
│       ├── video-upload
│       └── videos
│
├── (auth)
│   ├── sign-in
│   └── sign-up
│
├── layout.tsx
│
components
│
├── VideoCard.tsx
│
prisma
│
├── schema.prisma
│
screenshots
│
├── architecture.png
├── home.png
├── upload.png
└── social-share.png
│
diagrams
│
└── Untitled Diagram.drawio
```

---

# 🗄️ Database Schema

```prisma
model Video {
  id String @id @default(cuid())

  title String
  description String

  PublicId String

  originalSize Int
  compresssize Int

  duration Float

  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
}
```

---

# 🔌 API Endpoints

## Upload Video

```http
POST /api/video-upload
```

Uploads video to Cloudinary and stores metadata in PostgreSQL.

### Request

```json
{
  "title": "Sample Video",
  "description": "Video Description",
  "file": "video.mp4"
}
```

---

## Fetch Videos

```http
GET /api/videos
```

Returns all uploaded videos.

### Response

```json
[
  {
    "id": "clxyz123",
    "title": "My Video",
    "description": "Demo video",
    "PublicId": "video-uploads/sample",
    "originalSize": 5000000,
    "compresssize": 3000000,
    "duration": 25.4
  }
]
```

---

# ⚙️ Environment Variables

Create a `.env.local` file:

```env
DATABASE_URL=

NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
CLERK_SECRET_KEY=

NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=
CLOUDINARY_API_KEY=
CLOUDINARY_API_SECRET=
```

---

# 🚀 Installation

Clone repository

```bash
git clone <your-repository-url>
```

Navigate into project

```bash
cd cloudinary-learning
```

Install dependencies

```bash
npm install
```

Generate Prisma Client

```bash
npx prisma generate
```

Run migrations

```bash
npx prisma migrate dev
```

Start development server

```bash
npm run dev
```

---

# 📈 Future Improvements

* Delete Uploaded Videos
* User-specific Video Library
* Search & Filtering
* Pagination
* Upload Progress Bar
* Direct Browser-to-Cloudinary Upload
* Analytics Dashboard
* Video Categories & Tags

---

# 👨‍💻 Author

**Shivam Yadav**

Built using Next.js, Prisma, PostgreSQL, Cloudinary, and Clerk Authentication.

⭐ If you found this project useful, consider giving it a star.
