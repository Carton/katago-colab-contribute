# KataGo Colab 贡献（通过自动更新 gist 的 TensorRT/CUDA）

这是一个在 Google Colab 上为 KataGo 分布式训练贡献算力的极简步骤，直接复制两段代码即可运行。之所以使用 gist，是为了在 KataGo/TensorRT/CUDA 版本更新时，Notebook 无需手动修改，只需每次运行前重新下载脚本即可自动跟进更新。适合同时开多个 Colab 页贡献算力。

- 安装脚本 gist： https://gist.github.com/Carton/1da29b7f89144c7176543839ddc5f9bb
- 辅助扩展（可选）： https://github.com/Carton/ColabRunner

## 快速开始（Google Colab）

1. 打开一个新的 Colab 笔记本： https://colab.research.google.com/
2. 切换运行时到 GPU（优先选择 T4）：
   - 菜单：运行时  更改运行时类型  硬件加速器：GPU
   - 验证 GPU（应显示 T4）：

        !nvidia-smi -L

3. 在第一个代码单元，填写 KataGo 训练账户（可选设置并行线程数）：

        USERNAME = "你的用户名"   # katagotraining.org 的账户
        PASSWD = "你的密码"
        THREADS = 16              # 可选：并行自对弈局数

4. 在下一个代码单元，下载并运行安装脚本：

        !wget -O katago_dist_setup.ipy "https://gist.githubusercontent.com/Carton/1da29b7f89144c7176543839ddc5f9bb/raw/katago_dist_setup.ipy"
        %run katago_dist_setup.ipy

5. 观察日志。首次运行会安装依赖并下载引擎/模型，后续运行会更快。想贡献更多算力，可再开多个 Colab 标签页重复以上步骤。

## 为什么用 gist？
- 版本更新时自动跟进，所有 Colab 页面只需重新下载脚本即可保持最新。
- 便于多标签页并行运行，无需手动同步 Notebook 内容。

## 提示
- 脚本默认使用 CUDA + TensorRT，针对 Colab 的 Tesla T4 做过优化。
- 账户凭据用于 katagotraining.org，请确保正确填写。
- 如果首次启动没有 GPU，请切换到 GPU 运行时后，重新运行上面两个代码单元。

## 一键多标签控制（可选）
推荐使用 Chrome 扩展 ColabRunner 按标题关键字一键启动/停止多个 Colab 标签页，方便规模化并行贡献。

## 链接
- 安装脚本 gist： https://gist.github.com/Carton/1da29b7f89144c7176543839ddc5f9bb
- ColabRunner 扩展： https://github.com/Carton/ColabRunner
