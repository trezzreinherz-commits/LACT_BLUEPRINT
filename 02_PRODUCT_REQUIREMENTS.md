# 02_PRODUCT_REQUIREMENTS.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# Product Requirements

## Purpose

Dokumen ini mendefinisikan seluruh kebutuhan fungsional dan non-fungsional LACT.

Seluruh implementasi sistem harus mengacu pada dokumen ini.

AI maupun developer tidak diperbolehkan menambahkan fitur yang tidak tercantum di dokumen ini tanpa persetujuan.

---

# Product Objective

LACT harus mampu menjadi platform terintegrasi untuk mengelola administrasi, dokumentasi, perhitungan teknis, dan penyusunan dokumen proyek FTTH.

---

# Functional Requirements

## FR-001 Project Management

Sistem harus mampu:

* Membuat Project
* Mengubah Project
* Menghapus Project
* Menampilkan daftar Project
* Menyimpan seluruh informasi dasar proyek

---

## FR-002 BOQ Management

Sistem harus mampu:

* Menyimpan item BOQ
* Menampilkan BOQ
* Mengubah nilai Actual
* Mengelola Quantity
* Mengelola Designator
* Menghitung progress berdasarkan data BOQ

---

## FR-003 Evidence Management

Sistem harus mampu:

* Upload foto
* Preview foto
* Menghapus foto
* Menampilkan gallery
* Menyimpan metadata foto
* Menghubungkan evidence dengan item pekerjaan

---

## FR-004 Grounding

Sistem harus mampu menyimpan dokumentasi pekerjaan Grounding beserta evidence yang terkait.

---

## FR-005 Galian

Sistem harus mampu menyimpan dokumentasi pekerjaan Galian beserta evidence yang terkait.

---

## FR-006 Dismantling

Sistem harus mampu menyimpan dokumentasi pekerjaan Dismantling beserta evidence yang terkait.

---

## FR-007 Cut Over

Sistem harus mampu menyimpan dokumentasi pekerjaan Cut Over beserta evidence yang terkait.

---

## FR-008 Regel

Sistem harus mampu menyimpan dokumentasi pekerjaan Regel beserta evidence yang terkait.

---

## FR-009 ODP Management

Sistem harus mampu:

* Membuat ODP
* Menghapus ODP manual
* Menyinkronkan ODP dari BOQ
* Mengelola Port ODP
* Menyimpan informasi ODP

---

## FR-010 OPM Management

Sistem harus mampu:

* Menyimpan data pengukuran OPM
* Mengelola Port
* Melakukan perhitungan redaman
* Menampilkan Summary
* Menyimpan hasil perhitungan

Seluruh perhitungan dilakukan oleh Calculation Engine.

---

## FR-011 Supporting Documents

Sistem harus mampu mengelola seluruh dokumen pendukung proyek.

---

## FR-012 Additional BA

Sistem harus mampu mengelola Berita Acara tambahan.

---

## FR-013 Signature Management

Sistem harus mampu menyimpan dan menggunakan tanda tangan pada dokumen.

---

## FR-014 Gallery

Sistem harus mampu menampilkan seluruh evidence berdasarkan data yang tersimpan.

---

## FR-015 Summary

Sistem harus mampu menghasilkan ringkasan data proyek secara otomatis berdasarkan database.

---

## FR-016 Document Generator

Sistem harus mampu menghasilkan dokumen proyek berdasarkan template dan data yang tersimpan di database.

Dokumen yang dihasilkan harus konsisten dengan data proyek.

---

# Non Functional Requirements

Sistem harus:

* Mudah digunakan.
* Stabil.
* Mudah dipelihara.
* Mudah dikembangkan.
* Mudah diuji.
* Memiliki struktur modular.
* Menggunakan database sebagai Source of Truth.
* Menghindari duplikasi logika bisnis.

---

# Technology Requirements

Backend

* Python
* Flask

Frontend

* HTML
* CSS
* JavaScript (Vanilla)

Database

* SQLite

Document Processing

* python-docx
* pandas
* openpyxl

---

# Data Requirements

Seluruh data utama harus disimpan pada database.

Cache browser hanya digunakan sebagai penyimpanan sementara dan tidak boleh menjadi sumber data permanen.

Seluruh file upload harus memiliki metadata yang tersimpan di database.

---

# Constraints

Sistem tidak boleh:

* Menyimpan data utama di Frontend.
* Menghitung logika bisnis di JavaScript.
* Mengakses database tanpa melalui Backend.
* Membuat duplikasi fungsi.
* Menambahkan dependency tanpa persetujuan.

---

# Out of Scope

Fitur berikut berada di luar ruang lingkup versi saat ini:

* Mobile Application
* Multi Company
* ERP
* Accounting
* Inventory
* AI Chat
* WhatsApp Integration
* Telegram Integration
* Voice Assistant
* Cloud Synchronization

Seluruh fitur tersebut harus dimasukkan ke Backlog.

---

# Success Criteria

Produk dianggap memenuhi requirement apabila:

* Seluruh modul berjalan sesuai fungsinya.
* Seluruh data berasal dari database.
* Tidak terjadi inkonsistensi data antar modul.
* Seluruh dokumen dapat dihasilkan secara otomatis.
* Seluruh fitur lulus pengujian sesuai Testing Standard.

---

# Requirement Change Policy

Setiap perubahan requirement wajib:

1. Disetujui terlebih dahulu.
2. Dicatat pada Decision Log.
3. Memperbarui dokumen terkait apabila diperlukan.

---

# End of Document
