# BTH_014-Software-Testing
# 🧪 Pickle Module Stability & Correctness Test Suite  
# 🧪 Pickle 模块稳定性与正确性测试套件

## 📌 Project Objective | 项目目标

This project investigates the **determinism** and **platform consistency** of Python's `pickle` module.  
本项目旨在研究 Python `pickle` 模块的**确定性（determinism）**与**平台一致性（platform consistency）**。

> Does the same input always produce the same pickle file (i.e., the same hash)?  
> 相同的输入是否始终生成完全一致的 pickle 文件（即哈希值完全一致）？

---

## 🧰 Testing Approaches | 测试方法

The test suite includes both **white-box** and **black-box** methods.  
本测试套件涵盖了**白盒测试**与**黑盒测试**两种方法。

### ✅ White-box Testing 白盒测试（结构导向）

| Type | Comparison | 文件名 |
|------|------------|--------|
| Branch Coverage 分支覆盖 | Windows Python 3.12.4 vs 3.7.12 | `branch_python_hashes.txt` |
| Branch Coverage 分支覆盖 | Windows / Mac / Linux on 3.12.4 | `branch_hashes.txt` |
| Statement Coverage 语句覆盖 | Windows Python 3.12.4 vs 3.7.12 | `statement_python_hashes.txt` |
| Statement Coverage 语句覆盖 | Windows / Mac / Linux on 3.12.4 | `statement_hashes.txt` |
| Dataflow Coverage 数据流覆盖 | Windows Python 3.12.4 vs 3.7.12 | `dataflow_python_hashes.txt` |
| Dataflow Coverage 数据流覆盖 | Windows / Mac / Linux on 3.12.4 | `dataflow_hashes.txt` |

> 📁 所有测试代码位于 `whiteTest/` 目录下。

### ✅ Black-box Testing 黑盒测试（输入导向）

| Technique | Comparison | 文件名 |
|-----------|------------|--------|
| Boundary Value 边界值测试 | Windows Python 3.12.4 vs 3.7.12 | `result_win32_diffpy.txt` |
| Boundary Value 边界值测试 | Windows / Mac / Linux on 3.12.4 | `result_py3.12_multiOS.txt` |
| Equivalence Partition 等价类划分 | Windows Python 3.12.4 vs 3.7.12 | `blackbox_equiv_partition_diffpy.ipynb` |
| Equivalence Partition 等价类划分 | Windows / Mac / Linux on 3.12.4 | `blackbox_equiv_partition_diffos.ipynb` |

> 📁 所有测试代码与结果保存在 `blackbox/` 目录中。

---

## 🧾 Key Findings | 主要发现

- ✅ **Same Python Version, Different OS:**  
  Pickle files are hash-identical.  
  相同的 Python 版本，在不同操作系统下的结果一致（哈希值相同）。
  
- ❌ **Same OS, Different Python Versions:**  
  Pickle outputs differ due to version-specific implementations.  
  相同操作系统下，不同 Python 版本的输出结果不同（哈希值不同）。

---

## 🧪 Environment Matrix | 测试环境矩阵

| OS | Python 3.12.4 | Python 3.7.12 |
|----|---------------|---------------|
| Windows | ✅ | ✅ |
| macOS | ✅ | - |
| Linux | ✅ | - |

---

## 📊 Directory Overview | 文件目录说明

