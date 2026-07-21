# 10_AI_DEVELOPMENT_GUIDE.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# AI Development Guide

## Purpose

Dokumen ini merupakan panduan resmi bagi seluruh AI Assistant yang membantu pengembangan LACT Project.

AI wajib memahami blueprint proyek sebelum memberikan analisis, usulan perubahan, maupun implementasi kode.

Tujuan utama dokumen ini adalah menjaga konsistensi pengembangan serta menghindari perubahan yang tidak diperlukan.

---

# Primary Objective

Target utama AI adalah membantu pengembangan LACT sesuai blueprint proyek.

AI bukan pengambil keputusan.

AI bertugas membantu analisis, debugging, implementasi, dokumentasi, dan pengujian berdasarkan requirement yang telah disepakati.

---

# Required Reading Order

Sebelum memberikan solusi atau menulis kode, AI wajib memahami dokumen berikut secara berurutan:

1. PROJECT_CONSTITUTION
2. PRODUCT_VISION
3. PRODUCT_REQUIREMENTS
4. SYSTEM_ARCHITECTURE
5. DEVELOPMENT_RULES
6. DECISION_LOG
7. TESTING_STANDARD

Apabila terdapat konflik antar dokumen, urutan prioritas mengikuti PROJECT_CONSTITUTION.

---

# AI Core Principles

## Principle 1

Blueprint lebih tinggi daripada implementasi kode.

Apabila implementasi tidak sesuai blueprint, maka implementasi yang harus diperbaiki.

---

## Principle 2

Database adalah Source of Truth.

AI tidak boleh menganggap data pada frontend sebagai sumber data utama.

---

## Principle 3

Requirement lebih penting daripada asumsi.

Jika requirement belum jelas, AI harus meminta klarifikasi.

AI tidak boleh menebak kebutuhan pengguna.

---

## Principle 4

Minimal Change Principle.

Lakukan perubahan sekecil mungkin.

Perbaiki bagian yang bermasalah tanpa mengubah modul lain.

---

## Principle 5

Reuse Before Create.

Gunakan fungsi, endpoint, helper, maupun komponen yang sudah ada sebelum membuat yang baru.

---

# AI Workflow

Setiap permintaan pengembangan mengikuti alur berikut:

```text
Understand Requirement

↓

Read Related Module

↓

Analyze Existing Code

↓

Identify Root Cause

↓

Design Solution

↓

Implement Minimal Changes

↓

Testing

↓

Documentation
```

AI tidak boleh langsung melakukan implementasi tanpa memahami masalah terlebih dahulu.

---

# AI Coding Rules

AI wajib:

* Mengikuti arsitektur proyek.
* Menggunakan struktur proyek yang sudah ada.
* Menjaga kompatibilitas sistem.
* Menghasilkan kode yang sederhana.
* Menghindari duplikasi logika.
* Menjelaskan dampak perubahan apabila diminta.

AI tidak boleh:

* Mengubah modul yang tidak berkaitan.
* Membuat refactor besar tanpa instruksi.
* Mengganti teknologi proyek.
* Menambah dependency tanpa persetujuan.
* Mengubah struktur folder tanpa alasan yang kuat.

---

# Debugging Guidelines

Sebelum memperbaiki bug, AI wajib:

1. Memahami gejala bug.
2. Menemukan akar penyebab (Root Cause).
3. Memastikan area yang terdampak.
4. Menentukan solusi dengan perubahan minimal.
5. Menjelaskan risiko perubahan apabila diperlukan.

AI tidak boleh memperbaiki bug dengan cara trial and error tanpa analisis.

---

# Module Boundaries

AI harus menghormati batas tanggung jawab setiap modul.

Contoh:

* BOQ hanya mengelola data BOQ.
* Evidence hanya mengelola evidence.
* ODP hanya mengelola ODP.
* OPM hanya mengelola perhitungan OPM.
* Document Generator hanya menghasilkan dokumen.

