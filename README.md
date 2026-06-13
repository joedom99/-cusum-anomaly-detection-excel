# CUSUM Anomaly Detection in Excel

![Excel](https://img.shields.io/badge/Excel-spreadsheet-217346?logo=microsoftexcel&logoColor=white)
![Project Type](https://img.shields.io/badge/project%20type-marketing%20analytics-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Made With Love](https://img.shields.io/badge/made%20with-love-red)

A simple Excel example showing how CUSUM can catch a slow-moving anomaly before a single-day threshold would notice it.

This spreadsheet supports my article: **When the Numbers Look Wrong: A Marketer’s Guide to Anomaly Detection**.

---

## What's Included

- `cusum-anomaly-detection.xlsx` — the example spreadsheet
- A 60-day website sessions example
- A one-sided upper CUSUM model for detecting a slow bot traffic creep
- Editable inputs for:
  - Baseline sessions
  - Slack / allowance
  - Alert threshold
- A short explanation tab showing how the formula works

---

## Why This Matters

A basic z-score or control chart can catch big, obvious spikes.

But marketing problems are not always obvious. Sometimes bot traffic creeps in slowly. Sometimes a tracking event fades a little each day. Sometimes nothing looks strange on its own, but the pattern is moving.

CUSUM helps by adding up small, persistent deviations from normal until the accumulated drift is large enough to deserve attention.

---

## The Core Formula

```excel
CUSUM today = MAX(0, CUSUM yesterday + (Sessions today - baseline) - slack)
```

The alert fires when:

```excel
CUSUM > threshold
```

In the example sheet, the alert first fires on **day 48**, when the CUSUM value crosses the threshold of **600**.

---

## How to Use It

1. Download or clone this repository.
2. Open `cusum-anomaly-detection.xlsx` in Excel.
3. Change the yellow input cells:
   - Baseline sessions
   - Slack / allowance
   - Threshold
4. Watch how the alert moves.

Lowering the threshold makes the detector more sensitive. Raising the slack makes it less sensitive. That tradeoff is the whole point.

---

## Files

| File | Description |
|---|---|
| `cusum-anomaly-detection.xlsx` | Excel spreadsheet with the CUSUM model |
| `README.md` | Project overview and instructions |
| `LICENSE` | MIT license |

---

## Notes

This is a teaching example, not a production monitoring system. In real marketing data, you would also want to account for seasonality, holidays, campaigns, tracking changes, and known events.

Use the spreadsheet to understand the basic idea first. Then make it more realistic.

---

## Learn More

You can read more at [Marketing Data Science](https://blog.marketingdatascience.ai/).

---

## Author

Joe Domaleski  
[GitHub](https://github.com/joedom99) • [LinkedIn](https://www.linkedin.com/in/joedom/) • [Marketing Data Science](https://blog.marketingdatascience.ai/)

---

## License

This project is licensed under the MIT License.

