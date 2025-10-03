# Taskara

[![Build Status](https://img.shields.io/github/actions/workflow/status/your-org/taskara/maven.yml?branch=main\&logo=github\&style=flat-square)](https://github.com/your-org/taskara/actions)
[![License](https://img.shields.io/github/license/your-org/taskara?style=flat-square)](LICENSE)
[![Maven Central](https://img.shields.io/maven-central/v/your.group.id/taskara?style=flat-square)](https://search.maven.org/search?q=g:your.group.id%20AND%20a:taskara)
[![Docker Pulls](https://img.shields.io/docker/pulls/your-org/taskara?style=flat-square)](https://hub.docker.com/r/your-org/taskara)

Taskara is a simple, modern, and fast tool for planning, tracking, and collaborating on work.
It provides clean boards, flexible issue tracking, real-time updates, configurable time tracking, and secure access over SSL/TLS — helping teams stay focused and organized without unnecessary complexity.

Taskara is built using a modular **OSGi architecture powered by Apache Felix**, allowing features to be added or replaced as independent bundles.
It can be installed as a self-contained application using **jlink + jpackage**, or run as a **Podman container** for server deployment.

---

## ✨ Key Features

* **Simple & Intuitive** — Create projects and start tracking tasks in minutes.
* **Fast & Modular** — Powered by Apache Felix OSGi; features delivered as bundles.
* **Boards & Issues** — Kanban boards, backlogs, and sprints.
* **Configurable Time Tracking** — Round time logs to configurable windows (default 15 minutes).
* **Internal Data Storage (SQLite)** — Lightweight, self-contained persistence.
* **SSL/TLS Support** — Secure HTTPS access.
* **Real-time Updates** — Live updates across the team.
* **Search & Filters** — Quickly find tasks and issues.
* **Collaboration** — Assign, comment, tag, and track progress with your team.

---

## 🚀 Getting Started

### Option 1: Self-Contained Application (jlink + jpackage)

1. Install Taskara using the platform-specific package:

   * Windows: `.msi` or `.exe`
   * macOS: `.dmg` or `.pkg`
   * Linux: `.deb` or `.rpm`
   * Bundled with a custom launcher and required JDK.

2. Launch the application:

```bash
./taskara/bin/taskara
```

3. Access the Web UI (HTTPS):

```
https://localhost:8080
```

4. Configure SSL certificates in `conf/taskara.cfg`:

```properties
server.ssl.enabled=true
server.ssl.key-store=conf/keystore.jks
server.ssl.key-store-password=yourpassword
server.ssl.key-alias=taskara
```

---

### Option 2: Podman Container

1. Pull the Taskara image:

```bash
podman pull your-org/taskara:latest
```

2. Run the container with SSL certificate mounted:

```bash
podman run -d -p 8080:8080 --name taskara \
    -v taskara-data:/opt/taskara/data \
    -v /host/certs:/opt/taskara/certs:ro \
    -e TASKARA_SSL_KEYSTORE=/opt/taskara/certs/keystore.jks \
    -e TASKARA_SSL_PASSWORD=yourpassword \
    your-org/taskara:latest
```

3. Access the Web UI (HTTPS):

```
https://localhost:8080
```

---

### Configure Time Tracking (Optional)

* Default rounding window: 15 minutes.
* Adjust in `conf/taskara.cfg` or via environment variables:

```properties
TASKARA_TIME_TRACKING_ROUNDING_WINDOW_MINUTES=10
```

---

### Create Your First Project

* Use the web wizard to create boards, add issues, and log time.

---

## 🛠️ Tech Stack

* **Language:** Java 17+
* **Build Tool:** Maven
* **Runtime:** Apache Felix (OSGi)
* **Database:** SQLite (internal, self-contained)
* **Distribution:** jlink + jpackage or Podman container
* **Frontend:** React / Tailwind
* **API Docs:** OpenAPI / Swagger
* **Security:** SSL/TLS support
* **License:** Apache License 2.0

---

## 🌐 Roadmap (Planned)

* ✅ Basic issue tracking
* ✅ Project boards
* ✅ Configurable time tracking (15-minute default)
* ✅ Internal SQLite storage
* ✅ SSL/TLS support
* ⏳ User management
* ⏳ Sprint planning
* ⏳ Integrations (GitHub / GitLab / Slack)
* ⏳ Advanced workflows
* ⏳ Pluggable bundle marketplace

---

## 📜 License

Taskara is licensed under the **Apache License, Version 2.0**.
See the `LICENSE` file for full details.

---

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Submit a pull request

Before submitting:

* Run `mvn spotless:apply` to auto-format code and add license headers.
* Ensure all tests pass with `mvn test`.

---

## 🌟 Why Taskara?

Taskara focuses on **speed, clarity, modularity, and security**, offering teams powerful issue tracking, flexible time logging, and task collaboration without clutter.
Self-contained packages, SQLite storage, container images, and SSL support make installation and deployment simple and secure.

---

## 📬 Contact

* Website: [https://...](https://...) (placeholder)
* Email: [support@...](mailto:support@...)
* GitHub: [https://...](https://...)
