
# 🚀 LLM + MCP Simulation – Image Detection Assignment

This project demonstrates how to use an LLM (LLaMA 3 via Ollama) to interpret a user command and orchestrate two simulated services (`ImageDB` and `YoloDetector`) using a simplified MCP-style flow.

---

## 📌 Project Goal

Take a free-text user command like:

```
detect all cars in images between 11:00 and 11:05
```

Then:
1. Use an LLM to extract structured intent (task + time range).
2. Use `ImageDB` to filter only the images taken in the requested time window.
3. Use `YoloDetector` to simulate object detection and return only images that contain **cars**.

---

## 🧠 Technologies Used

- 🧠 **LLaMA 3** via [Ollama](https://ollama.com)
- 🐍 Python 3.x
- 📁 Simulated image data
- No external API or internet connection needed ✅

---

## 🗂 Project Structure

```
project/
├── main.py               # Main orchestration script
├── parse_command.py      # Interacts with LLaMA to extract task details
├── image_db.py           # Simulated image database filtering by time
├── yolo_detector.py      # Simulated object detector (cars)
```

---

## 🚀 How to Run

### 1. Install [Ollama](https://ollama.com)

Make sure `llama3` is downloaded:

```bash
ollama run llama3
```

### 2. Clone this repo

```bash
git clone https://github.com/your-username/neuronicode-assignment.git
cd neuronicode-assignment
```

### 3. Install dependencies (Python only uses built-in modules)

```bash
pip install -r requirements.txt
# Currently empty unless you add extras
```

### 4. Run the full pipeline

```bash
python main.py
```

---

## 🧪 Example Output

```
Final images with cars in the time range:
['image_1101.jpg', 'image_1106.jpg']
```

---

## 🎯 How It Works

| Step | Component        | Description |
|------|------------------|-------------|
| 1    | `parse_command`  | Sends instruction to LLaMA via `subprocess` and parses structured JSON |
| 2    | `ImageDB`        | Filters images by HH:MM time inside filenames |
| 3    | `YoloDetector`   | Simulates car detection using preloaded labels |

---

## ✨ Bonus Question Answer

> What would change if you used an existing NIM service with built-in detection?

**Answer:**

If we used a real NIM (Neuronicode's Intelligent Module) service with integrated detection, the LLM would only need to pass the task and time, and the entire flow (time filtering + detection) would be handled inside the NIM. This reduces orchestration complexity and improves performance but limits flexibility and modular control.

---

## 📬 Contact

Created by [Your Name] for the Neuronicode LLM MCP Intern Assignment.
