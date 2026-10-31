# NPU setup notes: Qwen2.5-Coder-7B on Lemonade Desktop

My notes for running Qwen2.5-Coder-7B on the NPU of my laptop with AMD's Lemonade Desktop app. There's no code here, just the steps that worked for me.

## Machine

- ASUS Vivobook 16, Ryzen AI 7 350 (XDNA2 NPU) with Radeon 860M iGPU, Windows
- Lemonade Desktop installed (default location `%LOCALAPPDATA%\lemonade_server`)
- Vitis AI isn't needed for the catalog Hybrid/NPU models

## Steps

1. Open the Lemonade desktop app.
2. In Backends Manager, install the Ryzen AI LLM / NPU backend (`ryzenai-llm`) if it isn't there yet.
3. Set the NPU to turbo once, from an admin terminal:

   ```powershell
   cd C:\Windows\System32\AMD
   .\xrt-smi configure --pmode turbo
   ```

4. In the model list, download and run `Qwen2.5-Coder-7B-Instruct-Hybrid` (prefill on the NPU, decode on the iGPU). If that doesn't load, `Qwen2.5-Coder-7B-Instruct-NPU` is the NPU-only fallback.

## What I ran on my machine

- `ryzenai-llm:npu` v1.7.0
- NPU power mode set to turbo
- `Qwen2.5-Coder-7B-Instruct-Hybrid` downloaded and loaded

I didn't measure tokens/s, so there are no speed numbers here. Other Ryzen AI chips or backend versions may behave differently.

## License

MIT. See [LICENSE](LICENSE).
