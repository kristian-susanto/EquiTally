# EquiTally — Unified Tool Suite Documentation

Welcome to the unified documentation for **EquiTally**. EquiTally combines four essential tools into a single, high-performance web interface: the **Stock Multi-Tab Researcher**, **Click Counter**, **Text Case Converter**, and **Financial Shorthand Converter**. The Financial Shorthand Converter transforms shorthand financial values with **K**, **M**, **B**, and **T** suffixes into full numbers.

This README merges all references into one unified guide for professional workflows, capital market analytics, productivity tracking, and financial data preparation.

---

## Table of Contents

- [Overview](#overview)
- [Core Key Features](#core-key-features)
  - [1. Stock Multi-Tab Researcher](#1-stock-multi-tab-researcher)
  - [2. Click Counter](#2-click-counter)
  - [3. Text Case Converter](#3-text-case-converter)
  - [4. Financial Shorthand Converter](#4-financial-shorthand-converter)
- [Global Core Layout Specifications](#global-core-layout-specifications)
- [Prerequisites & Environment Setup](#prerequisites--environment-setup)
  - [Prerequisites](#prerequisites)
  - [Step 1: Create a Virtual Environment](#step-1-create-a-virtual-environment)
  - [Step 2: Activate the Virtual Environment](#step-2-activate-the-virtual-environment)
  - [Step 3: Install Dependencies](#step-3-install-dependencies)
  - [Step 4: Run the Application](#step-4-run-the-application)
- [How to Use EquiTally](#how-to-use-equitally)
  - [Step 1: Initialize the Application](#step-1-initialize-the-application)
  - [Step 2: Utilizing the Stock Researcher](#step-2-utilizing-the-stock-researcher)
  - [Step 3: Operating the Click Counter](#step-3-operating-the-click-counter)
  - [Step 4: Converting Data Typography](#step-4-converting-data-typography)
  - [Step 5: Using the Financial Shorthand Converter](#step-5-using-the-financial-shorthand-converter)
- [Financial Shorthand Converter Reference](#financial-shorthand-converter-reference)
  - [Features](#features)
  - [Quick Start](#quick-start)
  - [Input Format](#input-format)
  - [Output Format](#output-format)
  - [Reverse Order Option](#reverse-order-option)
  - [How It Works](#how-it-works)
  - [Customization](#customization)
  - [Browser Support](#browser-support)
  - [Troubleshooting](#troubleshooting)
- [Unified Architecture & Technologies Used](#unified-architecture--technologies-used)
- [License](#license)

---

## Overview

EquiTally is a unified suite that provides complementary productivity, analytics, and financial data preparation tools:

1. **Stock Multi-Tab Researcher** — Launch multiple research tabs for a selected exchange, ticker, and data provider, including a locally rendered historical data view.
2. **Click Counter** — Track high-frequency click interactions with persistent state and safe reset controls.
3. **Text Case Converter** — Transform text between uppercase, lowercase, title case, sentence case, and toggle case.
4. **Financial Shorthand Converter** — Convert `K`, `M`, `B`, and `T` financial shorthand values into full integers for spreadsheet workflows.

Together, these tools eliminate context switching by combining productivity utilities, capital market analytics, and financial data normalization in one browser-based application.

---

## Core Key Features

### 1. 📊 Stock Multi-Tab Researcher

Designed for investors, traders, and financial analysts to eliminate repetitive browser research by triggering deep-dive analysis pipelines simultaneously with a single action.

- **Multi-Tab Execution Workflow:** Generates and launches custom analytical URLs instantly, mapping exchange codes and asset symbols dynamically.
- **Cross-Global Exchange Resolution System:** Out-of-the-box support for international markets including NYSE, NASDAQ, IDX, HKG, SGX, LON, TYO, and more.
- **Granular Data Point Filtering:** Choose precisely which dimensions to investigate (e.g., Latest News, Financial Ratios, Historical Trends, Balance Sheets, Income Statements, Cash Flow Metrics, or Dividend Trackers).
- **Triple Data Source Support:** Switch the structural parsing logic between **Package**, **StockAnalysis**, or **TradingView** environments depending on your data pipeline preferences.
- **Package Mode (Default):** A one-click bundled workflow that ignores the granular checklist and launches a fixed set of **6 analytical tabs** in a single action — combining StockAnalysis, TradingView, and a locally rendered historical data view.
- **Local Historical Data View:** The ⏳ **Historical Data** tab is rendered on the fly by the Flask backend. It queries Yahoo Finance quarterly closes (10 years) and displays them in a **transposed, responsive table** — dates across the top row, close prices in a single row underneath — with a sticky first column for easy horizontal scrolling.
- **Context-Aware Keyboard Shortcut:** Pressing `Enter` inside the Exchange Name field, Ticker Symbol field, or any radio option immediately triggers the research pipeline — no need to move your mouse to the button.
- **Fail-Safe Manual Backup Registry:** Embedded link presentation tier ensures that if a modern browser blocks multi-popups, backup clickable links render seamlessly to bypass security restrictions.

### 2. 🖱️ Click Counter

A lightweight, reactive digital tallying and micro-interaction sandbox designed for high-frequency tracking.

- **Micro-Interaction Visual System:** Live viewport numbers dynamically expand and contract using hardware-accelerated CSS scaling matrices upon click inputs for clear visual feedback.
- **Persistence State Stabilization:** Intercepts volatile browser events (such as accidental keyboard `F5` or `Ctrl+R` refreshes) to secure temporary click counts from unintended memory clears.
- **Safe Reset Dialogs:** Employs explicit user-intent confirmations before wiping state tracking records back to zero.

### 3. 🔤 Text Case Converter

A professional-grade typographical formatting workstation tailored for developers, copywriters, and structured data cleaners.

- **Multi-State Transformation Matrix:**
  - `UPPERCASE`: Standardizes code variables, tickers, or headings into all capital letters.
  - `lowercase`: Converts string strings to lowercase formats for normalized database ingestions.
  - `Capitalize Word`: Formats strings into title-case blocks by auto-capitalizing every segmented word.
  - `Sentence case`: Corrects running prose by adjusting only the initial character of text sequences.
  - `tOGGLE cASE`: Inverts the casing state of every single character arrays instantly.
- **One-Click Buffer Interface:** Directly interacts with the system clipboard APIs for frictionless, one-tap copy operations.
- **Protected Erasure Actions:** Guardrails data entries against accidental losses with integrated SweetAlert validation handlers.

### 4. 💰 Financial Shorthand Converter

A lightweight, responsive module that converts shorthand financial values with **K**, **M**, **B**, and **T** suffixes into full numbers. It automatically skips percentage lines, outputs tab-separated values for easy pasting into Sheets (horizontally), and includes an optional reverse-order feature to match right-to-left spreadsheet layouts.

- **Suffix conversion** — Converts `K` (×1,000), `M` (×1,000,000), `B` (×1,000,000,000), and `T` (×1,000,000,000,000) to full integers.
- **Percentage skipping** — Lines containing a `%` sign are ignored automatically.
- **Horizontal paste** — Output values are separated by tabs (`\t`), so they paste across a row in Sheets.
- **Reverse order** — Optional checkbox to reverse the output order, ideal for spreadsheets that list newest data on the left.
- **Exact math** — Uses BigInt arithmetic to avoid floating-point errors with very large numbers.
- **Invisible character handling** — Strips zero-width and bidirectional control characters that often come with copied data.
- **Responsive design** — Works on desktop, tablet, and mobile.
- **One-click copy** — Copies the entire output to the clipboard.
- **No dependencies** — Implemented in vanilla JavaScript with no external runtime libraries.

---

## Stock Researcher — Data Source Modes

The Stock Multi-Tab Researcher supports three distinct data-source modes, selectable through the **Data Source Support** radio panel. The selected mode determines which URLs are generated, how ticker casing is normalized, and whether the granular checklist is used.

| Mode              | Default | Checklist Used? | Tabs Opened | Description                                                                                                                                  |
| ----------------- | :-----: | :-------------: | :---------: | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Package**       |   ✅    |       No        |      6      | Fixed multi-source bundle (StockAnalysis + TradingView + Local Historical Data) launched simultaneously. Ideal for deep-dive reconnaissance. |
| **StockAnalysis** |    —    |       Yes       |    1 – 9    | Granular control; only the checklist-selected data points are opened. Tickers are normalized to lowercase.                                   |
| **TradingView**   |    —    |       Yes       |    1 – 9    | Granular control; only the checklist-selected data points are opened. Tickers are normalized to uppercase, exchange codes remapped.          |

### Package Mode — Fixed 6-Tab Bundle

When **Package** is selected (the default), the data-point checklist is dimmed and disabled, and clicking **Open All Selected Tabs** immediately launches the following six analytical views:

| #   | Data Point          | Provider                      | Purpose                                                     |
| --- | ------------------- | ----------------------------- | ----------------------------------------------------------- |
| 1   | 🏢 Overview         | StockAnalysis                 | Company profile, sector, business summary                   |
| 2   | 🏢 Overview         | TradingView                   | Company profile, sector, business summary                   |
| 3   | 📊 Ratios           | TradingView                   | Quarterly statistics and valuation ratios                   |
| 4   | ⏳ Historical Data  | Local (Flask + Yahoo Finance) | Quarter-end closing prices, last 10 years, transposed table |
| 5   | 📑 Income Statement | TradingView                   | Quarterly income statement                                  |
| 6   | ⚖️ Balance Sheet    | TradingView                   | Quarterly balance sheet                                     |

Package mode is intentionally unconfigurable — it is a fixed reconnaissance bundle designed so that switching between providers is not necessary when you simply want comprehensive coverage of a ticker. The locally rendered **Historical Data** tab is unique to Package mode and is opened via a client-side fetch to the Flask `/proxy` endpoint.

### Local Historical Data Tab

When the ⏳ **Historical Data** target is executed (only available inside Package mode), EquiTally opens a fresh browser tab and performs the following:

1. Resolves the ticker to a Yahoo Finance symbol using the exchange suffix map (e.g., `IDX → .JK`, `HKG → .HK`, `TYO → .T`).
2. Calls the Flask `/proxy?symbol=…&range=10y&interval=1d` endpoint, which forwards the request to Yahoo Finance with a desktop User-Agent header.
3. Parses the returned daily closes and reduces them to **quarter-end closing prices** (one data point per calendar quarter).
4. Renders a **transposed, responsive table**:
   - Dates run across the top header row.
   - A single **Close Price** row sits beneath, with values aligned to their respective dates.
   - The first column (`Quarter-End` / `Close Price`) is **sticky** so it remains visible while scrolling horizontally.
   - The table uses a 💼 favicon, matches the global light/dark theme via `prefers-color-scheme`, and adapts its padding/typography on mobile screens.

If a ticker is invalid or Yahoo Finance returns no data, the tab renders a friendly error card instead of the table.

---

## Global Core Layout Specifications

- **Hybrid Flask + Client-Side Architecture:** The frontend runs entirely inside the browser viewport, while a lightweight **Flask backend** (`app.py`) serves the page and provides a single `/proxy` endpoint used exclusively for fetching Yahoo Finance historical data.
- **Unified Global Theme Switcher:** Features a centralized master light/dark theme manager. Changes map instantly across all component blocks, typography color tokens, and custom alert cards.
- **Persistent Preferences:** Automatically mirrors user theme states using modern browser `localStorage`, ensuring your preferred interface style persists across subsequent sessions.
- **Fully Responsive Matrix UI:** Built from the ground up using clean CSS grids and fluid flexbox structures. Seamlessly transforms between compact mobile screens, tablets, and extensive multi-monitor setups.
- **Optimized Typography & Footprint:** Employs a crisp font stack hierarchy and inline SVG assets to ensure instant paint times and high layout performance.

---

## Prerequisites & Environment Setup

Before running EquiTally, ensure you have the following installed on your machine.

### Prerequisites

- **Python 3.8 or higher** — [Download Python](https://www.python.org/downloads/)
- **pip** (Python package installer, bundled with modern Python installations)

Verify your installation by running:

```bash
python --version
pip --version
```

### Step 1: Create a Virtual Environment

It is strongly recommended to isolate your project dependencies using a virtual environment. Navigate to the project folder containing `app.py`, then run:

**Windows:**

```bash
python -m venv venv
```

**macOS / Linux:**

```bash
python3 -m venv venv
```

### Step 2: Activate the Virtual Environment

**Windows (Command Prompt):**

```bash
venv\Scripts\activate
```

**Windows (PowerShell):**

```powershell
.\venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

Once activated, your terminal prompt should be prefixed with `(venv)`.

### Step 3: Install Dependencies

EquiTally requires **Flask** and **requests**. Install them with:

```bash
pip install flask requests
```

> **Tip:** You can also create a `requirements.txt` file containing:
>
> ```
> flask
> requests
> ```
>
> Then install with `pip install -r requirements.txt`.

### Step 4: Run the Application

Start the Flask development server:

```bash
python app.py
```

You should see the following banner in your terminal:

```
=======================================================
  EquiTally Server Running
  Open:  http://localhost:5000
=======================================================
```

Open your browser and navigate to `http://localhost:5000` to access the application.

---

## How to Use EquiTally

### Step 1: Initialize the Application

Run the Flask server from your terminal:

```bash
python app.py
```

Then open your browser and navigate to:

```
http://localhost:5000
```

The console will print the EquiTally banner and the exact URL for convenience.

### Step 2: Utilizing the Stock Researcher

1. **Define the Destination Market:** Begin typing the name of an exchange in the **Exchange Name** text area. Select from the automated global autocomplete registry (e.g., _Indonesia Stock Exchange (Indonesia)_ or _Nasdaq Stock Market (United States)_).
2. **Input Asset Tickers:** Input your specific tracking target code into the **Ticker Symbol** field (e.g., `BBRI`, `AAPL`, or `D05`).
3. **Choose Your Analytics Provider:** Select one of the three modes in the **Data Source Support** radio panel:
   - **📦 Package (default)** — Skips the checklist and launches a fixed 6-tab bundle across StockAnalysis, TradingView, and the local Historical Data view. Best for comprehensive reconnaissance.
   - **StockAnalysis** — Enables the checklist; only selected data points are opened. Tickers are normalized to lowercase.
   - **TradingView** — Enables the checklist; only selected data points are opened. Tickers are normalized to uppercase and exchange codes are remapped (e.g., `SHA` → `SSE`).
4. **Configure Your Focus Area (Checklist modes only):** If you are in StockAnalysis or TradingView mode, use the checkbox panel to specify the modules you need. You can use the instant `All` or `None` triggers to modify selections quickly. _(This panel is disabled in Package mode.)_
5. **Execute Research Tabs:** Click **Open All Selected Tabs** — or simply press `Enter` while focused on the Exchange Name, Ticker Symbol, or a radio option.
   - _Note on Security Blocks:_ If the tabs do not open immediately, check your browser's address bar for a "Pop-up Blocked" icon, select "Always allow pop-ups from this source," and retry. Alternatively, use the manually generated reference panel that appears below the controls.
   - _Note on the Historical Data tab:_ Because the historical view is fetched from your local Flask server, it must run from `http://localhost:5000` (or your deployed host). Opening the HTML file directly from the filesystem will disable the proxy call.

### Step 3: Operating the Click Counter

1. Click or tap the primary **CLICK HERE** module to increment tally parameters seamlessly.
2. To clear the counting buffer, activate the red **Reset** button and accept the verification prompt.

### Step 4: Converting Data Typography

1. Paste or type any alphanumeric raw data strings inside the centralized textarea.
2. Trigger any of the five available case transformations to modify text values instantly.
3. Click **Copy to Clipboard** to export your formatted text directly into your workflow buffers.

### Step 5: Using the Financial Shorthand Converter

1. Paste your list of values into the **Input** textarea.
2. (Optional) Adjust the **Reverse order** checkbox if needed.
3. Click **Copy result**.
4. Paste into your Sheets spreadsheet — values will fill a row horizontally.

---

## Keyboard Shortcuts

| Shortcut                      | Context                                          | Action                                                          |
| ----------------------------- | ------------------------------------------------ | --------------------------------------------------------------- |
| `Enter`                       | Exchange Name field                              | Triggers **Open All Selected Tabs**                             |
| `Enter`                       | Ticker Symbol field                              | Triggers **Open All Selected Tabs**                             |
| `Enter`                       | Radio option (Package/StockAnalysis/TradingView) | Triggers **Open All Selected Tabs**                             |
| `Enter`                       | Focused button                                   | Activates that specific button                                  |
| `Enter`                       | Inside any textarea                              | Inserts a new line (default browser behaviour)                  |
| `Ctrl + R` / `Cmd + R` / `F5` | Anywhere                                         | Blocked — refresh is intercepted to protect click-counter state |

---

## Financial Shorthand Converter Reference

The Financial Shorthand Converter is a lightweight, responsive web tool that converts shorthand financial values with **K**, **M**, **B**, and **T** suffixes into full numbers. It automatically skips percentage lines, outputs tab-separated values for easy pasting into Sheets (horizontally), and includes an optional reverse-order feature to match right-to-left spreadsheet layouts.

---

### Features

- **Suffix conversion** – Converts `K` (×1,000), `M` (×1,000,000), `B` (×1,000,000,000), and `T` (×1,000,000,000,000) to full integers.
- **Percentage skipping** – Lines containing a `%` sign are ignored automatically.
- **Horizontal paste** – Output values are separated by tabs (`\t`), so they paste across a row in Sheets.
- **Reverse order** – Optional checkbox to reverse the output order, ideal for spreadsheets that list newest data on the left.
- **Exact math** – Uses BigInt arithmetic to avoid floating-point errors with very large numbers.
- **Invisible character handling** – Strips zero-width and bidirectional control characters that often come with copied data.
- **Responsive design** – Works on desktop, tablet, and mobile.
- **One-click copy** – Copies the entire output to the clipboard.
- **No dependencies** – A single module with embedded CSS and JavaScript.

---

### Quick Start

1. Start the Flask server with `python app.py` and open `http://localhost:5000` in any modern web browser.
2. Paste your list of values into the **Input** textarea.
3. (Optional) Adjust the **Reverse order** checkbox if needed.
4. Click **Copy result**.
5. Paste into your Sheets spreadsheet – values will fill a row horizontally.

---

### Input Format

- One value per line.
- Each line may contain:
  - A number with optional decimal point (e.g., `9.26`, `10`, `11.64`).
  - An optional suffix: `K`, `M`, `B`, or `T` (case-insensitive).
  - An optional sign: `+` or `−` (the tool normalises various dash characters).
- Lines that contain a `%` symbol are skipped entirely.
- Blank lines are ignored.
- Extra spaces and invisible Unicode characters are cleaned automatically.

**Example input:**

```text
9.26 T
−2.05%
9.70 T
+4.25%
10.33 T
+9.01%
9.90 T
+1.90%
10.55 T
+13.93%
10.06 T
+3.75%
10.12 T
−2.02%
11.64 T
+17.60%
```

---

### Output Format

- Each valid input line produces a full integer with comma thousands separators (e.g., `9,260,000,000,000`).
- Percentage lines are omitted.
- All results are joined with a tab character (`\t`), so they appear on a single line in the output textarea.
- When pasted into Sheets, each value occupies its own cell in a row.

**Example output (for the input above):**

```text
9,260,000,000,000	9,700,000,000,000	10,330,000,000,000	9,900,000,000,000	10,550,000,000,000	10,060,000,000,000	10,120,000,000,000	11,640,000,000,000
```

> **Note:** If the **Reverse order** checkbox is checked, the output sequence is reversed (e.g., `11,640,000,000,000` first).

---

### Reverse Order Option

Many financial spreadsheets place the most recent period on the left and older periods on the right. If your input list is ordered from oldest to newest (left to right), enabling **Reverse order** will flip the sequence so the newest value appears first when pasted.

- **Checked (default):** Output is reversed. Newest (last in input) becomes first (leftmost in spreadsheet).
- **Unchecked:** Output preserves the original input order.

You can toggle this checkbox at any time; the output updates instantly.

---

### How It Works

1. **Line parsing** – Each line is cleaned of invisible characters and trimmed.
2. **Percentage detection** – If a line contains `%`, it is skipped.
3. **Number extraction** – A regular expression captures the sign, numeric part, and optional suffix.
4. **Suffix mapping** – The suffix is mapped to a BigInt multiplier:
   - `K` → 1,000
   - `M` → 1,000,000
   - `B` → 1,000,000,000
   - `T` → 1,000,000,000,000
   - No suffix → 1
5. **Exact multiplication** – The numeric string is split into integer and fractional parts. Both the scale (10^fraction length) and the multiplier are powers of ten, so the conversion is exact using BigInt arithmetic.
6. **Formatting** – The resulting integer is converted to a string and commas are inserted every three digits.
7. **Output assembly** – All converted values are collected, optionally reversed, and joined with tabs.

---

### Customization

You can easily modify the tool to suit your needs by editing the source files:

- **Sample data** – Change the `SAMPLE` array in the `<script>` section of `app.py` to load your own example.
- **Multipliers** – Adjust the `MULT` object if you need different scaling factors.
- **Placeholder text** – Update the `placeholder` attributes on the textareas.
- **Styling** – All CSS is embedded in the `<style>` block inside `HTML_PAGE`; feel free to tweak colors, fonts, or layout.
- **Package tab delay** – Adjust the `350` millisecond timeout inside `processSearch()` to change the delay between opening bundled Package tabs.
- **Proxy timeout** – The `/proxy` route uses a 15-second timeout to Yahoo Finance; adjust as needed for slower networks.

No build step is required — the Flask server hosts the single-file frontend.

---

### Browser Support

The tool works in all modern browsers that support:

- ES6+ (arrow functions, `const`/`let`, template literals are not used extensively, but BigInt is required).
- BigInt (Chrome 67+, Firefox 68+, Safari 14+, Edge 79+).
- Async clipboard API (or falls back to `document.execCommand('copy')`).
- `fetch` API for the local Historical Data proxy.

For older browsers, the fallback copy method may work, but BigInt support is essential.

---

### Troubleshooting

| Issue                                          | Possible Cause                               | Solution                                                                                                                         |
| ---------------------------------------------- | -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Copy button does nothing                       | Browser blocks clipboard access              | Use a secure context (HTTPS or localhost) or copy manually from the output textarea.                                             |
| Values not pasting horizontally                | Spreadsheet settings                         | Ensure you paste into a single cell and that the tab character is preserved. Some apps may convert tabs to spaces.               |
| Wrong number of columns                        | Input contains unrecognised lines            | Check the stats indicator (e.g., "8 converted · 8 skipped"). Unrecognised lines are silently ignored.                            |
| Reverse order not working                      | Checkbox state                               | Make sure the checkbox is checked if you need reversed output.                                                                   |
| Large numbers lose precision                   | JavaScript number limitations                | The tool uses BigInt, so precision is maintained. If you see incorrect values, ensure you are using a modern browser.            |
| `Enter` does not trigger search                | Focused inside a `<textarea>`                | Textareas (ZeroShift, Text Case Converter) intentionally keep native newline behaviour. Move focus to the Exchange/Ticker field. |
| Package mode launched too few tabs             | Fixed bundle of 6 tabs is expected           | This is by design. Switch to StockAnalysis or TradingView mode if you prefer granular checklist control.                         |
| Historical Data tab shows error                | Flask `/proxy` unreachable or ticker invalid | Ensure `python app.py` is running and the page is loaded from `http://localhost:5000`. Verify the ticker and exchange code.      |
| Historical Data favicon still shows old emoji  | Browser favicon cache                        | Perform a hard refresh (`Ctrl + F5` / `Cmd + Shift + R`) or open the tab in an incognito window.                                 |
| Historical table dates not aligned with prices | Horizontal scrolling is expected             | The table is intentionally transposed. The `Quarter-End` column stays sticky on the left while you scroll to compare dates.      |

---

## Unified Architecture & Technologies Used

- **Flask (Python) Backend:** `app.py` serves the single-file frontend via `render_template_string` and exposes a `/proxy` endpoint that forwards requests to Yahoo Finance for historical price data. This is the only server-side component.
- **HTML5 Elements:** Structured content layout separating input contexts from interactive control modules.
- **CSS3 Variables & Responsive Design:** Centralized color variables handle real-time theme swapping, while a mobile-first layout engine guarantees responsive adaptations — including the transposed, horizontally scrollable Historical Data table.
- **Vanilla JavaScript (ES6+):** Manages local caching layers, handles typography transformations, monitors tracking variables, maps data parameters into targeted financial URL strings, and renders the local Historical Data tab.
- **SweetAlert2 Library Integration:** Leveraged for modern, non-blocking toast popups and validation dialogs that automatically match the selected system theme.
- **BigInt Arithmetic:** Used by EquiTally's Financial Shorthand Converter for exact financial suffix conversion without floating-point precision loss.
- **Clipboard API Integration:** Enables one-click copy operations across EquiTally, with fallback support where needed.
- **`requests` (Python):** Used by the Flask `/proxy` route to make outbound HTTP calls to Yahoo Finance with a desktop User-Agent header.

---

## License

EquiTally is provided as-is for personal and commercial use. No warranty is expressed or implied. You are free to modify and distribute it.
