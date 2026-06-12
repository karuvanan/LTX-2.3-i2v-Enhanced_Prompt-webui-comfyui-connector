# Universal i2v ComfyUI Prompt Connector

Universal i2v ComfyUI Prompt Connector is a Python-based image-to-video prompt automation tool that combines a Tkinter desktop GUI, Gradio WebUI, and ComfyUI API integration.

It helps generate structured Universal i2v prompts, recommend camera/action motion plans, send prompts and images directly into a ComfyUI workflow, queue generation, wait for completion, and download the final SaveVideo output.

---

## 中文简介

Universal i2v ComfyUI Prompt Connector 是一个基于 Python 的图生视频 Prompt 自动化工具，结合 Tkinter Py GUI、Gradio WebUI 和 ComfyUI API。

它可以：

* 上传参考图片
* 生成 Universal i2v Prompt
* 自动推荐镜头流派
* 自动生成 5 套动作方案
* 自动评分动作组合
* 一键发送到 Stability Matrix 启动的 ComfyUI
* 自动上传 input image
* 自动写入 main prompt
* 自动设置 duration
* 自动随机 seed
* 保留 workflow 原本 negative prompt
* 等待 ComfyUI 完成生成
* 自动下载最终 SaveVideo 输出

---

## Features

* Tkinter desktop GUI
* Gradio WebUI for browser and mobile usage
* Reference image input
* AI scene analysis fields
* Environment tag selection
* Lighting preset selection
* Top 5 camera shot genre recommendation
* Click-style genre selection
* Automatic generation of 5 action-camera plans
* Action compatibility scoring
* Collision checking for action combinations
* Universal i2v prompt generation
* Negative prompt generation
* Segmented prompt template generation
* One-click prompt copy
* ComfyUI API connection test
* Send prompt and image to ComfyUI queue
* Random seed control
* Duration control
* Automatic output waiting
* Final SaveVideo download
* Stability Matrix / ComfyUI compatible workflow

---

## Recommended Project Structure

```text
universal-i2v-comfyui-prompt-connector/
│
├─ Universal_i2v_Enhanced_Prompt_v11_webui_comfyui_connector_autodownload_VIDEOFIX.py
│  Main application file.
│
├─ README.md
│  Project documentation.
│
├─ requirements.txt
│  Python dependencies.
│
├─ .gitignore
│  Safe Git ignore rules.
│
├─ workflows/
│  └─ LTX_2.3_i2v_API.example.json
│     Example ComfyUI API workflow.
│
├─ examples/
│  └─ env_config.example.json
│     Optional example environment configuration.
│
├─ screenshots/
│  Safe screenshots for README.
│
├─ comfyui_downloads/
│  Runtime output downloads. Do not upload.
│
├─ hf_models/
│  Local Hugging Face cache. Do not upload.
│
└─ logs/
   Runtime logs. Do not upload.
```

---

## Requirements

Recommended system:

```text
Windows 10 / Windows 11
Python 3.10 or Python 3.11
Git for Windows
VS Code
Stability Matrix
ComfyUI
```

This project does not require:

```text
PHP
MySQL
SQLite
Composer
npm
XAMPP
```

XAMPP is not required because this is a Python + Gradio + ComfyUI API project.

---

## Python Dependencies

Create a `requirements.txt` file:

```txt
gradio
Pillow
transformers
torch
huggingface_hub
opencv-python
numpy
requests
```

Install dependencies:

```cmd
pip install -r requirements.txt
```

---

## ComfyUI / Stability Matrix Setup

Start ComfyUI through Stability Matrix.

Recommended ComfyUI launch arguments:

```cmd
--user-directory "c:\comfyui\user"  --disable-dynamic-vram --cache-none --listen 0.0.0.0
```

Default ComfyUI server URL:

```text
http://127.0.0.1:8188
```

Open this URL in a browser to confirm ComfyUI is running:

```text
http://127.0.0.1:8188
```

---

## ComfyUI API Workflow

This tool uses a ComfyUI API Format JSON workflow.

Important node IDs used by the default workflow:

```text
Input Image Node: 269
Main Prompt Node: 320:319
Duration Node: 320:301
Random Seed Nodes: 320:276, 320:277
Negative Prompt Node: 320:313
Save Video Node: 75
```

The tool modifies:

```text
input image
main prompt
duration
random seed
```

The tool does not overwrite the original negative prompt in the workflow.

If you change the original ComfyUI workflow structure, export a new API workflow from ComfyUI:

```text
ComfyUI
→ Enable Dev Mode Options
→ Save (API Format)
```

---

## Installation on Windows

### 1. Open project folder

```cmd
cd /d "D:\comfui ui and sulphur"
```

### 2. Create virtual environment

```cmd
py -m venv .venv
```

### 3. Activate virtual environment

```cmd
.venv\Scripts\activate
```

### 4. Install dependencies

```cmd
pip install -r requirements.txt
```

If `requirements.txt` is not ready yet:

```cmd
pip install gradio Pillow transformers torch huggingface_hub opencv-python numpy requests
```

### 5. Start ComfyUI

Start ComfyUI from Stability Matrix with recommended arguments:

```cmd
--user-directory "c:\comfyui\user"  --disable-dynamic-vram --cache-none --listen 0.0.0.0
```

### 6. Run the application

```cmd
py "Universal_i2v_Enhanced_Prompt_v11_webui_comfyui_connector_autodownload_VIDEOFIX.py"
```

---

## Usage Flow

```text
1. Open Stability Matrix.
2. Start ComfyUI.
3. Confirm ComfyUI is running at http://127.0.0.1:8188.
4. Run the Python app.
5. Upload a reference image.
6. Analyze scene.
7. Select recommended camera genres.
8. Generate 5 action-camera plans.
9. Select final action plan.
10. Generate Universal i2v Prompt.
11. Test ComfyUI connection.
12. Send to ComfyUI Queue.
13. Wait for generation.
14. Download final SaveVideo output.
```

---

## Runtime Output

Downloaded video outputs are saved into:

```text
comfyui_downloads/
```

This folder should not be uploaded to GitHub.

---

## Files Not Included

This repository should not include:

```text
hf_models/
AI model files
private input images
generated videos
ComfyUI output files
.env
API keys
tokens
passwords
logs
cache
temporary files
database files
customer data
financial data
```

---

## GitHub Upload

First-time upload:

```cmd
git init
```

```cmd
git branch -M main
```

```cmd
git add .
```

```cmd
git commit -m "Initial commit: Universal i2v ComfyUI prompt connector"
```

```cmd
git remote add origin https://github.com/karuvanan/universal-i2v-comfyui-prompt-connector.git
```

```cmd
git push -u origin main
```

Update later:

```cmd
git status
```

```cmd
git add .
```

```cmd
git commit -m "Update ComfyUI connector"
```

```cmd
git push
```

---

## Safety Notes

Do not upload private images, real customer data, real financial data, API keys, generated videos, or local AI model files.

If you share workflow JSON files, make sure they do not contain private file paths or private image names. Prefer uploading example workflow files only.

---

## License

Choose a license depending on your intended usage.

Common options:

```text
MIT License
Apache License 2.0
Private repository without license
```

If this is a personal or private workflow tool, keep the repository private.
