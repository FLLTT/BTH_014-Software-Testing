# 🧪 Pickle Module Stability & Correctness Test Suite

## 📌 Project Objective

This project investigates the **determinism** and **platform consistency** of Python's `pickle` module.

> Does the same input always produce the same pickle file (i.e., the same SHA256 hash)?

---

## 🧰 Testing Approaches

The test suite includes both **white-box** and **black-box** techniques.

### ✅ White-box Testing

| Type | Comparison | Result File |
|------|------------|-------------|
| Branch Coverage | Windows Python 3.12.4 vs 3.7.12 | `branch_python_hashes.txt` |
| Branch Coverage | Windows / Mac / Linux on Python 3.12.4 | `branch_hashes.txt` |
| Statement Coverage | Windows Python 3.12.4 vs 3.7.12 | `statement_python_hashes.txt` |
| Statement Coverage | Windows / Mac / Linux on Python 3.12.4 | `statement_hashes.txt` |
| Dataflow Coverage | Windows Python 3.12.4 vs 3.7.12 | `dataflow_python_hashes.txt` |
| Dataflow Coverage | Windows / Mac / Linux on Python 3.12.4 | `dataflow_hashes.txt` |

> 📁 All scripts and result files are located in the `whiteTest/` directory.

### ✅ Black-box Testing

| Technique | Comparison | Result File |
|-----------|------------|-------------|
| Boundary Value Testing | Windows Python 3.12.4 vs 3.7.12 | `result_win32_diffpy.txt` |
| Boundary Value Testing | Windows / Mac / Linux on Python 3.12.4 | `result_py3.12_multiOS.txt` |
| Equivalence Partitioning | Windows Python 3.12.4 vs 3.7.12 | `blackbox_equiv_partition_diffpy.ipynb` |
| Equivalence Partitioning | Windows / Mac / Linux on Python 3.12.4 | `blackbox_equiv_partition_diffos.ipynb` |

> 📁 All related files are located in the `blackbox/` directory.

---

## 🧾 Key Findings

- ✅ **Same Python version, different OS:**  
  Pickle outputs are identical in hash — platform-independent.

- ❌ **Same OS, different Python versions:**  
  Pickle outputs differ — version-dependent behavior observed.

---

## 🧪 Environment Matrix

| OS      | Python 3.12.4 | Python 3.7.12 |
|---------|----------------|---------------|
| Windows | ✅              | ✅             |
| macOS   | ✅              | ❌             |
| Linux   | ✅              | ❌             |

---

## 📊 Directory Overview
