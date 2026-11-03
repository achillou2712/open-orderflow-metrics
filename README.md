# open-orderflow-metrics
Vectorized Python calculations for Volume Profile (POC, VAH, VAL) and Cumulative Volume Delta (CVD) on time-series market data.
# Open Orderflow Metrics

A lightweight, vectorized Python toolkit for computing quantitative microstructure and volume-based indicators on financial time-series data without proprietary platforms.

## Implemented Metrics
- **Volume Profile:** Computes Point of Control (POC), Value Area High (VAH), and Value Area Low (VAL) across customizable price bins and value area thresholds (default 70%).
- **Cumulative Volume Delta (CVD):** Approximates intrabar buying/selling pressure and tracks institutional orderflow divergence.

## Usage

```python
import pandas as pd
from microstructure import compute_volume_profile, compute_cvd_approximation

df = pd.read_csv("ohlcv_data.csv")
profile = compute_volume_profile(df, bins=50, value_area_pct=0.70)
print(f"POC: {profile.poc} | VAH: {profile.vah} | VAL: {profile.val}")
