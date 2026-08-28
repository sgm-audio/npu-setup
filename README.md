# NPU setup — Qwen2.5-Coder-7B (Lemonade Desktop)

Use the **official Lemonade Desktop app** you already installed. No custom web app, no CLI wrapper scripts.

## Machine

- ASUS Vivobook 16 / **Ryzen AI 7 350** (XDNA2) + **Radeon 860M**
- Lemonade Desktop already present (`%LOCALAPPDATA%\lemonade_server`)
- **Vitis AI not required** for catalog Hybrid/NPU models

## Desktop app steps

1. Open **Lemonade** (desktop app), not a browser project in this repo.
2. **Backends Manager** → install **Ryzen AI LLM** / NPU (`ryzenai-llm`) if it isn’t installed yet.
3. Set NPU turbo (Admin terminal once):

   ```powershell
   cd C:\Windows\System32\AMD
   .\xrt-smi configure --pmode turbo
   ```

4. In the app model list, download/run **`Qwen2.5-Coder-7B-Instruct-Hybrid`** (NPU prefill + iGPU decode).
   - Fallback: **`Qwen2.5-Coder-7B-Instruct-NPU`**

## Already done on this laptop

- `ryzenai-llm:npu` **v1.7.0** installed
- NPU set to **turbo**
- **Qwen2.5-Coder-7B-Instruct-Hybrid** downloaded and verified loadable

Open the desktop app and select that model to chat. Done.
