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

1. **Stock Multi-Tab Researcher** — Launch multiple research tabs for a selected exchange, ticker, and data provider.
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
- **Package Mode (Default):** A one-click bundled workflow that ignores the granular checklist and launches a fixed set of **8 analytical tabs** in a single action — perfect for deep-dive reconnaissance across both StockAnalysis and TradingView in parallel.
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
- **No dependencies** — A single HTML file with embedded CSS and JavaScript.

---

## Stock Researcher — Data Source Modes

The Stock Multi-Tab Researcher supports three distinct data-source modes, selectable through the **Data Source Support** radio panel. The selected mode determines which URLs are generated, how ticker casing is normalized, and whether the granular checklist is used.

| Mode              | Default | Checklist Used? | Tabs Opened | Description                                                                                                                         |
| ----------------- | :-----: | :-------------: | :---------: | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Package**       |   ✅    |       No        |      8      | Fixed multi-source bundle (StockAnalysis + TradingView) launched simultaneously. Ideal for deep-dive reconnaissance.                |
| **StockAnalysis** |    —    |       Yes       |    1 – 9    | Granular control; only the checklist-selected data points are opened. Tickers are normalized to lowercase.                          |
| **TradingView**   |    —    |       Yes       |    1 – 9    | Granular control; only the checklist-selected data points are opened. Tickers are normalized to uppercase, exchange codes remapped. |

### Package Mode — Fixed 8-Tab Bundle

When **Package** is selected (the default), the data-point checklist is dimmed and disabled, and clicking **Open All Selected Tabs** immediately launches the following eight analytical views:

| #   | Data Point          | Provider      | Purpose                                          |
| --- | ------------------- | ------------- | ------------------------------------------------ |
| 1   | 🏢 Overview         | StockAnalysis | Company profile, sector, business summary        |
| 2   | 📊 Ratios           | StockAnalysis | Quarterly financial ratios and valuation metrics |
| 3   | 📊 Ratios           | TradingView   | Quarterly statistics and ratios                  |
| 4   | ⏳ Historical Data  | StockAnalysis | Full historical price and volume records         |
| 5   | 📑 Income Statement | StockAnalysis | Quarterly income statement                       |
| 6   | 📑 Income Statement | TradingView   | Quarterly income statement                       |
| 7   | ⚖️ Balance Sheet    | StockAnalysis | Quarterly balance sheet                          |
| 8   | ⚖️ Balance Sheet    | TradingView   | Quarterly balance sheet                          |

Package mode is intentionally unconfigurable — it is a fixed reconnaissance bundle designed so that switching between providers is not necessary when you simply want comprehensive coverage of a ticker.

---

## Global Core Layout Specifications

- **100% Client-Side Architecture:** Runs completely inside the browser viewport. Zero database configurations, zero backend dependencies, and maximum data privacy.
- **Unified Global Theme Switcher:** Features a centralized master light/dark theme manager. Changes map instantly across all component blocks, typography color tokens, and custom alert cards.
- **Persistent Preferences:** Automatically mirrors user theme states using modern browser `localStorage`, ensuring your preferred interface style persists across subsequent sessions.
- **Fully Responsive Matrix UI:** Built from the ground up using clean CSS grids and fluid flexbox structures. Seamlessly transforms between compact mobile screens, tablets, and extensive multi-monitor setups.
- **Optimized Typography & Footprint:** Employs a crisp font stack hierarchy and inline SVG assets to ensure instant paint times and high layout performance.

---

## How to Use EquiTally

### Step 1: Initialize the Application

Run the unified EquiTally `.html` file inside any modern web browser window (e.g., Google Chrome, Microsoft Edge, Mozilla Firefox, or Apple Safari).

### Step 2: Utilizing the Stock Researcher

1. **Define the Destination Market:** Begin typing the name of an exchange in the **Exchange Name** text area. Select from the automated global autocomplete registry (e.g., _Indonesia Stock Exchange (Indonesia)_ or _Nasdaq Stock Market (United States)_).
2. **Input Asset Tickers:** Input your specific tracking target code into the **Ticker Symbol** field (e.g., `BBRI`, `AAPL`, or `D05`).
3. **Choose Your Analytics Provider:** Select one of the three modes in the **Data Source Support** radio panel:
   - **📦 Package (default)** — Skips the checklist and launches a fixed 8-tab bundle across StockAnalysis and TradingView. Best for comprehensive reconnaissance.
   - **StockAnalysis** — Enables the checklist; only selected data points are opened. Tickers are normalized to lowercase.
   - **TradingView** — Enables the checklist; only selected data points are opened. Tickers are normalized to uppercase and exchange codes are remapped (e.g., `SHA` → `SSE`).
