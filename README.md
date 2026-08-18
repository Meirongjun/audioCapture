# 拾音 · 安装说明（Mac / Apple Silicon）

## 系统要求

- macOS 13.0 或更高版本
- Apple Silicon（M1 / M2 / M3 / M4）。不支持 Intel 机型
- 磁盘空间：应用约 1GB，首次转写另需下载约 250MB 模型

## 安装步骤

1. 双击打开 dmg，把「拾音」拖入 `Applications` 文件夹
2. **首次打开**：因为未做公证签名，系统会提示「无法打开，因为无法验证开发者」。任选其一：
   - 在「访达 → 应用程序」里**右键点「拾音」→ 打开 → 再点「打开」**（只需一次）
   - 或到「系统设置 → 隐私与安全性」，拉到底点「仍要打开」
   - 若提示文件「已损坏」，在终端执行：`xattr -cr /Applications/拾音.app`

## 首次使用

1. **模型下载**：第一次转写会自动从 ModelScope 下载 FunASR 模型（约 250MB），需要联网，之后离线可用
2. **系统内录（可选）**：要录电脑内部声音（如线上会议对方的声音），需安装 BlackHole 虚拟声卡：
   - 官网下载：https://existential.audio/blackhole/ （选 BlackHole 2ch，免费）
   - 或用 Homebrew：`brew install blackhole-2ch`
3. **LLM 整理（可选）**：转写后自动生成整理稿、摘要稿需要在 App 的「LLM 设置」里填入任一大模型 API Key（如 DeepSeek、通义、OpenAI 等）
4. **ffmpeg（可选）**：仅当需要转写视频文件或 m4a/mp3 时需要：`brew install ffmpeg`

## 常见问题

- **首次转写慢**：模型在下载（约 250MB），看进度输出，下载完成后速度正常
- **录音没有声音**：检查「系统设置 → 声音」里输入设备选择；录系统声音需先装 BlackHole 并在录音设置里选择
- **转写报错找不到模型**：确认网络可达 modelscope.cn 后重启 App 重试

## 卸载

把「拾音」拖入废纸篓即可；模型缓存位于 `~/.cache/modelscope`，可手动删除。
