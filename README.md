# 🚀 Raspberry Pi Self-Hosted GitHub Actions Runner

[![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python&logoColor=white)](https://www.python.org/)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-Running-success?logo=githubactions&logoColor=white)](https://github.com/features/actions)
[![Raspberry Pi](https://img.shields.io/badge/Running%20on-Raspberry%20Pi%205-red?logo=raspberrypi&logoColor=white)](https://www.raspberrypi.com/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A simple yet powerful setup to run **GitHub Actions** on your own **Raspberry Pi 5 (aarch64)** as a self-hosted runner.  
Perfect for CI/CD pipelines when you want control, speed, and fun with ARM-based hardware.

---

## 📂 Project Structure
```
|
+-- .github/
|   +-- workflows/
|       +-- ci.yml              # GitHub Actions workflow definition
|
+-- requirements.txt            # Python dependencies
+-- your_script.py              # Main Python script
+-- README.md                   # Project documentation
```


---

## ⚡ Features

✅ Self-hosted GitHub Actions runner on Raspberry Pi 5  
✅ Runs Python scripts automatically on code push  
✅ ARM64-compatible  
✅ Lightweight & low power consumption  
✅ Kubernetes-friendly setup  

---

## 🛠️ Setup Instructions

### 1️⃣ Clone the repository
```
git clone https://github.com/your-username/your-repo.git
cd your-repo
```
2️⃣ Install dependencies
```
pip install -r requirements.txt
```

3️⃣ Configure GitHub Actions runner on Raspberry Pi
Follow the official guide:
Self-Hosted Runners - GitHub Docs

Example setup:

```
mkdir actions-runner && cd actions-runner
curl -o actions-runner-linux-arm64-2.317.0.tar.gz -L https://github.com/actions/runner/releases/download/v2.317.0/actions-runner-linux-arm64-2.317.0.tar.gz
tar xzf ./actions-runner-linux-arm64-2.317.0.tar.gz
./config.sh --url https://github.com/your-username/your-repo --token YOUR_RUNNER_TOKEN
sudo ./svc.sh install
sudo ./svc.sh start
```

🧪 Test Your Setup
Push any changes to your repo:

```
git add .
git commit -m "Test pipeline"
git push
```

GitHub Actions will trigger the self-hosted runner on your Pi.

📌 Notes

  1. Make sure your Raspberry Pi 5 is always on and connected to the internet.

  2. The runner service starts automatically on boot after sudo ./svc.sh install.

  3. Works seamlessly with Kubernetes deployments.


📄 License

This project is licensed under the MIT License.