4. **Configure Your Focus Area (Checklist modes only):** If you are in StockAnalysis or TradingView mode, use the checkbox panel to specify the modules you need. You can use the instant `All` or `None` triggers to modify selections quickly. _(This panel is disabled in Package mode.)_
5. **Execute Research Tabs:** Click **Open All Selected Tabs** — or simply press `Enter` while focused on the Exchange Name, Ticker Symbol, or a radio option.
   - _Note on Security Blocks:_ If the tabs do not open immediately, check your browser's address bar for a "Pop-up Blocked" icon, select "Always allow pop-ups from this source," and retry. Alternatively, use the manually generated reference panel that appears below the controls.

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
- **No dependencies** – A single HTML file with embedded CSS and JavaScript.

---

### Quick Start

1. Save the provided HTML code as `equitally.html` (or any name you prefer).
2. Open the file in any modern web browser.
3. Paste your list of values into the **Input** textarea.
4. (Optional) Adjust the **Reverse order** checkbox if needed.
5. Click **Copy result**.
6. Paste into your Sheets spreadsheet – values will fill a row horizontally.

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

You can easily modify the tool to suit your needs by editing the HTML file:

- **Sample data** – Change the `SAMPLE` array in the `<script>` section to load your own example.
- **Multipliers** – Adjust the `MULT` object if you need different scaling factors.
- **Placeholder text** – Update the `placeholder` attributes on the textareas.
- **Styling** – All CSS is embedded in the `<style>` block; feel free to tweak colors, fonts, or layout.
- **Package tab delay** – Adjust the `250` millisecond timeout inside `processSearch()` to change the delay between opening bundled Package tabs.

No build step or server is required.

---

### Browser Support

The tool works in all modern browsers that support:

- ES6+ (arrow functions, `const`/`let`, template literals are not used extensively, but BigInt is required).
- BigInt (Chrome 67+, Firefox 68+, Safari 14+, Edge 79+).
- Async clipboard API (or falls back to `document.execCommand('copy')`).

For older browsers, the fallback copy method may work, but BigInt support is essential.

---

### Troubleshooting

| Issue                               | Possible Cause                     | Solution                                                                                                                         |
| ----------------------------------- | ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- |
| Copy button does nothing            | Browser blocks clipboard access    | Use a secure context (HTTPS or localhost) or copy manually from the output textarea.                                             |
| Values not pasting horizontally     | Spreadsheet settings               | Ensure you paste into a single cell and that the tab character is preserved. Some apps may convert tabs to spaces.               |
| Wrong number of columns             | Input contains unrecognised lines  | Check the stats indicator (e.g., "8 converted · 8 skipped"). Unrecognised lines are silently ignored.                            |
| Reverse order not working           | Checkbox state                     | Make sure the checkbox is checked if you need reversed output.                                                                   |
| Large numbers lose precision        | JavaScript number limitations      | The tool uses BigInt, so precision is maintained. If you see incorrect values, ensure you are using a modern browser.            |
| `Enter` does not trigger search     | Focused inside a `<textarea>`      | Textareas (ZeroShift, Text Case Converter) intentionally keep native newline behaviour. Move focus to the Exchange/Ticker field. |
| Package mode launched too many tabs | Fixed bundle of 8 tabs is expected | This is by design. Switch to StockAnalysis or TradingView mode if you prefer granular checklist control.                         |

---

## Unified Architecture & Technologies Used

- **HTML5 Elements:** Structured content layout separating input contexts from interactive control modules.
- **CSS3 Variables & Responsive Design:** Centralized color variables handle real-time theme swapping, while a mobile-first layout engine guarantees responsive adaptations.
- **Vanilla JavaScript (ES6+):** Manages local caching layers, handles typography transformations, monitors tracking variables, and maps data parameters into targeted financial URL strings.
- **SweetAlert2 Library Integration:** Leveraged for modern, non-blocking toast popups and validation dialogs that automatically match the selected system theme.
- **BigInt Arithmetic:** Used by EquiTally's Financial Shorthand Converter for exact financial suffix conversion without floating-point precision loss.
- **Clipboard API Integration:** Enables one-click copy operations across EquiTally, with fallback support where needed.
- **Single-File / No-Dependency Design:** EquiTally is designed to run directly in the browser without backend services, database configuration, or build steps.

---

## License

EquiTally is provided as-is for personal and commercial use. No warranty is expressed or implied. You are free to modify and distribute it.
