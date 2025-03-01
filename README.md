# ollama-webui-https

This Docker Compose setup provides an isolated application with [`Ollama`](https://github.com/ollama/ollama), [`Open-WebUI`](https://github.com/open-webui/open-webui), and enables `Open-WebUI` to use **SSL (HTTPS)** via `Nginx`, as `Open-WebUI` does not support **SSL** natively.

---

## Prerequisites
Ensure you have the following installed:

  - [`Docker`](https://docs.docker.com/get-docker/)
  - [`Docker Compose`](https://docs.docker.com/compose/install/)

---

## 📦 Installation

### 1. Clone the Repository
```sh
git clone https://github.com/ilolm/ollama-webui-https.git
cd ollama-webui-https
```

### 2. Configure SSL Certificates
Place your SSL certificate (`fullchain.pem`) and private key (`privkey.pem`) inside the `ssl/` directory.

### 3. Update Nginx Configuration (Domain)
Before running the application, you **must** update your domain in the Nginx configuration:
  1. Open the Nginx configuration file:  
   ```sh
   nano default.conf
   ```
  2. Replace **`example.com`** with your actual domain in the `server` blocks for ports **80** and **443**.    _(There are **only two `example.com` entities**)_
  3. Save the file.

### 4. Start the Stack
```sh
docker compose up -d
```

Your WebUI will be available at **https://your-domain.com** or **https://localhost** 🎉

---

## 🛠 Updating Containers
```sh
docker compose pull
docker compose up -d --force-recreate
```

---

## 📜 License
This project is licensed under the MIT License.

---

## 🤝 Contributing
Feel free to open issues or submit pull requests to improve the project.

---
Made with ❤️ by [Ilolm](https://github.com/ilolm)
