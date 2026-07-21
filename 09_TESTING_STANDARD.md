# 09_TESTING_STANDARD.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# Testing Standard

## Purpose

Dokumen ini menetapkan standar pengujian untuk seluruh modul pada LACT Project.

Seluruh fitur dianggap selesai hanya apabila telah memenuhi requirement, lulus pengujian, dan tidak menyebabkan regresi pada modul lain.

Testing merupakan bagian wajib dari setiap proses pengembangan.

---

# Testing Principles

Seluruh pengujian mengikuti prinsip berikut:

* Requirement Based Testing
* Database First Validation
* Regression Prevention
* End-to-End Workflow Validation
* Repeatable Test
* No Assumption

---

# Testing Levels

## Level 1 - Unit Testing

Tujuan:

Memastikan satu fungsi bekerja sesuai tanggung jawabnya.

Contoh:

* Helper Function
* Calculation Function
* Utility Function
* Validation Function

---

## Level 2 - Module Testing

Tujuan:

Memastikan seluruh fungsi dalam satu modul berjalan dengan benar.

Contoh:

* BOQ
* Evidence
* ODP
* OPM
* Grounding

---

## Level 3 - Integration Testing

Tujuan:

Memastikan komunikasi antar modul berjalan dengan baik.

Contoh:

BOQ

↓

ODP

↓

OPM

↓

Summary

---

## Level 4 - End-to-End Testing

Tujuan:

Memastikan seluruh workflow pengguna berjalan tanpa kendala.

Contoh:

Project

↓

BOQ

↓

Evidence

↓

Document Generator

↓

Download

---

# General Testing Rules

Seluruh pengujian wajib memastikan:

* Tidak terjadi error.
* Tidak terjadi data corruption.
* Tidak ada data yang hilang.
* Database tetap konsisten.
* Modul lain tidak terpengaruh.

---

# Module Testing Checklist

## Project Management

Wajib diuji:

* Create Project
* Update Project
* Delete Project
* Load Project
* Project Detail

---

## BOQ

Wajib diuji:

* Import BOQ
* Save BOQ
* Edit Actual
* Quantity
* Designator
* Progress Calculation

---

## Evidence

Wajib diuji:

* Upload
* Preview
* Delete
* Gallery
* Metadata
* Reload Data

---

## Grounding

Wajib diuji:

* Save Data
* Upload Evidence
* Reload
* Summary

---

## Galian

Wajib diuji:

* Save
* Upload
* Reload

---

## Dismantling

Wajib diuji:

* Save
* Upload
* Reload

---

## Cut Over

Wajib diuji:

* Save
* Upload
* Reload

---

## Regel

Wajib diuji:

* Save
* Upload
* Reload

---

## ODP

Wajib diuji:

* Create Tab
* Delete Manual Tab
* Auto Generate
* Save
* Load
* Port Management

---

## OPM

Wajib diuji:

* Save
* Load
* Calculation Engine
* Summary
* Port Data

---

## Supporting Documents

Wajib diuji:

* Upload
* Preview
* Delete

---

## Additional BA

Wajib diuji:

* Create
* Save
* Load

---

## Signature

Wajib diuji:

* Upload
* Save
* Generate Document

---

## Gallery

Wajib diuji:

* Preview
* Reload
* Delete
* Image Display

---

## Document Generator

Wajib diuji:

* Generate DOCX
* Generate PDF
* Data Mapping
* Image Mapping
* Template Replacement

---

# Database Validation

Setiap perubahan data wajib memastikan:

* Data tersimpan pada tabel yang benar.
* Foreign Key tetap valid.
* Tidak ada duplicate record.
* Tidak ada orphan data.
* Seluruh relasi tetap konsisten.

Database merupakan sumber validasi utama.

---

# API Testing

Seluruh endpoint harus diuji:

* Request Valid
* Request Invalid
* Error Handling
* Response Format
* HTTP Status Code

API tidak boleh menghasilkan error yang tidak ditangani.

---

# Upload Testing

Setiap proses upload wajib diuji:

* Validasi file
* Penyimpanan file
* Penyimpanan metadata
* Preview
* Reload
* Delete

---

# Calculation Testing

Seluruh Calculation Engine wajib diuji:

* Input Valid
* Input Invalid
* Nilai Batas
* Pembulatan
* Konsistensi Hasil

Frontend tidak boleh menjadi acuan hasil perhitungan.

---

# Regression Testing

Setelah setiap perubahan, minimal lakukan pengujian terhadap:

* Project
* BOQ
* Evidence
* ODP
* OPM
* Document Generator

Bug baru tidak boleh muncul akibat perbaikan sebelumnya.

---

# Performance Testing

Periksa bahwa:

* Halaman dapat dimuat dengan baik.
* Query database tetap efisien.
* Upload tidak mengalami penurunan performa signifikan.
* Document Generator tetap berjalan dengan stabil.

---

# Bug Classification

## Critical

* Kehilangan data
* Database rusak
* Dokumen gagal dibuat
* Perhitungan salah
* Sistem tidak dapat digunakan

Harus diperbaiki sebelum melanjutkan pekerjaan lain.

---

## Major

* Fitur utama gagal berjalan.
* API gagal.
* Upload gagal.
* Summary salah.

Harus menjadi prioritas tinggi.

---

## Minor

* Tampilan tidak sesuai.
* Pesan tidak tepat.
* Kesalahan kecil yang tidak memengaruhi fungsi utama.

Dapat dijadwalkan pada sprint berikutnya.

---

# Definition of Done

Sebuah fitur dianggap selesai apabila:

* Requirement terpenuhi.
* Lulus seluruh pengujian yang relevan.
* Tidak menimbulkan regression.
* Database tetap konsisten.
* Dokumentasi diperbarui apabila diperlukan.

---

# Testing Report

Setiap pengujian sebaiknya mencatat:

* Module
* Feature
* Test Scenario
* Expected Result
* Actual Result
* Status (Pass / Fail)
* Tester
* Date

---

# End of Document
