# Python Flask Greetings App

A minimal Flask-based web application that exposes a simple API endpoint returning a greeting message.

---

## 📌 Features

* Lightweight Flask server
* Configurable port via CLI argument or environment variable
* JSON API response
* Works with PM2 process manager
* Uses isolated Python virtual environment (recommended)

---

## 🧰 Requirements

* Python 3.X+
* pip (via Python)
* Node.js + PM2 (optional, for process management)

---

## 📦 Installation

### 1. Clone or download the project

```bash
git clone <your-repo-url>
cd python-greetings
```

---

### 2. Create a virtual environment (IMPORTANT)

```bash
python3 -m venv venv
```

---

### 3. Activate the virtual environment

* **macOS / Linux:**

```bash
source venv/bin/activate
```

* **Windows (Command Prompt):**

```bash
venv\Scripts\activate
```

* **Windows (PowerShell):**

```bash
venv\Scripts\Activate.ps1
```

---

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

If `pip` doesn’t work:

```bash
python3 -m pip install -r requirements.txt
```

---

## ▶️ Running Locally

```bash
python app.py
```

App will start on:

```
http://localhost:3000
```

---

### 🔧 Custom Port

#### CLI argument:

```bash
python app.py --port 5000
```

#### Environment variable:

* macOS/Linux:

```bash
export PORT=5000
```

* Windows CMD:

```bash
set PORT=5000
```

* PowerShell:

```bash
$env:PORT=5000
```

---

## 🌐 API Endpoint

### GET `/greetings`

**Response:**

```json
{
  "greeting": "Hello from Python App!"
}
```

Test:

```bash
curl http://localhost:3000/greetings
```

---

## ⚙️ Running with PM2

⚠️ **Important:** PM2 must use your virtual environment, otherwise Flask won’t be found.

---

### 1. Install PM2

```bash
npm install -g pm2
```

---

### 2. Start the app (correct way)

```bash
pm2 start app.py --name python-greetings --interpreter ./venv/bin/python
```

---

### 3. Pass arguments (optional)

```bash
pm2 start app.py --name python-greetings --interpreter ./venv/bin/python -- --port 4000
```

---

### 4. PM2 Commands

```bash
pm2 list
pm2 logs
pm2 restart python-greetings
pm2 stop python-greetings
pm2 delete python-greetings
```


---

## 🖥️ OS-Specific Notes

### macOS / Linux

* Use `python3` instead of `python` if needed
* Always use a virtual environment (required with Homebrew Python)
* PM2 interpreter path:

  ```bash
  ./venv/bin/python
  ```

---

### Windows

* Use `python` (usually mapped to Python 3)

* Virtual environment path:

  ```bash
  venv\Scripts\python.exe
  ```

* PM2 example:

  ```bash
  pm2 start app.py --name python-greetings --interpreter venv\Scripts\python.exe
  ```

---

## ⚠️ Troubleshooting

### `ModuleNotFoundError: No module named 'flask'`

✔️ Cause: PM2 or Python is not using your virtual environment

✔️ Fix:

```bash
pm2 start app.py --interpreter ./venv/bin/python
```

---

### `externally-managed-environment` (macOS)

✔️ Cause: Homebrew Python prevents global installs

✔️ Fix: Always use virtual environment

---

### `pip: command not found`

Use:

```bash
python3 -m pip install -r requirements.txt
```

---

## ⚠️ Development Notes

* The app runs with `debug=True`
* Do NOT use this in production
* For production, consider:

  * gunicorn (Linux/macOS)
  * reverse proxy (e.g., Nginx)

---

## 📄 License

Free to use and modify.

