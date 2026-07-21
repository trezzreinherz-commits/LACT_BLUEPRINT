# 04_DEVELOPMENT_RULES.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# Development Rules

## Purpose

Dokumen ini berisi standar dan aturan pengembangan LACT Project.

Seluruh developer maupun AI Assistant wajib mengikuti aturan ini untuk menjaga konsistensi sistem, kualitas kode, dan integritas data.

---

# Rule 1 - Constitution First

Seluruh pengembangan wajib mengikuti **PROJECT_CONSTITUTION.md**.

Apabila terdapat perbedaan antara implementasi dan blueprint, maka blueprint yang menjadi acuan.

---

# Rule 2 - Requirement Driven Development

Setiap perubahan harus memiliki dasar yang jelas pada **PRODUCT_REQUIREMENTS.md**.

Tidak diperbolehkan membuat fitur berdasarkan asumsi atau opini.

---

# Rule 3 - Minimal Change Principle

Setiap perubahan harus dilakukan sekecil mungkin.

Perbaiki bagian yang bermasalah tanpa mengubah modul lain yang tidak berkaitan.

---

# Rule 4 - Database is the Source of Truth

Database adalah satu-satunya sumber data utama.

Dilarang menggunakan:

* JavaScript Cache
* Local Storage
* Session Storage
* Hidden Input

sebagai penyimpanan permanen data proyek.

---

# Rule 5 - Single Responsibility Principle

Setiap fungsi hanya memiliki satu tanggung jawab.

Setiap modul hanya memiliki satu tujuan utama.

Contoh:

* BOQ hanya mengelola data BOQ.
* OPM hanya mengelola data OPM.
* Evidence hanya mengelola evidence.

---

# Rule 6 - Separation of Layers

Frontend hanya bertanggung jawab terhadap:

* UI
* Event
* Validasi sederhana
* Menampilkan data

Backend bertanggung jawab terhadap:

* Validasi bisnis
* Perhitungan
* Database
* Proses utama

Frontend tidak boleh berisi logika bisnis.

---

# Rule 7 - Calculation Engine

Seluruh perhitungan teknis wajib dilakukan oleh Calculation Engine.

Contoh:

* OPM Loss
* Total Loss
* Summary
* Perhitungan teknis lainnya

JavaScript tidak boleh menghitung nilai bisnis maupun teknis.

---

# Rule 8 - API First

Seluruh komunikasi data dilakukan melalui REST API.

Frontend tidak boleh:

* mengakses database secara langsung
* membaca file database
* membuat logika sinkronisasi sendiri

---

# Rule 9 - Reuse Before Create

Sebelum membuat fungsi baru wajib memastikan:

* fungsi serupa belum tersedia
* helper yang ada belum dapat digunakan
* endpoint yang ada belum memenuhi kebutuhan

Hindari duplikasi logika.

---

# Rule 10 - No Unnecessary Refactor

Dilarang melakukan refactor besar apabila:

* hanya memperbaiki bug
* hanya menambah satu fitur kecil
* hanya mengubah tampilan

Refactor besar hanya dilakukan berdasarkan keputusan resmi.

---

# Rule 11 - Backward Compatibility

Perubahan baru tidak boleh merusak:

* Data lama
* Database lama
* API lama
* Dokumen lama

Kecuali telah disetujui melalui Decision Log.

---

# Rule 12 - Database Changes

Perubahan struktur database hanya diperbolehkan apabila:

* benar-benar diperlukan
* telah dianalisis dampaknya
* telah dicatat pada Decision Log

Migration harus dilakukan secara terkontrol.

---

# Rule 13 - File Upload Standard

Seluruh file upload wajib:

* divalidasi
* disimpan pada struktur folder uploads/
* memiliki metadata di database
* dapat dipulihkan kembali dari metadata

---

# Rule 14 - Error Handling

Seluruh proses wajib memiliki penanganan error yang jelas.

Tidak boleh:

* silent error
* swallow exception
* empty catch

Kesalahan harus dapat ditelusuri.

---

# Rule 15 - Logging

Seluruh proses penting wajib memiliki logging yang memadai.

Contoh:

* Upload
* Save
* Delete
* Calculation
* Generate Document
* API Error

Logging harus membantu proses debugging.

---

# Rule 16 - Testing

Fitur dianggap selesai apabila:

* berhasil dijalankan
* tidak merusak modul lain
* lulus pengujian
* memenuhi requirement

---

# Rule 17 - Documentation

Perubahan yang memengaruhi arsitektur, requirement, atau proses bisnis wajib memperbarui dokumentasi terkait.

Blueprint harus selalu sesuai dengan implementasi.

---

# Rule 18 - Decision Log

Keputusan berikut wajib dicatat pada **Decision Log**:

* perubahan arsitektur
* perubahan database
* perubahan requirement
* perubahan teknologi
* perubahan workflow utama

---

# Rule 19 - AI Development Rules

AI Assistant wajib:

* membaca blueprint sebelum coding
* mengikuti requirement
* menggunakan fungsi yang sudah ada
* menghindari pembuatan fungsi duplikat
* menjaga kompatibilitas sistem
* menjelaskan dampak perubahan apabila diminta

AI tidak boleh mengubah modul lain tanpa instruksi yang jelas.

---

# Rule 20 - Code Quality

Kode harus memenuhi prinsip berikut:

* Mudah dibaca.
* Mudah dipahami.
* Mudah diuji.
* Mudah dipelihara.
* Konsisten dengan struktur proyek.
* Tidak memiliki logika yang berulang.

---

# Development Workflow

Setiap pengembangan mengikuti urutan berikut:

```
Requirement

↓

Analysis

↓

Design

↓

Implementation

↓

Testing

↓

Documentation

↓

Review

↓

Merge
```

Tahapan tidak boleh dilewati.

---

# Code Review Checklist

Sebelum perubahan dianggap selesai, pastikan:

* Requirement telah terpenuhi.
* Tidak ada fungsi duplikat.
* Tidak ada perubahan di luar ruang lingkup.
* Database tetap konsisten.
* API tetap kompatibel.
* Tidak ada bug baru.
* Dokumentasi telah diperbarui bila diperlukan.

---

# End of Document
