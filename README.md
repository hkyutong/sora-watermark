Sora Watermark Cleaner (SoraWm)English | 中文本项目提供了一个高效、优雅的解决方案，用于一键移除 Sora2 生成视频中的官方水印。🚀 性能与效果概览特性详情检测模型YOLOv11s（已针对最新水印优化）修复模型LAMA（基于 iopaint 实现）处理方式纯深度学习驱动，效果优异运行支持Python / Streamlit Web UI / FastAPI Server / One-Click EXE<table>  <tr>    <td width="50%">      <h3 align="center">✅ 水印移除效果</h3>      <video src="https://github.com/user-attachments/assets/8cdc075e-7d15-4d04-8fa2-53dd287e5f4c" width="100%"></video>    </td>    <td width="50%">      <h3 align="center">❌ 原始视频</h3>      <video src="https://github.com/user-attachments/assets/4f032fc7-97da-471b-9a54-9de2a434fa57" width="100%"></video>    </td>  </tr></table>✨ 核心亮点全功能支持： 完美支持视频批量处理。持续迭代： 已更新 YOLO 权重，精准识别并处理包含用户名的最新版水印。社区贡献： 标注数据集已公开，欢迎社区训练和改进检测模型。极简部署： Windows 用户可直接下载一键便携式版本，无需任何配置。🛠️ 方法原理 (Methodology)SoraWatermarkCleaner（SoraWm）由深度学习模型协同工作，实现高效的水印去除：Sora 水印检测器 (SoraWaterMarkDetector)技术栈： 基于训练的 YOLOv11s 模型。作用： 自动精确地定位视频帧中的 Sora 水印区域。水印内容清除器 (WaterMarkCleaner)技术栈： 基于 LAMA 模型的修复（Inpainting）算法。作用： 利用周围像素信息智能填充，实现无痕迹地清除水印。（致谢：LAMA 模型的实现借鉴自 IOPaint 项目。）💻 快速安装 (Installation)步骤 1：安装 FFmpeg视频处理需要 FFmpeg。请确保您的系统已安装并配置好 FFmpeg。步骤 2：安装 Python 环境依赖推荐使用 uv 工具进行依赖安装：# 自动创建并安装所有依赖到 .venv 目录
uv sync
激活环境（可选）：source .venv/bin/activate
步骤 3：模型自动下载Yolo 权重 (best.pt) 和 Lama 模型将在运行时自动下载至本地。如遇下载失败，请检查网络连接。🚀 命令行批量处理使用 cli.py 脚本对指定目录下的视频进行批量处理：python cli.py [-h] -i INPUT -o OUTPUT [-p PATTERN] [--quiet]
参数说明:-i INPUT: 输入文件夹路径。-o OUTPUT: 输出文件夹路径。-p PATTERN: 视频文件匹配模式，例如 *.mov (可选)。--quiet: 禁用 Tqdm 进度条显示 (可选)。示例:# 处理 input 文件夹中的所有 .mp4 文件
python batch_process.py -i /path/to/input -o /path/to/output
# 处理所有 mov、avi、mp4 文件
python batch_process.py -i /path/to/input -o /path/to/output --pattern "*.{mp4,mov,avi}"
💡 演示与示例脚本演示运行 example.py 进行基础功能测试：from pathlib import Path
from sorawm.core import SoraWM


if __name__ == "__main__":
    input_video_path = Path("resources/dog_vs_sam.mp4")
    output_video_path = Path("outputs/sora_watermark_removed.mp4")
    
    sora_wm = SoraWM()
    sora_wm.run(input_video_path, output_video_path)
Streamlit Web 交互界面您可以使用 streamlit 启动一个本地的交互式网页应用：streamlit run app.py
<img src="resources/app.png" alt="Streamlit 应用截图" style="zoom: 25%;" />界面特色： 支持拖动文件夹或多选文件进行批量处理。<img src="assests/streamlit_batch.png" alt="Streamlit 批量处理界面截图" style="zoom: 50%;" />📥 4. 一键便携式版本 (Windows)专为 Windows 用户设计，无需安装 Python 环境，下载解压即可运行。平台链接提取码备注Google Drive点击下载--百度网盘https://pan.baidu.com/s/1onMom81mvw2c6PFkCuYzdg?pwd=jusujusu适用于中国大陆用户🌐 5. Web 服务器部署 (FastAPI)通过 FastAPI 快速将此工具部署为高性能 Web 服务。启动服务python start_server.py
Web 服务器默认启动在 5344 端口。API 接口详情请访问 http://localhost:5344/docs 查看完整的 API 文档。路由方法描述/submit_remove_taskPOST上传视频并提交处理任务。返回任务 ID，处理立即开始。/get_resultsGET使用任务 ID 检查处理进度。完成后返回包含 下载 URL 的结果。/downloadGET使用返回的 URL 下载已清理水印的视频文件。<img src="resources/53abf2fd-11a9-4dd7-a348-34920775f8ad.png" alt="FastAPI 任务提交接口截图" style="zoom: 25%;" />📚 6. 引用与致谢引用 (Citation)如果您在学术或商业工作中使用本项目，请引用：@misc{sorawatermarkcleaner2025,
  author = {linkedlist771},
  title = {SoraWatermarkCleaner},
  year = {2025},
  url = {[https://github.com/linkedlist771/SoraWatermarkCleaner](https://github.com/linkedlist771/SoraWatermarkCleaner)}
}
致谢 (Acknowledgments)本项目感谢以下优秀项目提供的支持：IOPaint：提供了 LAMA 修复算法的实现参考。Ultralytics YOLO：提供了强大的目标检测框架。
