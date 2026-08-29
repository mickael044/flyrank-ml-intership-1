# Plain-English Explainer: Dynamic Portfolio Feature & Data Flow

## 1. Selected Dynamic Feature
An automated **Interactive Contact / Message Capture Form** integrated directly into the portfolio site, backed by a serverless form handler (Formspree / Netlify Forms free tier).

---

## 2. Technical Explanation in Plain Words

### **What is a Backend?**
The frontend (HTML/CSS) is just the visible "storefront" on the user's browser. It cannot send emails or process records directly due to browser security restrictions. The **backend** is the hidden engine running on a server that receives incoming requests, processes logic, validates security rules, and performs actions like sending emails or storing database entries.

### **How the Data Flows (End-to-End Steps)**
1. **User Action:** The visitor types their name, email, and message into the HTML input fields on the page and clicks **Submit**.
2. **HTTP POST Payload:** The browser package this input into a secure `POST` request payload and sends it across the web to the backend endpoint URL.
3. **Backend Processing:** The serverless backend API catches the payload, parses the text fields, applies spam filtering, and routes the message payload directly to my verified inbox (`m.hasanov@ufaz.az`).
4. **User Feedback loop:** The backend returns an HTTP `200 OK` response code, triggering a user success confirmation notice on the frontend screen without reloading the page.

---

## 3. Verification & Live Test Evidence
- **Trigger Test:** Submitted a test message containing `"FlyRank Week 6 Real Test Delivery"`.
- **Outcome:** Received the confirmation email payload instantly in the inbox with full sender metadata attached, confirming end-to-end functionality on a zero-cost tier.
