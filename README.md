<p align="center">
  <img src="./assets/hero.svg" alt="Animated Mosesnetto workflow: learn, build, deploy, improve" width="100%" />
</p>

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.11%2B-3776ab?logo=python&logoColor=white" />
  <img alt="Raspberry Pi" src="https://img.shields.io/badge/Raspberry%20Pi-5%204GB-C51A4A?logo=raspberrypi&logoColor=white" />
  <img alt="AWS IoT" src="https://img.shields.io/badge/AWS%20IoT-232f3f?logo=amazonaws&logoColor=white" />
  <img alt="MQTT" src="https://img.shields.io/badge/MQTT-662D91?logo=mqtt&logoColor=white" />
  <img alt="Tailscale" src="https://img.shields.io/badge/Tailscale-242424?logo=tailscale&logoColor=white" />
  <img alt="GitHub Actions" src="https://img.shields.io/badge/CI-GitHub%20Actions-2088FF?logo=githubactions&logoColor=white" />
</p>

<p align="center">
  <strong>Learn · Build · Deploy · Improve</strong><br />
  <span style="color:#94a3b8">Turning ideas into practical, reliable systems through continuous learning and iteration.</span>
</p>

---

## My workflow

I work iteratively:

```text
LEARN  →  BUILD  →  DEPLOY  →  IMPROVE
```

I learn from problems, build small useful systems, put them into real
environments, and improve them through feedback. Technology changes; the
workflow stays consistent.

## Selected work

These are examples of projects built through the workflow—not the entire
scope of my work.

### Modbus AWS Logger — private preview

A focused **Modbus TCP → AWS IoT Core** bridge written in Python.

**Implemented:**

- Persistent Modbus TCP holding-register scanning
- AWS IoT MQTT/TLS publishing with QoS 1
- Environment-based configuration with no credentials in source control
- PLC and MQTT reconnect handling
- Offline `--check-config` and safe `--demo` modes
- Optional SMTP daily operational summaries with duplicate-send protection
- Unit tests, dependency checks, secret-pattern checks, and GitHub Actions CI
- Deployment documentation for a Raspberry Pi 5 edge host

[Open the private project repository](https://github.com/mosesnetto/modbus-aws-logger) · **private preview**

### Reference edge deployment

The companion deployment pattern uses a **Raspberry Pi 5 with 4 GB RAM** as the
site edge host:

- **Tailscale VPN** connects multiple authorized devices through a private tailnet.
- **Flask UI/API** provides a browser or API interface on the local network.
- **xrdp** provides open-source remote desktop access over TCP/3389.
- **Modbus AWS Logger** reads the PLC and publishes telemetry to AWS IoT.
- AWS IoT MQTT/TLS remains a separate, authenticated cloud connection.

The Flask application and operating-system services are documented as a
companion deployment pattern; they are not automatically provisioned by the
logger repository.

<p align="center">
  <img src="./assets/edge-flow.svg" alt="Animated Raspberry Pi 5, Tailscale, Flask, xrdp, PLC, and AWS IoT architecture" width="100%" />
</p>

---

## Engineering principles

<table>
  <tr>
    <td width="33%" align="center">
      <strong>🔐 Secrets stay out of Git</strong><br />
      <span style="color:#64748b">Environment files, certificates, private keys, logs, and runtime state stay local.</span>
    </td>
    <td width="33%" align="center">
      <strong>🧪 Offline validation first</strong><br />
      <span style="color:#64748b">Demo and configuration checks make it possible to verify behavior before touching a PLC or cloud account.</span>
    </td>
    <td width="33%" align="center">
      <strong>🔒 Least privilege by design</strong><br />
      <span style="color:#64748b">Tailscale access is restricted by device and port; AWS IoT access is restricted by certificate and topic policy.</span>
    </td>
  </tr>
  <tr>
    <td align="center">
      <strong>📡 Useful telemetry</strong><br />
      <span style="color:#64748b">Structured JSON payloads preserve operational context for later analysis.</span>
    </td>
    <td align="center">
      <strong>🧱 Small, testable pieces</strong><br />
      <span style="color:#64748b">Clear modules, repeatable checks, and honest documentation over unsupported claims.</span>
    </td>
    <td align="center">
      <strong>🛠️ operable systems</strong><br />
      <span style="color:#64748b">Reconnects, summaries, CI, and deployment notes are part of the product—not afterthoughts.</span>
    </td>
  </tr>
</table>

---

## What we can implement next

These are concrete next steps, not claims about current functionality:

- [ ] A secure Flask control plane with authentication, role-based access, and read-only telemetry views
- [ ] A Modbus simulator for safe development and commissioning
- [ ] Health/readiness status and connection/publish metrics
- [ ] Payload schema versioning and migration policy
- [ ] Docker, systemd, and Windows service deployment profiles
- [ ] Tailscale policy templates for Pi, Flask, xrdp, and PLC subnet access
- [ ] Alert policies for stale telemetry, repeated Modbus failures, and broker outages
- [ ] Public documentation and a customer commissioning guide after the security and license review

---

## Current stack

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3.11%2B-3776ab?logo=python&logoColor=white" />
  <img alt="Modbus TCP" src="https://img.shields.io/badge/Modbus%20TCP-502-10B981?logo=modbus&logoColor=white" />
  <img alt="MQTT" src="https://img.shields.io/badge/MQTT-3F51B5?logo=mqtt&logoColor=white" />
  <img alt="AWS IoT Core" src="https://img.shields.io/badge/AWS%20IoT%20Core-232f3f?logo=amazonaws&logoColor=white" />
  <img alt="Flask" src="https://img.shields.io/badge/Flask-000000?logo=flask&logoColor=white" />
  <img alt="xrdp" src="https://img.shields.io/badge/xrdp-0F766E?logo=github&logoColor=white" />
  <img alt="Tailscale" src="https://img.shields.io/badge/Tailscale-242424?logo=tailscale&logoColor=white" />
  <img alt="Raspberry Pi" src="https://img.shields.io/badge/Raspberry%20Pi-5-C51A4A?logo=raspberrypi&logoColor=white" />
</p>

---

## More public work

### Career Guidance Chatbot

[ChatBot-For-Carrier-Guidance](https://github.com/mosesnetto/ChatBot-For-Carrier-Guidance) ·
Python · PyTorch · NLTK · Flask

An offline AI career-guidance chatbot with intent classification, confidence
gating, a web chat UI, a terminal interface, reproducible training, tests, and
CI.

### MCC Machine Shift Monitor

[machine-monitor](https://github.com/mosesnetto/machine-monitor) ·
Python · Raspberry Pi 5 · Telegram · 4G/A7670E

A Raspberry Pi 5 machine-shift monitor with downtime alerts, shift-aware
reports, offline text-to-speech, and optional real phone-call notifications.

---

## GitHub

<p align="center">
  <a href="https://github.com/mosesnetto">
    <img alt="Mosesnetto GitHub profile" src="https://img.shields.io/badge/GitHub-mosesnetto-24292f?logo=github&logoColor=white" />
  </a>
</p>

<p align="center" style="color:#64748b">
  Building secure industrial telemetry from the edge to the cloud.
</p>
