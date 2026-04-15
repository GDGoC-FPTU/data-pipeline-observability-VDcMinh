# Experiment Report: Data Quality Impact on AI Agent

**Student ID:** Not provided
**Name:** Not provided
**Date:** 2026-04-15

---

## 1. Ket qua thi nghiem

Chay `agent_simulation.py` voi 2 bo du lieu va ghi lai ket qua:

| Scenario | Agent Response | Accuracy (1-10) | Notes |
|----------|----------------|-----------------|-------|
| Clean Data (`processed_data.csv`) | Agent: Based on my data, the best choice is Laptop at $1200.0. | 9 | Tra loi phu hop voi du lieu da duoc lam sach va van giu lai cac san pham electronics hop le. |
| Garbage Data (`garbage_data.csv`) | Agent: Based on my data, the best choice is Nuclear Reactor at $999999. | 2 | Ket qua sai lech do du lieu rac co outlier gia rat lon va khong co buoc validation truoc khi agent suy luan. |

---

## 2. Phan tich & nhan xet

### Tai sao Agent tra loi sai khi dung Garbage Data?

Agent tra loi sai voi garbage data vi bo du lieu nay chua nhieu loi chat luong cung luc. Dau tien, duplicate ID lam mat tinh duy nhat cua tung record, nen agent kho hieu record nao moi la doi tuong dang tin. Thu hai, truong `price` co sai kieu du lieu nhu `ten dollars`, cho thay schema khong on dinh va de gay loi neu co cac phep tinh hoac so sanh. Thu ba, record `Nuclear Reactor` co gia 999999 la mot outlier cuc doan; vi agent dang chon san pham electronics co gia cao nhat, outlier nay lap tuc chi phoi cau tra loi. Ngoai ra, null values va gia bang 0 cho thay bo du lieu thieu va ban. Khi dau vao khong duoc validate, agent van co the tra loi rat tu tin nhung sai ban chat.

(Viet nhan xet cua ban o day — it nhat 50 tu)

(Hay phan tich cac van de nhu Duplicate IDs, wrong data types, outliers, null values
va giai thich tai sao chung anh huong den ket qua cua Agent.)

---

## 3. Ket luan

**Quality Data > Quality Prompt?** Dong y. Prompt tot giup agent hieu cau hoi, nhung du lieu tot moi quyet dinh agent co co so de tra loi dung hay khong. Neu knowledge base chua record loi, outlier, hoac null values, thi prompt du ro rang van co the sinh ra cau tra loi sai.

