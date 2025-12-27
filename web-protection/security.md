## 🔒 Domain Blocklists & Threat Prevention

Munetios Web Protection includes built-in domain blocklists to **prevent the browser from loading known malicious or high-risk third-party resources**.

### 🚫 Malicious Domains
The project maintains a list of domains associated with:
- Malware distribution
- Scam or phishing campaigns
- Cryptomining scripts
- Fake CDNs and compromised infrastructure
- Known supply-chain attacks

When a resource (such as an iframe or embedded URL) matches a blocked domain, it is **prevented from loading** or **removed from the page** before execution.

### 🛑 Tracking & Analytics Domains (Strict Mode)
In `mode: "strict"`, additional domains commonly used for:
- Cross-site tracking
- Behavioral analytics
- Advertising networks
- Session replay and monitoring tools

are blocked to reduce tracking, fingerprinting, and privacy exposure.

### 🧠 How Blocking Works
- Domain matching is based on **exact hostname comparison** and **subdomain matching**
- No wildcard or pattern-based overblocking is used
- Blocking is performed **locally in the browser**
- No requests are sent to external services for verification

### ⚠️ Important Notes
- Blocklists are **preventive**, not antivirus software
- They reduce exposure but cannot guarantee complete protection
- Users and site owners may override or extend blocklists if needed

### 🧩 Customization
Developers may customize behavior using:

```js
window.MunetiosProtection = {
  mode: "strict" | "warn" | "off"
};
