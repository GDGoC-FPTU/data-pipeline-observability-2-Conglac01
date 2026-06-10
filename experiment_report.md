# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** Conglac01
**Name:** Conglac01
**Date:** 2026-06-10

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200. | 9 | Du lieu da duoc validate nen chi con record co price hop le va category day du. Agent tim dung san pham electronics co gia cao nhat trong tap du lieu sach. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Tap du lieu bi poison boi duplicate ID, sai kieu du lieu, null value va outlier cuc lon. Agent van tra loi duoc nhung ket qua khong dang tin cay. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai voi Garbage Data vi logic cua agent phu thuoc truc tiep vao du lieu dau vao. Khi co outlier nhu Nuclear Reactor gia 999999 trong category electronics, ham se chon record nay lam san pham tot nhat vi no chi so sanh theo price cao nhat. Duplicate ID lam mat tinh nhat quan cua khoa dinh danh, wrong data type nhu "ten dollars" co the gay loi khi xu ly so, con null value lam thieu thong tin quan trong de filter. Vi vay prompt co tot den dau nhung context bi sai thi agent van dua ra cau tra loi sai hoac gay hieu nham.

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y.

Du lieu chat luong cao quan trong hon viec chi viet prompt that hay. Prompt chi huong dan cach tra loi, con du lieu quyet dinh noi dung ma agent dua vao de suy luan. Pipeline ETL can validate, transform va log ro rang de giam rui ro dua du lieu rac vao ung dung AI.
