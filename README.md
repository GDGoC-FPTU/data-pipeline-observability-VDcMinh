[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23574310&assignment_repo_type=AssignmentRepo)
# Day 10 Lab: Data Pipeline & Data Observability

**Student Email:** vuducminh474@gmail.com   
**Name:** Vũ Đức Minh

---

## Mo ta

Lab nay xay dung mot ETL pipeline don gian de doc du lieu JSON, loai bo record loi, chuan hoa category, tinh gia giam 10%, va xuat ket qua ra CSV. Ngoai pipeline, bai lam con thu nghiem agent voi du lieu sach va du lieu rac de quan sat tac dong cua data quality len cau tra loi.

---

## Cach chay (How to Run)

### Prerequisites
```bash
pip install pandas
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

Pipeline doc 5 records tu `raw_data.json`, giu lai 3 records hop le va loai 2 records khong dat yeu cau (`price <= 0` hoac `category` rong). File `processed_data.csv` duoc tao thanh cong voi cac cot `discounted_price` va `processed_at`. Khi chay stress test, agent tra loi hop ly voi clean data, nhung bi dan huong sai boi record outlier trong `garbage_data.csv`.
