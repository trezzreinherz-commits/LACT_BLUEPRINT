# 03_SYSTEM_ARCHITECTURE.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# System Architecture

## Purpose

Dokumen ini menjelaskan arsitektur sistem LACT serta hubungan antar komponen.

Seluruh pengembangan harus mengikuti arsitektur ini agar sistem tetap konsisten, mudah dipelihara, dan mudah dikembangkan.

---

# Architecture Overview

LACT menggunakan arsitektur berlapis (Layered Architecture).

```
Browser
      │
      ▼
HTML Template
(project_detail.html)
      │
      ▼
JavaScript (UI Layer)
      │
      ▼
REST API
      │
      ▼
Routes (Controller)
      │
      ▼
Business Logic / Engine
      │
      ▼
Models
      │
      ▼
SQLite Database
      │
      ▼
Uploads
```

Setiap layer memiliki tanggung jawab yang berbeda dan tidak boleh mengambil alih tanggung jawab layer lain.

---

# Technology Stack

## Backend

* Python
* Flask

---

## Frontend

* HTML
* CSS
* JavaScript (Vanilla)

---

## Database

* SQLite

---

## Document Processing

* python-docx
* openpyxl
* pandas

---

## Image Processing

* Pillow
* OpenCV (apabila diperlukan)

---

# System Principles

## Layer Separation

Frontend hanya menangani tampilan.

Backend hanya menangani logika bisnis.

Database hanya menyimpan data.

---

## Database First

Database merupakan satu-satunya Source of Truth.

Frontend tidak boleh menjadi sumber data utama.

---

## API Driven

Seluruh komunikasi antara Frontend dan Backend dilakukan melalui REST API.

Frontend tidak boleh mengakses database secara langsung.

---

## Modular Architecture

Setiap modul bekerja secara independen.

Perubahan pada satu modul tidak boleh mengubah perilaku modul lain.

---

# Main Components

## 1. Project Management

Mengelola informasi utama proyek.

Contoh:

* Data Project
* Informasi Mitra
* Informasi Lokasi
* Status Project

---

## 2. BOQ Module

Mengelola seluruh data BOQ.

Tanggung jawab:

* Menyimpan item BOQ
* Actual Quantity
* Designator
* Sinkronisasi dengan modul lain

---

## 3. Evidence Module

Mengelola seluruh dokumentasi foto.

Tanggung jawab:

* Upload Foto
* Preview
* Gallery
* Metadata Foto

---

## 4. ODP Module

Mengelola seluruh data ODP.

Tanggung jawab:

* ODP Tabs
* Port Management
* Relasi dengan OPM

---

## 5. OPM Module

Mengelola seluruh perhitungan redaman.

Tanggung jawab:

* Input Pengukuran
* Calculation Engine
* Summary
* Port Information

Perhitungan hanya dilakukan pada Calculation Engine.

Frontend tidak boleh menghitung nilai teknis.

---

## 6. Supporting Document Module

Mengelola seluruh dokumen pendukung proyek.

---

## 7. Additional BA Module

Mengelola Berita Acara tambahan.

---

## 8. Signature Module

Mengelola tanda tangan digital pada dokumen.

---

## 9. Document Generator

Menghasilkan dokumen proyek secara otomatis berdasarkan data database.

Seluruh dokumen harus mengambil data langsung dari database.

---

# Data Flow

```
User

↓

Frontend

↓

REST API

↓

Routes

↓

Business Logic

↓

Database

↓

Business Logic

↓

JSON Response

↓

Frontend

↓

User
```

Seluruh validasi data dilakukan pada Backend.

---

# Upload Flow

```
User

↓

Upload File

↓

Validation

↓

Save File

↓

Save Metadata

↓

Database

↓

Preview
```

Metadata file wajib disimpan di database.

Lokasi file mengikuti struktur folder uploads/.

---

# Calculation Flow

```
User Input

↓

Validation

↓

Calculation Engine

↓

Database

↓

Summary

↓

Frontend
```

Perhitungan hanya boleh dilakukan oleh Calculation Engine.

Frontend hanya menampilkan hasil.

---

# Document Generation Flow

```
Database

↓

Document Generator

↓

Word

↓

PDF (Optional)

↓

Download
```

Generator tidak boleh menggunakan cache frontend sebagai sumber data.

---

# Source of Truth

| Jenis Data         | Source of Truth     |
| ------------------ | ------------------- |
| Project            | Database            |
| BOQ                | Database            |
| Evidence           | Database            |
| ODP                | Database            |
| OPM                | Database            |
| Summary            | Database            |
| Generated Document | Database + Template |

Cache browser hanya digunakan untuk meningkatkan pengalaman pengguna dan tidak boleh menjadi sumber data permanen.

---

# Design Principles

1. Single Responsibility.
2. Database First.
3. Reusable Components.
4. Minimal Coupling.
5. High Cohesion.
6. API Driven.
7. Modular Design.
8. Minimal Changes.
9. Backward Compatibility.

---

# Architecture Constraints

Seluruh pengembangan wajib mengikuti aturan berikut:

* Tidak mengakses database langsung dari Frontend.
* Tidak melakukan perhitungan teknis di JavaScript.
* Tidak membuat logika bisnis di Template HTML.
* Tidak menduplikasi fungsi yang sudah ada.
* Tidak membuat API baru apabila endpoint yang ada masih dapat digunakan.
* Tidak mengubah struktur database tanpa keputusan resmi.
* Tidak melakukan refactor besar tanpa persetujuan.

---

# End of Document
