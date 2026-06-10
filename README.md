[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=24112893&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** Conglac01
**Name:** Conglac01

---

## Mo ta

Bai lab nay xay dung mot ETL pipeline don gian cho du lieu san pham. Pipeline doc du lieu tu `raw_data.json`, validate de loai bo record co `price <= 0` hoac `category` rong, transform du lieu bang cach chuan hoa category sang Title Case, tinh `discounted_price = price * 0.9`, them cot `processed_at`, sau do ghi ket qua ra `processed_data.csv`.

Ngoai phan ETL, bai lam co stress test voi mot agent simulation de so sanh tac dong cua du lieu sach va du lieu rac. Ket qua cho thay du lieu co outlier, null value, duplicate ID va sai kieu du lieu co the lam agent dua ra cau tra loi sai.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas pytest
```

### Chay ETL Pipeline
```bash
python solution.py
```

### Chay Agent Simulation (Stress Test)
```bash
python generate_garbage.py
python agent_simulation.py
```

### Chay test local
```bash
pytest -q
```

---

## Cau truc thu muc

```
├── solution.py              # ETL Pipeline script
├── processed_data.csv       # Output cua pipeline
├── experiment_report.md     # Bao cao thi nghiem
└── README.md                # File nay
```

---

## Ket qua

Pipeline doc 5 records tu `raw_data.json`, giu lai 3 records hop le va loai 2 records loi. File `processed_data.csv` duoc tao voi cac cot `id`, `product`, `price`, `category`, `discounted_price`, va `processed_at`.

Trong stress test, agent dung clean data chon `Laptop` la san pham electronics co gia cao nhat. Khi dung garbage data, agent chon `Nuclear Reactor` gia 999999 vi outlier trong tap du lieu rac lam sai ket qua.
