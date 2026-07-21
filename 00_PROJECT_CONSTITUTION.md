# 00_PROJECT_CONSTITUTION.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# PROJECT CONSTITUTION

## Purpose

Dokumen ini merupakan **Single Source of Truth (SSOT)** untuk seluruh pengembangan LACT Project.

Seluruh developer, AI Assistant, maupun kontributor proyek wajib menjadikan dokumen ini sebagai acuan utama sebelum melakukan perubahan apa pun.

Apabila terjadi perbedaan antara implementasi kode dengan blueprint proyek, maka **blueprint yang menjadi acuan** dan implementasi harus disesuaikan.

---

# Vision

Membangun platform terpadu untuk mendukung proses administrasi, monitoring, perhitungan teknis, dokumentasi, dan pelaporan proyek FTTH secara terintegrasi dalam satu aplikasi.

Platform harus mampu mengurangi pekerjaan manual, menjaga konsistensi data, serta mempercepat proses penyusunan dokumen proyek.

---

# Mission

* Menjadikan database sebagai sumber kebenaran utama (Source of Truth).
* Menghilangkan duplikasi proses dan data.
* Menyediakan alur kerja yang sederhana dan konsisten.
* Memastikan seluruh modul dapat berkembang tanpa saling memengaruhi.
* Menjaga kualitas kode agar mudah dipelihara dalam jangka panjang.

---

# Golden Rules

Blueprint > Code

Database > Cache

Requirement > Assumption

Testing > Opinion

Simplicity > Complexity

Consistency > Speed

Minimal Change > Large Refactor

Finish > Perfect

---

# Project Scope

LACT berfokus pada pengelolaan proyek FTTH dari proses administrasi hingga penyusunan dokumen akhir.

Modul utama meliputi:

* Project Management
* BOQ Management
* Evidence Management
* Grounding
* Galian
* Dismantling
* Cut Over
* Regel
* ODP Management
* OPM Management
* Supporting Documents
* Additional BA
* Signature Management
* Gallery
* Summary
* Document Generator

---

# Out of Scope

Berikut bukan bagian dari ruang lingkup versi saat ini dan harus masuk Backlog:

* Mobile Application
* Multi Company
* ERP
* Accounting
* Inventory Management
* AI Chat Assistant
* WhatsApp Integration
* Telegram Integration
* Voice Assistant
* Cloud Synchronization
* Real-time Collaboration

---

# Core Principles

## Database First

Seluruh data proyek harus berasal dari database.

Cache hanya digunakan sebagai media sementara untuk meningkatkan pengalaman pengguna dan tidak boleh menjadi sumber data utama.

---

## Single Source of Truth

Setiap data hanya memiliki satu sumber utama.

Tidak boleh terdapat dua mekanisme berbeda yang menyimpan informasi yang sama.

---

## Modular Architecture

Setiap modul memiliki tanggung jawab yang jelas.

Perubahan pada satu modul tidak boleh menyebabkan perubahan pada modul lain tanpa alasan yang jelas.

---

## Reusability

Fungsi yang sudah ada harus digunakan kembali apabila masih memenuhi kebutuhan.

Pembuatan fungsi baru hanya diperbolehkan apabila memang belum tersedia solusi yang sesuai.

---

## Minimal Changes

Perubahan harus dilakukan sekecil mungkin.

Hindari refactor besar apabila tujuan dapat dicapai dengan perubahan yang lebih sederhana.

---

# Development Rules

1. Tidak menambahkan fitur di luar sprint yang sedang berjalan.
2. Tidak mengubah struktur database tanpa persetujuan.
3. Tidak mengubah arsitektur sistem tanpa keputusan resmi.
4. Seluruh perubahan harus mengikuti Product Requirements.
5. Seluruh keputusan penting harus dicatat pada Decision Log.
6. Seluruh ide baru harus masuk Backlog.
7. Seluruh fitur wajib memiliki skenario pengujian.
8. Tidak boleh membuat duplikasi fungsi maupun logika bisnis.
9. Semua perubahan harus menjaga kompatibilitas dengan data proyek yang sudah ada.

---

# Definition of Done

Sebuah fitur dianggap selesai apabila:

* Requirement telah terpenuhi.
* Tidak merusak modul lain.
* Lulus pengujian.
* Menggunakan database sebagai Source of Truth.
* Dokumentasi diperbarui apabila diperlukan.
* Tidak meninggalkan kode sementara (temporary code).

---

# Priority Order

Apabila terjadi konflik antar dokumen, urutan prioritas adalah:

1. PROJECT_CONSTITUTION
2. PRODUCT_VISION
3. PRODUCT_REQUIREMENTS
4. SYSTEM_ARCHITECTURE
5. DEVELOPMENT_RULES
6. DECISION_LOG
7. TESTING_STANDARD

---

# Philosophy

LACT bukan sekadar aplikasi administrasi proyek.

LACT merupakan platform yang mengintegrasikan seluruh proses pekerjaan FTTH ke dalam satu sistem yang konsisten, terstruktur, mudah dipelihara, dan dapat dikembangkan secara berkelanjutan.

---

End of Document
