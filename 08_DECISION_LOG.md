# 08_DECISION_LOG.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# Decision Log

## Purpose

Dokumen ini mencatat seluruh keputusan penting yang telah disepakati selama pengembangan LACT Project.

Decision Log menjadi referensi utama untuk memahami alasan di balik setiap perubahan arsitektur, teknologi, database, maupun workflow.

Keputusan yang telah berstatus **Approved** dianggap sebagai standar proyek dan wajib diikuti oleh seluruh developer maupun AI Assistant.

---

# Decision Rules

1. Setiap keputusan harus memiliki alasan yang jelas.
2. Keputusan tidak boleh bertentangan dengan Project Constitution.
3. Perubahan keputusan harus membuat entri baru, bukan menghapus riwayat lama.
4. Seluruh perubahan besar wajib dicatat pada dokumen ini.
5. Setiap keputusan harus memiliki status.

Status yang digunakan:

* Proposed
* Approved
* Deprecated
* Replaced

---

# Architecture Decisions

---

## DECISION-001

### Title

Backend Framework

### Decision

Menggunakan **Flask** sebagai framework backend utama.

### Reason

* Ringan.
* Sederhana.
* Cocok untuk arsitektur modular.
* Sesuai dengan kebutuhan proyek.

### Status

Approved

---

## DECISION-002

### Title

Frontend Technology

### Decision

Menggunakan HTML, CSS, dan Vanilla JavaScript.

### Reason

* Tidak bergantung pada framework frontend.
* Mudah dipelihara.
* Ringan.
* Mudah dipahami.

### Status

Approved

---

## DECISION-003

### Title

Database

### Decision

Menggunakan SQLite sebagai database utama selama tahap pengembangan.

### Reason

* Ringan.
* Mudah digunakan.
* Tidak memerlukan server database.
* Cocok untuk development.

### Status

Approved

---

## DECISION-004

### Title

Architecture Style

### Decision

Menggunakan Layered Architecture.

### Reason

Memisahkan tanggung jawab antara Frontend, API, Business Logic, dan Database.

### Status

Approved

---

# Data Management Decisions

---

## DECISION-005

### Title

Database as Source of Truth

### Decision

Seluruh data utama hanya berasal dari database.

### Reason

Menghindari inkonsistensi data antar modul.

### Status

Approved

---

## DECISION-006

### Title

Browser Cache

### Decision

Browser cache hanya digunakan sebagai penyimpanan sementara.

### Reason

Cache tidak boleh menjadi sumber data permanen.

### Status

Approved

---

## DECISION-007

### Title

Metadata Management

### Decision

Seluruh file upload wajib memiliki metadata pada database.

### Reason

Memastikan file dapat ditemukan, dipulihkan, dan dikelola secara konsisten.

### Status

Approved

---

# Development Decisions

---

## DECISION-008

### Title

Minimal Change Principle

### Decision

Perubahan dilakukan sekecil mungkin.

### Reason

Mengurangi risiko munculnya bug baru dan menjaga stabilitas modul lain.

### Status

Approved

---

## DECISION-009

### Title

Reuse Existing Components

### Decision

Menggunakan fungsi, helper, endpoint, atau komponen yang sudah ada sebelum membuat yang baru.

### Reason

Menghindari duplikasi logika dan mempermudah pemeliharaan.

### Status

Approved

---

## DECISION-010

### Title

No Large Refactor Without Approval

### Decision

Refactor besar hanya boleh dilakukan setelah mendapat persetujuan.

### Reason

Mengurangi risiko perubahan yang tidak terkontrol.

### Status

Approved

---

# Module Decisions

---

## DECISION-011

### Title

Calculation Engine

### Decision

Seluruh perhitungan teknis dilakukan oleh Calculation Engine di backend.

### Reason

Menjaga konsistensi hasil perhitungan dan menghindari perbedaan logika antara frontend dan backend.

### Status

Approved

---

## DECISION-012

### Title

Document Generator

### Decision

Document Generator hanya menggunakan data yang berasal dari database.

### Reason

Menjamin dokumen yang dihasilkan sesuai dengan kondisi data terbaru.

### Status

Approved

---

## DECISION-013

### Title

Evidence Management

### Decision

Seluruh metadata evidence dikelola melalui database.

### Reason

Memastikan upload, preview, gallery, dan document generator menggunakan data yang sama.

### Status

Approved

---

## DECISION-014

### Title

BOQ as Operational Reference

### Decision

BOQ menjadi referensi utama untuk data pekerjaan dan sinkronisasi dengan modul terkait.

### Reason

Mengurangi duplikasi data serta menjaga konsistensi antar modul.

### Status

Approved

---

# Documentation Decisions

---

## DECISION-015

### Title

Blueprint Priority

### Decision

Blueprint memiliki prioritas lebih tinggi dibanding implementasi kode.

### Reason

Blueprint merupakan Single Source of Truth bagi pengembangan proyek.

### Status

Approved

---

## DECISION-016

### Title

Living Documentation

### Decision

Task Board, Backlog, dan Decision Log diperbarui secara berkala mengikuti perkembangan proyek.

### Reason

Menjaga dokumentasi tetap relevan dengan kondisi aktual proyek.

### Status

Approved

---

# Decision Template

Setiap keputusan baru harus mengikuti format berikut:

```text
DECISION-XXX

Title:
...

Decision:
...

Reason:
...

Impact:
...

Status:
Proposed / Approved / Deprecated / Replaced

Date:
YYYY-MM-DD
```

---

# Change Policy

Keputusan yang telah berstatus **Approved** tidak boleh diubah secara langsung.

Apabila diperlukan perubahan:

1. Buat keputusan baru.
2. Referensikan keputusan sebelumnya.
3. Ubah status keputusan lama menjadi **Replaced** atau **Deprecated**.
4. Jelaskan alasan perubahan.

Riwayat keputusan harus tetap dipertahankan.

---

# Decision Review

Decision Log harus diperbarui apabila terjadi:

* Perubahan arsitektur.
* Perubahan teknologi.
* Perubahan struktur database.
* Perubahan workflow utama.
* Perubahan prinsip pengembangan.
* Perubahan kebijakan proyek.

---

# End of Document
