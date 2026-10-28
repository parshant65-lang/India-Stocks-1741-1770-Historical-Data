# India-Stocks-1741-1770-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 1741 to 1770)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-1741-1770-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (1741 to 1770)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 1741 | `NDL` | Nandan Denim Limited | `NDL.NS` |
| 1742 | `NDLVENTURE` | NDL Ventures Limited | `NDLVENTURE.NS` |
| 1743 | `NDRAUTO` | Ndr Auto Components Limited | `NDRAUTO.NS` |
| 1744 | `NDTV` | New Delhi Television Limited | `NDTV.NS` |
| 1745 | `NEAGI` | Neelamalai Agro Industries Limited | `NEAGI.NS` |
| 1746 | `NECCLTD` | North Eastern Carrying Corporation Limited | `NECCLTD.NS` |
| 1747 | `NECLIFE` | Nectar Lifesciences Limited | `NECLIFE.NS` |
| 1748 | `NELCAST` | Nelcast Limited | `NELCAST.NS` |
| 1749 | `NELCO` | NELCO Limited | `NELCO.NS` |
| 1750 | `NEOGEN` | Neogen Chemicals Limited | `NEOGEN.NS` |
| 1751 | `NEPHROPLUS` | Nephrocare Health Services Limited | `NEPHROPLUS.NS` |
| 1752 | `NESCO` | Nesco Limited | `NESCO.NS` |
| 1753 | `NETWORK18` | Network18 Media & Investments Limited | `NETWORK18.NS` |
| 1754 | `NEUEON` | Neueon Corporation Limited | `NEUEON.NS` |
| 1755 | `NEWGEN` | Newgen Software Technologies Limited | `NEWGEN.NS` |
| 1756 | `NEXTMEDIA` | Next Mediaworks Limited | `NEXTMEDIA.NS` |
| 1757 | `NFL` | National Fertilizers Limited | `NFL.NS` |
| 1758 | `NGIL` | Nakoda Group of Industries Limited | `NGIL.NS` |
| 1759 | `NGLFINE` | NGL Fine-Chem Limited | `NGLFINE.NS` |
| 1760 | `NIBE` | NIBE Limited | `NIBE.NS` |
| 1761 | `NIBL` | NRB Industrial Bearings Limited | `NIBL.NS` |
| 1762 | `NICCOPAR` | Nicco Parks & Resorts Limited | `NICCOPAR.NS` |
| 1763 | `NIITLTD` | NIIT Limited | `NIITLTD.NS` |
| 1764 | `NIITMTS` | NIIT Learning Systems Limited | `NIITMTS.NS` |
| 1765 | `NILAINFRA` | Nila Infrastructures Limited | `NILAINFRA.NS` |
| 1766 | `NILASPACES` | Nila Spaces Limited | `NILASPACES.NS` |
| 1767 | `NILE` | Nile Limited | `NILE.NS` |
| 1768 | `NILKAMAL` | Nilkamal Limited | `NILKAMAL.NS` |
| 1769 | `NIMBSPROJ` | Nimbus Projects Limited | `NIMBSPROJ.NS` |
| 1770 | `NINSYS` | NINtec Systems Limited | `NINSYS.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream NDL 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-1741-1770-Historical-Data/main/NDL/1m/2026/10/NDL_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
