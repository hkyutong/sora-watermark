Sora Watermark Cleaner (SoraWm)English | 中文本项目提供了一个高效、纯深度学习驱动的解决方案，用于一键移除 Sora2 生成视频中的官方水印。⚡️ 核心功能与性能概览SoraWm 采用 YOLO 目标检测和 LAMA 修复模型协同工作，确保水印去除的准确性与无痕化。功能模块技术细节特点水印检测器YOLOv11s已针对包含用户名的最新水印进行优化，定位精确。水印清除器LAMA 修复算法基于 IOPaint 实现，利用周围像素智能填充。处理支持批量处理完美支持文件夹或多文件批量操作。运行环境Python / Streamlit / FastAPI / EXE提供多种部署和使用方式。效果对比      <h3 align="center">✅ 水印移除效果</h3>            <h3 align="center">❌ 原始视频</h3>      <video src="https://github.com/user-attachments/assets/8cdc075e-7d15-4d04-8fa2-53dd287e5f4c" width="100%"></video><video src="https://github.com/user-attachments/assets/4f032fc7-97da-471b-9a54-9de2a434fa57" width="100%"></video>快速开始我们提供命令行、网页界面和一键式安装包，满足不同用户的需求。📥 1. 一键便携式版本 (Windows)无需安装 Python 或配置环境，下载解压即可运行，推荐 Windows 用户使用。平台链接提取码备注Google Drive点击下载--百度网盘https://pan.baidu.com/s/1onMom81mvw2c6PFkCuYzdg?pwd=jusujusu适用于中国大陆用户💻 2. Python 环境安装步骤 A：安装 FFmpeg视频处理依赖 FFmpeg，请确保您的系统已安装此工具。步骤 B：安装 Python 依赖推荐使用 uv 进行快速安装：# 自动创建并安装所有依赖到 .venv 目录
uv sync
模型下载说明： Yolo 权重 (best.pt) 和 Lama 模型将在首次运行时自动下载。🚀 3. 使用示例命令行批量处理使用 cli.py 脚本进行高效批量操作：python cli.py -i <输入文件夹> -o <输出文件夹> [--pattern "*.{mp4,mov,avi}"]

# 示例：处理 input 文件夹中的所有视频文件
python batch_process.py -i ./videos_input -o ./videos_output --pattern "*.{mp4,mov,avi}"
Streamlit Web 界面如果您更喜欢交互式界面，可启动本地 Streamlit App：streamlit run app.py
界面预览：界面支持拖动文件夹或多选文件进行批量处理。🌐 FastAPI Web 服务器部署将本项目部署为高性能网络服务，提供 RESTful API 接口。启动服务python start_server.py
Web 服务器默认运行在 5344 端口。API 接口详情请访问 http://localhost:5344/docs 查看完整的 API 文档。路由方法描述/submit_remove_taskPOST上传视频，返回任务 ID，处理立即开始。/get_resultsGET使用任务 ID 检查进度，完成后返回下载 URL。/downloadGET下载已清理水印的视频文件。📚 社区与贡献引用 (Citation)如果您在学术或商业工作中使用本项目，请引用：@misc{sorawatermarkcleaner2025,
  author = {linkedlist771},
  title = {SoraWatermarkCleaner},
  year = {2025},
  url = {[https://github.com/linkedlist771/SoraWatermarkCleaner](https://github.com/linkedlist771/SoraWatermarkCleaner)}
}
数据集共享为鼓励模型优化，我们已公开标注数据集：Hugging Face 数据集链接。致谢 (Acknowledgments)IOPaint：LAMA 修复算法的实现参考。Ultralytics YOLO：强大的目标检测框架。💝 支持我们： 如果本项目对您有所帮助，请考虑给我们买杯咖啡以支持持续开发！
