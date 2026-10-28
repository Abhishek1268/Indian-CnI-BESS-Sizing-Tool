# Indian C&I BESS Sizing Tool

> A Python tool that helps energy companies figure out whether 
> installing a battery at an industrial site makes financial sense — 
> and exactly what contract structure makes it work.

---

## The Problem This Solves

Industrial factories in India pay very high electricity bills.
A big part of that bill comes not from how much electricity 
they use — but from how much they use at peak moments.

For example:
- A factory peaks at 500 kW for just 15 minutes in May
- The electricity company bills them for that 500 kW all month
- If they exceed their contract limit, they pay a heavy penalty on top

A battery system (BESS) can fix this by:
- Absorbing that peak so the bill is calculated on a lower number
- Preventing the factory from ever crossing its contract limit
- Charging at night when electricity is cheap and 
  discharging during expensive hours

This tool calculates whether installing that battery is worth it.

---

## The Business Model We Tested

We tested a model called **BESS-as-a-Service (BaaS)**:
The energy company installs and owns the battery
The factory pays nothing upfront
Both parties share the savings the battery generates


Think of it like solar rooftop leasing — the factory gets 
the benefit without the investment risk.

---

## The Customer We Used As a Case Study

| Detail | Value |
|---|---|
| Customer | xyz |
| Location | Hyderabad, Telangana |
| Electricity provider | TSSPDCL |
| Contract limit | 500 kVA |
| Problem | Exceeding the limit 9 out of 12 months and paying penalties |

---

## What the Tool Does — Step by Step

### Step 1 — Reads the customer's electricity usage data
Loads 12 months of real usage data recorded every 15 minutes
(35,136 data points in total)

### Step 2 — Finds the peaks
Identifies which months the customer is exceeding their 
contract limit and by how much

### Step 3 — Sizes the battery
Calculates exactly what size battery is needed in kW and kWh
accounting for battery chemistry, efficiency and degradation

### Step 4 — Calculates the savings
Three separate saving streams:

| Saving Type | What It Means | Year 1 Amount |
|---|---|---|
| MD Charge Reduction | Lower peak = lower monthly demand bill | INR 6.21 L |
| Penal Charge Saving | No more contract breaches = no more penalties | INR 2.02 L |
| ToD Arbitrage | Charge at night (cheap), use during day (expensive) | INR 5.83 L |
| **Total** | | **INR 14.06 L** |

### Step 5 — Tests two business models
Compares revenue share vs fixed monthly fee to find 
which structure actually works

### Step 6 — Runs a 15-year financial model
Accounts for battery degradation, rising tariffs, 
loan repayment and discount rate to calculate 
real-world NPV, ROI and payback period

### Step 7 — Generates an Excel report
Professional 4-sheet report with charts — ready to 
present to a customer or investor

---

## What We Found

### The battery we sized
The energy company installs and owns the battery
The factory pays nothing upfront
Both parties share the savings the battery generates


Think of it like solar rooftop leasing — the factory gets 
the benefit without the investment risk.

---

## The Customer We Used As a Case Study

| Detail | Value |
|---|---|
| Customer | xyz |
| Location | Hyderabad, Telangana |
| Electricity provider | TSSPDCL |
| Contract limit | 500 kVA |
| Problem | Exceeding the limit 9 out of 12 months and paying penalties |

---

## What the Tool Does — Step by Step

### Step 1 — Reads the customer's electricity usage data
Loads 12 months of real usage data recorded every 15 minutes
(35,136 data points in total)

### Step 2 — Finds the peaks
Identifies which months the customer is exceeding their 
contract limit and by how much

### Step 3 — Sizes the battery
Calculates exactly what size battery is needed in kW and kWh
accounting for battery chemistry, efficiency and degradation

### Step 4 — Calculates the savings
Three separate saving streams:

| Saving Type | What It Means | Year 1 Amount |
|---|---|---|
| MD Charge Reduction | Lower peak = lower monthly demand bill | INR 6.21 L |
| Penal Charge Saving | No more contract breaches = no more penalties | INR 2.02 L |
| ToD Arbitrage | Charge at night (cheap), use during day (expensive) | INR 5.83 L |
| **Total** | | **INR 14.06 L** |

### Step 5 — Tests two business models
Compares revenue share vs fixed monthly fee to find 
which structure actually works

### Step 6 — Runs a 15-year financial model
Accounts for battery degradation, rising tariffs, 
loan repayment and discount rate to calculate 
real-world NPV, ROI and payback period

### Step 7 — Generates an Excel report
Professional 4-sheet report with charts — ready to 
present to a customer or investor

---

## What We Found

### The battery we sized
Type : LFP (Lithium Iron Phosphate)
Power : 110 kW
Energy : 300 kWh
Total cost : INR 93.8 Lakhs


### Which business model works?

We tested two models:

