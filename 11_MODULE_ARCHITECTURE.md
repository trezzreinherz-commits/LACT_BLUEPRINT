# 11_MODULE_ARCHITECTURE.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# Module Architecture

## Purpose

Dokumen ini menjelaskan struktur setiap modul pada LACT Project.

Setiap modul memiliki tanggung jawab yang jelas, batas perubahan yang tegas, serta hubungan dengan modul lain.

Seluruh developer maupun AI wajib memahami dokumen ini sebelum melakukan perubahan pada suatu modul.

---

# Architecture Principles

Setiap modul wajib memenuhi prinsip berikut:

* Single Responsibility
* Database First
* API Driven
* Modular
* Reusable
* Low Coupling
* High Cohesion

---

# Overall Module Structure

```text
Project

├── Project Management
│
├── BOQ
│
├── Evidence
│
├── Grounding
│
├── Galian
│
├── Dismantling
│
├── Cut Over
│
├── Regel
│
├── ODP
│
├── OPM
│
├── Supporting Documents
│
├── Additional BA
│
├── Signature
│
├── Summary
│
└── Document Generator
```

---

# Standard Module Structure

Setiap modul idealnya terdiri dari:

```text
Frontend (HTML + JS)

↓

REST API

↓

Route

↓

Business Logic

↓

Model

↓

Database
```

Seluruh modul mengikuti pola yang sama.

---

# Module Definition

## 1. Project Management

### Responsibility

Mengelola data utama proyek.

### Database

* projects

### Related Modules

* Seluruh modul

### Source of Truth

Database

---

## 2. BOQ Module

### Responsibility

Mengelola seluruh data BOQ.

### Database

* boq_items

### Related Modules

* Evidence
* ODP
* Summary
* Document Generator

### Rules

BOQ merupakan referensi utama pekerjaan.

---

## 3. Evidence Module

### Responsibility

Mengelola evidence pekerjaan.

### Database

* evidences
* evidence_items

### Related Modules

* BOQ
* Gallery
* Document Generator

### Rules

Seluruh metadata evidence wajib berada pada database.

---

## 4. Grounding Module

### Responsibility

Mengelola pekerjaan Grounding.

### Related Modules

Evidence

Summary

Document Generator

---

## 5. Galian Module

### Responsibility

Mengelola pekerjaan Galian.

---

## 6. Dismantling Module

### Responsibility

Mengelola pekerjaan Dismantling.

---

## 7. Cut Over Module

### Responsibility

Mengelola pekerjaan Cut Over.

---

## 8. Regel Module

### Responsibility

Mengelola pekerjaan Regel.

---

## 9. ODP Module

### Responsibility

Mengelola seluruh ODP.

### Database

* odp_tabs

### Related Modules

* BOQ
* OPM

### Rules

ODP tidak melakukan perhitungan.

ODP hanya mengelola data.

---

## 10. OPM Module

### Responsibility

Mengelola seluruh data pengukuran.

### Database

* opm_data
* opm_ports

### Related Modules

* ODP
* Summary

### Rules

Perhitungan hanya dilakukan Calculation Engine.

Frontend tidak menghitung.

---

## 11. Supporting Document Module

Mengelola seluruh dokumen pendukung.

---

## 12. Additional BA Module

Mengelola Berita Acara tambahan.

---

## 13. Signature Module

Mengelola tanda tangan.

---

## 14. Summary Module

### Responsibility

Menampilkan ringkasan data proyek.

### Rules

Summary hanya membaca data.

Summary tidak menyimpan data.

---

## 15. Document Generator

### Responsibility

Menghasilkan dokumen proyek.

### Rules

Generator membaca data dari database.

Tidak membaca cache frontend.

---

# Module Communication

Komunikasi antar modul dilakukan melalui:

```text
Frontend

↓

API

↓

Route

↓

Database

↓

Response
```

Modul tidak boleh memanggil JavaScript modul lain secara langsung.

---

# Dependency Rules

Modul hanya boleh bergantung pada:

Database

↓

Shared Helper

↓

Shared Component

Tidak boleh membuat dependency silang yang tidak diperlukan.

---

# Module Boundary

Setiap modul hanya boleh:

✔ membaca data yang diperlukan

✔ mengubah data miliknya

✔ memanggil API yang sesuai

Tidak boleh:

✘ mengubah database modul lain

✘ memanggil fungsi internal modul lain

✘ mengubah workflow modul lain

---

# Module Lifecycle

```text
User

↓

Frontend

↓

API

↓

Business Logic

↓

Database

↓

Response

↓

Frontend
```

Seluruh modul menggunakan lifecycle yang sama.

---

# Future Expansion

Apabila modul baru ditambahkan:

* harus memiliki Responsibility
* harus memiliki Database Mapping
* harus memiliki API
* harus memiliki Testing
* harus memiliki Documentation

Sebelum implementasi dilakukan.

---

# End of Document
