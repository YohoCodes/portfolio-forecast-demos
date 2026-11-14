# portfolio-forecast demos

Jupyter notebooks that work through complete examples of
[portfolio-forecast](https://github.com/YohoCodes/portfolio-forecast), a
Monte Carlo simulator of future portfolio and strategy returns. The first
three download prices from Yahoo Finance. `01` and `02b` use a window that
ends today, so their numbers change from run to run; `02a` uses a fixed
window (2025-10-31 to 2026-10-31). The last generates its own synthetic
history.

| Notebook | What it does |
| --- | --- |
| `01_quick_start_daily.ipynb` | Quick start on daily prices: backtests a four-stock portfolio, forecasts it with all three simulators, compares their fan charts and statistical reports, and compiles a PDF report |
| `02a_intraday_backtest_mistakes.ipynb` | Four common intraday backtesting mistakes and their fixes, on hourly AAPL bars: labelling a bar's close with the time of its open, measuring every return close-to-close, treating the backtest as proof, and pooling overnight gaps with bar returns in a Monte Carlo simulation. Builds each fix by hand, then repeats the whole analysis in a few lines of portfolio-forecast |
| `02b_intraday_sessions_and_gaps.ipynb` | Introduction to working with intraday sessions: backtests a three-stock portfolio on hourly data and forecasts future returns with nonparametric simulation, forecasts BTC with regime-switching Monte Carlo |
| `03_choosing_a_simulator.ipynb` | 🚧 Under Maintenance |

To read them without installing anything, open them on GitHub, which shows
the saved outputs. Links in the notebooks point to the
[portfolio-forecast 0.4.0 README](https://github.com/YohoCodes/portfolio-forecast/blob/v0.4.0/README.md).

## Running the demos

Requires Python 3.10 or later.

1. Clone this repository and create a virtual environment:

   ```bash
   git clone https://github.com/YohoCodes/portfolio-forecast-demos.git
   cd portfolio-forecast-demos
   python3 -m venv venv            # Doesn't work? Try python instead of python3
   source venv/bin/activate        # Windows Powershell: .\venv\Scripts\Activate.ps1, Windows Command Prompt: venv\Scripts\activate.bat
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

4. Run all cells. Demos `01`, `02a` and `02b` need internet access to
   download prices. The last step of `01_quick_start_daily.ipynb` builds a PDF with
   LaTeX and needs `pdflatex` on the PATH (for example from TeX Live, MacTeX
   or MiKTeX); without it, that cell says so and skips the PDF. The PDF is
   saved to `Reporting/`, which git ignores.