**Model A — Revenue Share (company takes 80% of savings)**

Customer saves : INR 2.81 Lakhs in Year 1 — zero investment
Company NPV : INR +1.58 Lakhs — VIABLE ✓
Payback : Year 12
ROI on equity : 425%


**Model B — Fixed Monthly Fee**

Fee customer can afford : INR 82,000/month maximum
Fee company needs to break even : INR 1,13,000/month minimum
Gap : INR 31,000/month — NOT VIABLE ✗


**Conclusion: Revenue share works. Fixed fee does not.**

---

## The Honest Story Behind This Project

This tool did not just confirm that BESS works.
It went through 7 iterations to find the deal structure 
that actually makes the numbers work:

Start → NPV -95 Lakhs wrong financing
After fix 1 → NPV -42 Lakhs better loan structure
After fix 2 → NPV -29 Lakhs changed tariff zone
After fix 3 → NPV -17 Lakhs lower battery cost
After fix 4 → NPV -11 Lakhs longer contract
After fix 5 → NPV -10.5 L higher revenue share
After fix 6 → NPV +1.58 L added second arbitrage cycle ✓

Most BESS models only show the final answer.
This one shows the journey — because that is what 
real analysis looks like.

---

## The Excel Report This Tool Generates

| Sheet | What It Shows |
|---|---|
| Executive Summary | One-page overview with all key numbers and load profile chart |
| Cash Flow Model | Year-by-year cash flows with payback curve |
| Monthly Savings | How savings vary across seasons — peak summer vs winter |
| Battery and Tariff | Battery degradation over 15 years and tariff structure |

---

## How To Run It

### What you need
- Python 3.8 or above
- Jupyter Notebook

### Install the libraries
```bash
pip install pandas numpy matplotlib openpyxl
```

### Clone and open
```bash
git clone https://github.com/Abhishek1268/Indian-CnI-BESS-Sizing-Tool
cd Indian-CnI-BESS-Sizing-Tool
jupyter notebook BESS_Sizing_Tool.ipynb
```

### Run all cells from top to bottom
The notebook creates the sample load profile automatically.
No external data file needed to get started.

### Use your own customer data
Replace the data generation cell with:
```python
df = pd.read_csv('your_file.csv', parse_dates=['timestamp'])
```
Your file needs two columns:
- `timestamp` — date and time every 15 minutes
- `demand_kw` — electricity demand in kilowatts

---

## How To Change It For a Different Customer

All the key inputs are clearly labelled at the top of each block:

```python
SANCTIONED_LIMIT_KW          = 450    # from customer's DISCOM contract
PEAK_SHAVING_TARGET_PCT      = 20     # how aggressively to shave the peak
MD_CHARGE_INR_PER_KVA_MONTH  = 500    # from the local tariff schedule
BATTERY_COST_INR_PER_KWH     = 25000  # current market price
COMPANY_REVENUE_SHARE_PCT    = 80     # contract negotiation
CONTRACT_YEARS               = 15     # contract length
```

Change these six numbers and the entire model recalculates.

---

## Files In This Repository

BESS_Sizing_Tool.ipynb — main notebook
load_profile_xyz_12m.csv — sample 12-month data
BESS_BaaS_Report_xyz.xlsx — sample Excel output
chart_load.png — load profile chart
chart_monthly.png — monthly savings chart
chart_payback.png — company payback curve
chart_degradation.png — battery degradation chart
README.md — this file


---

## Tech Stack

| Tool | Used For |
|---|---|
| Python | Core programming language |
| Pandas | Reading and processing load profile data |
| NumPy | Financial calculations |
| Matplotlib | Generating charts |
| OpenPyXL | Building the Excel report |
| Jupyter Notebook | Interactive step-by-step environment |

---

## Tariff Data Source

All tariff numbers are from the official TSSPDCL published 
tariff schedule for FY 2025-26:

[TSSPDCL Tariff Schedule FY 2025-26](https://tgsouthernpower.org/resources/PDF/Tariffs/63tarifffile.pdf)

Key rates used:
- Demand charge: INR 500/kVA/month
- Energy charge: INR 7.65/kWh  
- Peak surcharge: +INR 1.00/kWh (6-10am and 6-10pm)
- Off-peak rebate: -INR 1.50/kWh (10pm-6am)
- Billing demand: higher of actual peak or 80% of contracted demand

---

## About the Author

**Abhishekkumar Prakashkumar Panchal**

M.Eng. Smart Energy Systems — Hochschule Ansbach, Germany

I build techno-economic models for battery storage and 
energy management systems with a focus on the Indian 
and European C&I markets.

[LinkedIn](https://linkedin.com/in/abhishekkumar-panchal-2391a4253) 
| [GitHub](https://github.com/Abhishek1268)
| abhishekpanchal3041@gmail.com

---

## Licence

MIT — free to use with attribution.
