# portfolio-forecast demos

Jupyter notebooks that work through complete examples of
[portfolio-forecast](https://github.com/YohoCodes/portfolio-forecast), a
Monte Carlo simulator of future portfolio and strategy returns. The first two
download recent prices from Yahoo Finance, over a window that ends today, so
their numbers change from run to run; the third generates its own synthetic
history.

| Notebook | What it does |
| --- | --- |
| `01_quick_start_daily.ipynb` | Quick start on daily prices: backtests a four-stock portfolio, forecasts it with all three simulators, compares their fan charts and statistical reports, and compiles a PDF report |
| `02_intraday_sessions_and_gaps.ipynb` | Intraday sessions and gaps on hourly bars: the marks of a session, return classes and their warnings, gap and bar volatility, future marks across a weekend and a half-day, a forecast counted in sessions, and continuous mode for a 24/7 asset |
| `03_choosing_a_simulator.ipynb` | Choosing a simulator, on a synthetic two-regime history whose true model is known, so each method can be checked against the truth |

To read them without installing anything, open them on GitHub, which shows
the saved outputs. Links in the notebooks point to the
[portfolio-forecast 0.4.0 README](https://github.com/YohoCodes/portfolio-forecast/blob/v0.4.0/README.md).

## Running the demos

Requires Python 3.10 or later.

1. Clone this repository and create a virtual environment:

   ```bash
   git clone https://github.com/YohoCodes/portfolio-forecast-demos.git
   cd portfolio-forecast-demos
   python -m venv venv
   source venv/bin/activate        # Windows: venv\Scripts\activate
   ```

2. Install portfolio-forecast from PyPI with its `notebook` extra (which adds
   `yfinance` and `ipykernel`), plus JupyterLab:

   ```bash
   pip install -r requirements.txt
   ```

3. Open a demo:

   ```bash
   jupyter lab 01_quick_start_daily.ipynb
   ```

   In VS Code, open the notebook and select the `venv` Python as its kernel
   instead.

4. Run all cells. The first two demos need internet access to download
   prices. The last step of `01_quick_start_daily.ipynb` builds a PDF with
   LaTeX and needs `pdflatex` on the PATH (for example from TeX Live, MacTeX
   or MiKTeX); without it, that cell says so and skips the PDF. The PDF is
   saved to `Reporting/`, which git ignores.
