# Site Hardening & Edge-Case Stress Test Log (Break Your Own Site)

## 1. Edge-Case Stress Testing ("Try to Break It")

| Test Scenario | Action Taken | Expected vs Actual Behavior | Triage Category |
| :--- | :--- | :--- | :--- |
| **Empty Form Submission** | Clicked submit on contact form without filling input fields. | **Before:** Sent blank payload to server. <br>**Fix:** Added HTML5 `required` attributes and client-side email format validation. | **Fix-Now** |
| **Double Click / Spam Submit** | Rapidly clicked the submit button 5 times within 1 second. | **Before:** Triggered 5 duplicate requests. <br>**Fix:** Added JS submit button disabling on first click with spinner state. | **Fix-Now** |
| **Long Text Input Injection** | Inputted a 10,000-character test string with special characters (`<script>`, `''`). | Form handled payload gracefully; input string auto-escaped by backend handler. | **Verified Safe** |
| **Slow Network / Offline Test** | Throttled network speed to 3G and disabled connection mid-request. | **Behavior:** Takes ~8 seconds before timeout; shows generic alert without custom retry screen. | **Known Limitation** |

---

## 2. SEO, Meta Tags & Speed Check

### **Meta Tags Added**
```html
<title>Mikayil Hasanov | AI & Machine Learning Engineer Portfolio</title>
<meta name="description" content="Portfolio of Mikayil Hasanov - AI Engineering intern showcasing production-grade ML workflows, local agent tools, and applied AI systems.">
<meta property="og:title" content="Mikayil Hasanov | AI & ML Engineering Portfolio">
<meta property="og:description" content="Interactive project demos, technical specs, and AI agent architectures.">
<meta property="og:type" content="website">
