# BadBuddha VWAP - NinjaTrader 8 Indicator

![Version](https://img.shields.io/badge/version-2.0.0-blue)
![NinjaTrader](https://img.shields.io/badge/NinjaTrader-8.0+-orange)
![License Lite](https://img.shields.io/badge/Lite-FREE-brightgreen)
![License Pro](https://img.shields.io/badge/Pro-Licensed-blue)

**Professional Volume Weighted Average Price indicator with optional standard deviation bands for NinjaTrader 8**

---

## 📊 Overview

BadBuddha VWAP is available in two editions:

- **🆓 Lite (FREE)**: Essential VWAP calculation with session resets
- **💎 Pro (Licensed)**: Advanced VWAP with standard deviation bands, multiple reset periods, and SharpDX rendering

Both versions feature clean code, automatic update alerts, and are optimized for performance.

---

## 🆚 Lite vs Pro Comparison

| Feature | Lite (FREE) | Pro (Licensed) |
|---------|-------------|----------------|
| **VWAP Calculation** | ✅ Yes | ✅ Yes |
| **Session Reset** | ✅ Yes | ✅ Yes |
| **Daily Reset** | ❌ No | ✅ Yes |
| **Weekly Reset** | ❌ No | ✅ Yes |
| **Monthly Reset** | ❌ No | ✅ Yes |
| **0.5 StdDev Bands** | ❌ No | ✅ Yes |
| **1.0 StdDev Bands** | ❌ No | ✅ Yes |
| **1.5 StdDev Bands** | ❌ No | ✅ Yes |
| **2.0 StdDev Bands** | ❌ No | ✅ Yes |
| **Shaded Band Fills** | ❌ No | ✅ Yes |
| **Opacity Control** | ❌ No | ✅ Yes (0-100%) |
| **SharpDX Rendering** | ❌ No | ✅ Yes |
| **Color Customization** | ✅ VWAP only | ✅ Full (VWAP + bands) |
| **Line Width Control** | ✅ VWAP only | ✅ Full (VWAP + bands) |
| **Number of Plots** | 1 (VWAP) | 9 (VWAP + 8 bands) |
| **Code Size** | 289 lines | 771 lines |
| **License Required** | ❌ None (FREE) | ✅ Required |
| **Automatic Updates** | ✅ Yes | ✅ Yes |

---

## 🚀 Quick Start

### Choose Your Version

#### 🆓 **Lite (FREE)** - Perfect if you need:
- Simple VWAP line visualization
- Session-based resets only
- Basic color/width customization
- Zero cost, no license required
- Lightweight and fast

👉 **[Download Lite Version](https://github.com/badbuddhatrades/BadBuddhaVWAP/raw/refs/heads/main/BadBuddhaVWAP_Lite.zip)**

#### 💎 **Pro (Licensed)** - Perfect if you need:
- Standard deviation bands (4 levels)
- Multiple reset periods (Daily/Weekly/Monthly)
- Professional SharpDX rendering with fills
- Full visual customization
- Institutional-grade analysis

👉 **[Get Pro License](https://badbuddhacustoms.com/vwap-pro)**

---

## 📥 Installation

### Lite Version
1. Download `BadBuddhaVWAP_Lite.zip`
2. Open Tools -> Import -> NinjaScript Addon... -> find zip file, click ok.
3. Add to chart via Indicators menu

### Pro Version
1. **Ensure you have a valid Pro license** Purchase your Pro License from: https://www.badbuddhacustoms.com/product-page/badbuddha-vwap-pro
2. Download `BadBuddhaVWAP_Pro.zip`
3 . Open Tools -> Import -> NinjaScript Addon... -> find zip file, click ok.
4. Add to chart via Indicators menu
5. Message support@badbuddhacustoms.com with the email address associated with your NinjaTrader account.

---

## 🎯 Key Features

### 🆓 Lite Features

**VWAP Calculation**
- Volume-weighted typical price: `(High + Low + Close) / 3`
- Session-based automatic resets
- Real-time updates on bar close

**Visual Settings**
- Customizable VWAP line color (default: Purple)
- Adjustable line width (1-10 pixels)

**Updates**
- Automatic update checking (daily)
- Popup notifications with changelog

**Use Cases**
- Day trading fair value identification
- Dynamic support/resistance levels
- Mean reversion trading
- Institutional level monitoring

---

### 💎 Pro Features

**Advanced VWAP Calculation**
- Full variance tracking for StdDev bands
- Multiple reset periods: Session, Daily, Weekly, Monthly
- Smart bar skipping after reset for clean gaps
- Minimum bar requirements (3 for VWAP, 5 for bands)

**Standard Deviation Bands**
- **0.5σ**: Tight inner bands for precise entries
- **1.0σ**: 68% confidence intervals (most common)
- **1.5σ**: Extended volatility zones
- **2.0σ**: 95% confidence extremes (default ON)
- Toggle each level independently
- Upper and lower bands for each level

**Professional Rendering**
- SharpDX hardware-accelerated graphics
- Translucent shaded fills between bands
- Configurable opacity (0-100%)
- Automatic segment detection for gaps
- Efficient PathGeometry rendering

**Full Visual Customization**
- VWAP line: color + width (1-10 pixels)
- Band lines: color + width (1-5 pixels)
- Band fills: separate color + opacity
- All 9 plots independently styled

**Use Cases**
- Professional day trading with StdDev zones
- Mean reversion strategies (1σ, 2σ)
- Multi-timeframe analysis (Daily/Weekly/Monthly)
- Options trading with volatility bands
- Algorithmic trading with programmatic access
- Probability analysis (68% / 95% confidence)

---

### Pro Version

**Day Trading Setup**
- Reset Period: Session or Daily
- Bands: Enable 1.0σ and 2.0σ
- Opacity: 10-20% for subtle fills
- Colors: High contrast for visibility

**Swing Trading Setup**
- Reset Period: Weekly or Monthly
- Bands: Enable 1.5σ and 2.0σ
- Opacity: 15-25% for visibility
- Line Width: 3-4 for clarity

**Scalping Setup**
- Reset Period: Session
- Bands: Enable 0.5σ and 1.0σ
- Opacity: 5-10% (light fills)
- Focus: Quick mean reversion to VWAP

---

## 🔧 Strategy Development

### Lite Version - Programmatic Access
```csharp
// Access VWAP value
double vwap = BadBuddhaVWAP_Lite()[0];

// Or via property
double vwap = BadBuddhaVWAP_Lite().VWAP[0];
```

### Pro Version - Programmatic Access
```csharp
// Access VWAP
double vwap = BadBuddhaVWAP_Pro().VWAP[0];

// Access bands
double upper2 = BadBuddhaVWAP_Pro().Upper2[0];  // +2.0σ
double lower2 = BadBuddhaVWAP_Pro().Lower2[0];  // -2.0σ
double upper1 = BadBuddhaVWAP_Pro().Upper1[0];  // +1.0σ
double lower1 = BadBuddhaVWAP_Pro().Lower1[0];  // -1.0σ

// Check if price is at extreme
if (Close[0] > upper2)
{
    // Price at 2σ extreme (95% confidence)
    // Consider mean reversion short
}
```

---

## 📊 Trading Applications Examples

### Mean Reversion (Pro)
- Price touches 2σ band → Expect reversion to VWAP
- 95% of price action occurs within ±2σ
- Strong probability-based entries

### Trend Following (Both)
- Price above VWAP → Bullish bias
- Price below VWAP → Bearish bias
- VWAP acts as dynamic support/resistance

### Institutional Trading (Both)
- VWAP is the benchmark for large orders
- Institutions aim to execute near VWAP
- Monitor price relative to VWAP for order flow

### Options Trading (Pro)
- Standard deviation bands = implied volatility zones
- Use 2σ for high-probability support/resistance
- Match option strategies to volatility zones

---

## 🔄 Reset Periods (Pro Only)

| Period | Reset Timing | Best For |
|--------|-------------|----------|
| **Session** | Trading session boundaries | Traditional VWAP, day trading |
| **Daily** | Calendar day changes (midnight) | 24-hour traders, futures |
| **Weekly** | Monday (week start) | Swing trading, position sizing |
| **Monthly** | First day of month | Long-term analysis, trends |


---

## 💡 Version Information

- **Current Version**: 2.0.0
- **Release Date**: October 31, 2025
- **NinjaTrader**: 8.0.0.0+
- **Framework**: .NET 4.8
- **Author**: BadBuddha Customs LLC

---

## 🔗 Links

- **Website**: [https://badbuddhacustoms.com](https://badbuddhacustoms.com)
- **Support**: support@badbuddhacustoms.com

---

## 📝 License

- **Lite**: Free for all users, no license required
- **Pro**: Requires NinjaTrader Vendor License - contact vendor for licensing

---

## ❓ FAQ

**Q: Can I use Lite for free forever?**
A: Yes! Lite is 100% free with no time limits or restrictions.

**Q: What's the difference between Lite and Pro?**
A: Pro adds standard deviation bands, multiple reset periods, SharpDX rendering, and full customization. See comparison table above.

**Q: Can I upgrade from Lite to Pro later?**
A: Yes! Simply purchase Pro license, download Pro version, and remove Lit and install Pro.

**Q: Do both versions receive updates?**
A: Yes, both have automatic update checking built-in.

**Q: Can I use these in automated strategies?**
A: Yes! Both versions support programmatic access for strategy development.

**Q: How do I know which version to choose?**
A: Start with Lite if you only need basic VWAP. Upgrade to Pro if you need bands and advanced features.

---

## 🎓 Support

For questions, issues, or feature requests:
- Email: support@badbuddhacustoms.com
- Website: https://badbuddhacustoms.com


---

## 🙏 Credits

Developed by **BadBuddha Customs LLC**

Special thanks to the NinjaTrader community for feedback and testing.

---

**Choose your version and start trading with professional VWAP analysis today!** 🚀
