# 🏝️ Caye

> **Zero-refresh hot island replacement for live web production pages.**  
> *Pure left-hand elegance (`c-a-y-e`).*

Caye allows developers to hot-swap individual UI components (Islands) directly on live production web pages in real-time, without refreshing the page, without touching production deploys, and without disrupting user state or session cookies.

---

## ✨ Features

- **Zero-Refresh Hot Swap**: Save a file locally, and see the component update on your live production site in ~200ms.
- **Pure Left-Hand Typing (`c-a-y-e`)**: Zero awkward right-hand reach (`u, i, o, p, k, l` free).
- **Cryptographic Security**: Ed25519 asymmetric signature verification via WebCrypto prevents any unauthorized code injection.
- **Shared Module Direct Pipeline**: Shares host page modules (`react`, `react-dom`, etc.) to eliminate duplicate library baggage and avoid hook breakdown.
- **Selective Fingerprint Rebuild**: SHA-256 island level diffing — only rebuilds and pushes what changed.
- **Tailscale & Cloudflare Ready**: Designed for secure internal access over tailnets or tunnels.

---

## 🚀 Quick Start

### 1. In your App (Client)

```tsx
import { CayeProvider, Island } from "caye";

export function Header() {
  return (
    <nav>
      <Island name="header.brand" fallback={<BrandName />}>
        <BrandName />
      </Island>
    </nav>
  );
}
```

### 2. Start Dev Server (Local Mac/PC)

```bash
bun x caye dev --port 5196 --tailnet /my-islands
```

### 3. Authorize via Live View

```bash
bun x caye live on
```

Visit your production site — your live component is now hot-replaced!

---

## 📜 License

MIT © [SnoMiao / SNO LAB](https://github.com/snolab)
