# Appendix: Additional Notes on Python Virtual Environment Deployment

This project involves many packages, and dependency issues have long been a persistent pain point in Python, which makes the engineering ecosystem quite fragmented.

To address this, uv provides a unified entry point for virtual environment management and incorporates advanced package management practices from the Rust ecosystem. Using it can reduce the time we spend on Python engineering tasks. Below we use uv to set up the project's virtual environment.

## 1.1 uv Environment Management

### 1.1.1 Windows

**Install uv via PowerShell**

```bash
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**After installation, follow the prompt to add the environment variables.** Note that the installation path varies by user, so copy and paste the command exactly as shown in your prompt.

```bash
$env:Path = "C:\Users\michaelbradley\.local\bin;$env:Path" 
```

![Installation success prompt](./images/1_4_1.png)

**Run the uv command; if you see the following, the installation succeeded**

![uv installed successfully](./images/1_4_2.png)

### 1.1.2 Linux / macOS

**Install uv with curl**

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

If curl is unavailable, **install uv with wget**:

```bash
wget -qO- https://astral.sh/uv/install.sh | sh
```

**Run the uv command; if you see the following, the installation succeeded**

![uv installed successfully](./images/1_4_3.png)

## 1.2 Create and Activate a Virtual Environment

### 1.2.1 Create a virtual environment

```bash
uv venv rag --python 3.12.7
```

This creates a virtual environment named `rag` using Python version 3.12.7.

On Windows, you should see output similar to:

```bash
PS C:\Users\parallel> uv venv rag --python 3.12.7
Using CPython 3.12.7
Creating virtual environment at: rag
Activate with: rag\Scripts\activate
```

On Linux / macOS, you should see:

```bash
┌──(parallel㉿pacman)-[~/Desktop]
└─$ uv venv rag -p 3.12.7
Using CPython 3.12.7
Creating virtual environment at: rag
Activate with: source rag/bin/activate
```

### 1.2.2 Activate the virtual environment

Windows:

```bash
rag\Scripts\activate
```

Linux / macOS:

```bash
source rag/bin/activate
```