Perubahan pada satu modul tidak boleh mengubah perilaku modul lain tanpa kebutuhan yang jelas.

---

# Database Rules

AI wajib:

* Menggunakan database sebagai sumber data.
* Menjaga integritas relasi.
* Memastikan Foreign Key tetap valid.
* Menghindari data duplikat.
* Menghindari orphan data.

Perubahan struktur database hanya dilakukan apabila benar-benar diperlukan.

---

# Frontend Rules

Frontend hanya bertanggung jawab untuk:

* Menampilkan data.
* Mengelola interaksi pengguna.
* Validasi sederhana.
* Mengirim request ke backend.

Frontend tidak boleh menjadi tempat logika bisnis maupun perhitungan teknis.

---

# Backend Rules

Backend bertanggung jawab untuk:

* Validasi bisnis.
* Perhitungan.
* Akses database.
* API.
* Document Generator.

Seluruh logika utama berada pada backend.

---

# Before Writing Code

AI harus mampu menjawab pertanyaan berikut:

* Apa requirement yang ingin dipenuhi?
* Modul apa yang terdampak?
* Fungsi apa yang sudah tersedia?
* Apakah perubahan ini benar-benar diperlukan?
* Apakah solusi ini dapat dilakukan dengan perubahan yang lebih kecil?

Jika salah satu belum dapat dijawab, AI sebaiknya melakukan analisis terlebih dahulu.

---

# Before Creating New Function

AI wajib memeriksa:

* Apakah fungsi serupa sudah ada?
* Apakah helper yang ada dapat digunakan?
* Apakah endpoint yang ada sudah mencukupi?
* Apakah logika dapat dipindahkan tanpa membuat duplikasi?

Apabila jawabannya "ya", gunakan komponen yang sudah ada.

---

# Before Database Changes

Sebelum mengubah struktur database, AI harus memastikan:

* Dampak terhadap data lama.
* Dampak terhadap relasi.
* Dampak terhadap API.
* Dampak terhadap Document Generator.
* Dampak terhadap modul lain.

Perubahan database harus menjadi pilihan terakhir.

---

# Before Finishing a Task

AI harus memastikan:

* Requirement telah terpenuhi.
* Tidak ada perubahan di luar ruang lingkup.
* Tidak ada fungsi duplikat.
* Database tetap konsisten.
* API tetap kompatibel.
* Modul lain tidak terdampak.
* Testing telah dilakukan.
* Dokumentasi diperbarui bila diperlukan.

---

# Preferred Response Format

Untuk permintaan implementasi, AI disarankan menggunakan struktur berikut:

1. Analisis Masalah
2. Root Cause
3. Dampak Perubahan
4. Rencana Implementasi
5. Implementasi
6. Hasil Pengujian
7. Risiko (jika ada)

Pendekatan ini memudahkan proses review sebelum kode diterapkan.

---

# AI Restrictions

AI tidak boleh:

* Menambah fitur di luar Product Requirements.
* Mengubah blueprint tanpa persetujuan.
* Menghapus fungsi hanya karena terlihat tidak digunakan.
* Membuat asumsi terhadap workflow bisnis.
* Mengubah banyak modul sekaligus untuk memperbaiki satu bug.

---

# Success Criteria

AI dianggap berhasil membantu proyek apabila:

* Solusi sesuai requirement.
* Perubahan minimal.
* Tidak menimbulkan bug baru.
* Arsitektur tetap konsisten.
* Database tetap menjadi Source of Truth.
* Dokumentasi tetap sinkron dengan implementasi.

---

# Philosophy

AI adalah alat bantu pengembangan, bukan pengambil keputusan.

Keputusan teknis tetap mengikuti blueprint, requirement, dan keputusan resmi proyek.

Tujuan utama AI adalah membantu menyelesaikan proyek secara konsisten, stabil, dan dapat dipelihara dalam jangka panjang.

---

# End of Document
