Languages: English | [中文版](README.zh-CN.md)

# ♟️ KataGo Colab Contribute (TensorRT/CUDA via auto-updating gist)

✨ Simple, copy-paste setup to contribute compute to KataGo distributed training on Google Colab. It uses an always-updating gist so you don't need to copy notebooks around.

- 📦 Gist (installer): https://gist.github.com/Carton/1da29b7f89144c7176543839ddc5f9bb
- 🧩 Optional helper extension: https://github.com/Carton/ColabRunner

## 🚀 Quick Start (Google Colab)

1. Open a new notebook in Colab: https://colab.research.google.com/
2. Switch runtime to GPU (preferably T4):
   - Menu: Runtime -> Change runtime type -> Hardware accelerator: GPU
   - Verify GPU (should show T4):

        !nvidia-smi -L

3. In the first cell, set your KataGo training credentials (and optionally threads):

        USERNAME = "your_username"   # from katagotraining.org
        PASSWD = "your_password"
        THREADS = 16                  # optional: parallel selfplay games

4. In the next cell, fetch and run the installer gist:

        !wget -O katago_dist_setup.ipy "https://gist.githubusercontent.com/Carton/1da29b7f89144c7176543839ddc5f9bb/raw/katago_dist_setup.ipy"
        %run katago_dist_setup.ipy

5. Watch the logs. The first run installs dependencies and downloads engines/models; subsequent runs are faster. To contribute more, open multiple Colab tabs and repeat.

## 🤔 Why a gist?
- ✅ Auto updates when KataGo/TensorRT/CUDA versions change; your Colab tabs stay current by re-downloading.
- ✅ Ideal for running many notebooks in parallel without manual updates.

## 💡 Tips
- 🎯 Script targets CUDA + TensorRT and is tuned for Tesla T4 on Colab.
- 🔐 Credentials are for katagotraining.org; ensure they are correct.
- 🖥️ If launched without GPU, switch runtime to GPU and rerun the two cells.

## 🧰 One-click multi-tab control (optional)
Use the Chrome extension ColabRunner to start/stop multiple Colab tabs by title keyword.

## 🔗 Links
- 📦 Gist installer: https://gist.github.com/Carton/1da29b7f89144c7176543839ddc5f9bb
- 🧩 ColabRunner extension: https://github.com/Carton/ColabRunner
