# 06_TASK_BOARD.md

Version: 1.0.0

Status: Active

Project: LACT (Local Access Construction Tools)

---

# Task Board

## Purpose

Dokumen ini digunakan untuk mencatat seluruh pekerjaan yang sedang dikerjakan pada LACT Project.

Task Board hanya berisi pekerjaan aktif.

Ide baru dan pengembangan di luar sprint harus dimasukkan ke **BACKLOG.md**, bukan ke Task Board.

---

# Current Sprint

**Sprint 3 – System Stabilization & Module Completion**

Status:

**In Progress**

Target Utama:

* Menyelesaikan seluruh modul utama.
* Menghilangkan bug kritis.
* Menjaga konsistensi data.
* Mempersiapkan sistem menuju Production Release.

---

# Active Tasks

## TASK-001

### Module

BOQ

### Objective

Menyempurnakan seluruh proses BOQ sebagai sumber data utama.

### Status

In Progress

---

## TASK-002

### Module

Evidence

### Objective

Menyempurnakan upload, preview, gallery, dan sinkronisasi evidence dengan database.

### Status

In Progress

---

## TASK-003

### Module

Grounding

### Objective

Menyempurnakan workflow upload evidence dan penyimpanan data Grounding.

### Status

In Progress

---

## TASK-004

### Module

ODP

### Objective

Menyempurnakan sinkronisasi ODP dari BOQ, pengelolaan tab, dan port.

### Status

In Progress

---

## TASK-005

### Module

OPM

### Objective

Menyempurnakan Calculation Engine, Summary, dan integrasi Port.

### Status

In Progress

---

## TASK-006

### Module

Document Generator

### Objective

Menyempurnakan proses pembuatan dokumen proyek berdasarkan database.

### Status

Planned

---

## TASK-007

### Module

Testing

### Objective

Melakukan pengujian seluruh modul utama sebelum Production Release.

### Status

Planned

---

# Module Status

| Module              | Status      |
| ------------------- | ----------- |
| Project Management  | Stable      |
| BOQ                 | In Progress |
| Evidence            | In Progress |
| Grounding           | In Progress |
| Galian              | In Progress |
| Dismantling         | In Progress |
| Cut Over            | In Progress |
| Regel               | In Progress |
| ODP                 | In Progress |
| OPM                 | In Progress |
| Supporting Document | Stable      |
| Additional BA       | Stable      |
| Signature           | Stable      |
| Gallery             | In Progress |
| Summary             | In Progress |
| Document Generator  | Planned     |

---

# Current Priorities

## Priority 1

Menyelesaikan bug yang memengaruhi integritas data.

---

## Priority 2

Menyelesaikan sinkronisasi antar modul menggunakan database sebagai Source of Truth.

---

## Priority 3

Menyelesaikan seluruh workflow upload evidence.

---

## Priority 4

Menyempurnakan Calculation Engine.

---

## Priority 5

Menyelesaikan Document Generator.

---

# Task Workflow

Seluruh task mengikuti alur berikut:

```text
Backlog

↓

Analysis

↓

Development

↓

Testing

↓

Review

↓

Completed
```

Task tidak boleh langsung berpindah ke **Completed** tanpa melalui tahap **Testing**.

---

# Task Status Definition

## Backlog

Belum menjadi pekerjaan aktif.

---

## Planned

Sudah disetujui tetapi belum dikerjakan.

---

## In Progress

Sedang dalam proses pengembangan.

---

## Testing

Sedang diuji.

---

## Review

Menunggu verifikasi hasil implementasi.

---

## Completed

Sudah selesai dan memenuhi seluruh requirement.

---

## Blocked

Tidak dapat dilanjutkan karena terdapat kendala yang harus diselesaikan terlebih dahulu.

---

# Completion Checklist

Sebuah task dianggap selesai apabila:

* Requirement telah terpenuhi.
* Tidak menimbulkan bug baru.
* Tidak mengubah modul lain tanpa alasan.
* Database tetap konsisten.
* API tetap berjalan normal.
* Pengujian berhasil.
* Dokumentasi diperbarui apabila diperlukan.

---

# Task Rules

1. Setiap task hanya memiliki satu tujuan utama.
2. Satu task hanya berfokus pada satu modul.
3. Bug lebih diprioritaskan dibanding fitur baru.
4. Fitur baru tidak boleh dikerjakan apabila masih terdapat bug kritis.
5. Perubahan di luar ruang lingkup task tidak diperbolehkan.
6. Seluruh perubahan harus mengikuti Development Rules.
7. Ide baru harus dipindahkan ke Backlog.

---

# Project Progress

| Area                 | Progress |
| -------------------- | -------: |
| Blueprint            |     100% |
| Core System          |      95% |
| BOQ                  |      90% |
| Evidence             |      80% |
| ODP                  |      90% |
| OPM                  |      90% |
| Document Generator   |      70% |
| Testing              |      60% |
| Production Readiness |      75% |

> **Catatan:** Persentase di atas merupakan indikator kematangan modul dan dapat diperbarui seiring perkembangan proyek.

---

# End of Document
