# Personal Site Architecture & DNS Walkthrough (PF-01)

## 1. Overview & Deployed Site
- **Live Site URL:** `https://mickael044.github.io/flyrank-ml-intership-1/`
- **Hosted Content:** Personal portfolio featuring background overview, GitHub, LinkedIn, CV links, and integrated FlyRank completion badge.

---

## 2. DNS Infrastructure Walkthrough

### **A Record vs. CNAME Record**
- **A Record (Address Record):** Maps a human-readable domain name directly to a specific numerical IPv4 address (e.g., `example.com` ➔ `185.199.108.153`). Used for apex/root domains.
- **CNAME Record (Canonical Name):** Maps an alias domain to another standard domain name (e.g., `www.example.com` ➔ `mickael044.github.io`). It lets GitHub/hosting providers manage IP address changes automatically behind the scenes.

### **How DNS Resolution Works (Step-by-Step)**
1. **Request:** User types a custom domain URL into the browser.
2. **Recursive Lookup:** The browser queries the ISP's DNS resolver to locate the corresponding IP address.
3. **CNAME Mapping:** If a CNAME record exists, the resolver redirects to the hosting target (`username.github.io`).
4. **IP Resolution:** The DNS server resolves `username.github.io` to GitHub's routing IP addresses.
5. **TLS/HTTPS Handshake:** GitHub Pages handles free automatic SSL/TLS certificate provisioning via Let's Encrypt, establishing an encrypted HTTPS connection.

---

## 3. FlyRank Badge Integration
```html
<a href="[https://internship.flyrank.ai](https://internship.flyrank.ai)"><img src="[https://img.shields.io/badge/FlyRank-AI%20Engineering-green](https://img.shields.io/badge/FlyRank-AI%20Engineering-green)" alt="FlyRank Badge"></a>
