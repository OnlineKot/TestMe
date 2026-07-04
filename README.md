# TestMe ⚡ — All-in-One Speed & Performance Test Suite

A single-page web app that tests five things, entirely in your browser:

| Test | What it measures | How |
|------|------------------|-----|
| 🌐 **WiFi / Internet Speed** | Ping, jitter, download & upload (Mbps) | Transfers data to/from Cloudflare's speed-test servers |
| 🖱️ **CPS Test** | Clicks per second (1s / 5s / 10s / 30s modes) | Click counter with a high-precision timer |
| 🎮 **GPU Benchmark** | Average FPS and rendering score under increasing load | WebGL renders up to 20,000 animated triangles |
| 🧠 **CPU Benchmark** | Single-core & multi-core scores (M ops/sec) | Math, prime-sieve and hashing workloads; multi-core via Web Workers |
| ⌨️ **Typing Test** | WPM (words per minute) and accuracy | 60-second typing test with live character highlighting |

## How to run

No build step, no dependencies — it's one HTML file.

```bash
# Option 1: just open it
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux

# Option 2: serve it locally
python3 -m http.server 8000
# then visit http://localhost:8000
```

> The WiFi speed test requires an internet connection (it uses `speed.cloudflare.com`).
> Everything else works fully offline.

## Notes

- No data is stored or sent anywhere, except the traffic generated during the speed test itself.
- CPU/GPU scores are browser-dependent — compare results only within the same browser.
- The GPU test requires WebGL support (available in all modern browsers).
