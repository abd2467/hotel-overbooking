# Hotel overbooking and deposit commitment

> **Decision:** _to be filled in when the analysis is done._ Overbook X rooms on weekdays and Y on weekends: net revenue +Z% vs a flat 5% rule, with chance of turning a guest away below W%.

**Status:** in progress (started 23 Nov 2026).

## The problem
Hotels lose money on rooms that are booked and then cancelled. In the open hotel booking dataset, 27.8% of resort bookings and 41.7% of city-hotel bookings were cancelled (Antonio et al., 2019). Most projects on this data stop at predicting cancellations. This one ends in a decision: how many rooms to overbook each night, and whether non-refundable deposits actually change guest behaviour.

## Approach
1. Explore the data and reproduce the published cancellation rates.
2. Survival analysis: when do bookings cancel, not just whether.
3. Propensity matching: do deposits change cancellation behaviour? (Deposits were not randomly assigned.)
4. Overbooking: newsvendor model and simulation, compared with a flat 5% rule.
5. Sensitivity: the cost of turning a guest away has no published figure, so results are shown across a range.

## Repo layout
| Folder | Contents |
|---|---|
| `data/` | Raw data (not committed) and processed files |
| `notebooks/` | Numbered analysis notebooks |
| `src/` | Reusable scripts |
| `app/` | Streamlit dashboard |
| `reports/` | Decision memo and charts |
| `notes/` | Learning log |

## Data
See [DATA_REGISTER.md](DATA_REGISTER.md). Raw data is not re-hosted here.

## How AI was used
See [AI_USE.md](AI_USE.md).

## Reproduce
```bash
git clone https://github.com/abd2467/hotel-overbooking.git
cd hotel-overbooking
python -m venv .venv
# Mac/Linux: source .venv/bin/activate    Windows: .venv\Scripts\activate
pip install -r requirements.txt
```
