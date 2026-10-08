# 如何使用 AlphaFold3？

## 前提条件

此镜像基于ubuntu22.04_580构建的alphafold3镜像。
**驱动版本方面的注意**
选择gpu服务器的时候需要Nvidia驱动大于580版本及其以上的gpu云主机
**显卡方面的注意**
建议算力8.0至12.1cc(Compute Capability)的显卡，无需更改环境配置即可下载数据库和权重参数文件后开始使用。
**请参考下述地址内容选择支持算力7.5至12.1cc的nvidia显卡**
[nvidia gpu compute capability](https://developer.nvidia.com/cuda/gpus)

## 文件数据事项

数据库和模型参数文件model parameters由于版权所以需要自行处理。

**数据库**
使用/root/alphafold3/fetch_databases.sh下载，下载过慢可使用网盘下载后上传
[databases 123网盘](https://www.123865.com/s/nf1cVv-8PwJ3)
[databases baidu网盘](https://pan.baidu.com/s/1hqfsYiyR9-ZfTkXHFJpJug) 提取码: 1111
**模型参数文件**由于版权声明。models目录需要自行放置af3.bin，此文件为model parameters（模型参数），需要前往此链接去申请[model parameters](https://forms.gle/svvpY4u2jsHEwWYS6)
**若上述数据获取操作有困难，可在评论区留下评论以便获取帮助。**
**文件的解压**
在切换到models目录下执行 unzstd *.zst && rm *.zst 来解压zst文件
在databases目录中执行 unzstd *.zst && rm *.zst && tar -xf *.tar && rm *.tar 来解压数据库中的zst和tar文件

## 如何使用

1. 运行命令 `cd ~/alphafold3` 切换到 ~/alphafold3 目录
2. （首次使用）然后运行命令 `./fetch_databases.sh` 将数据库下载到 /root/autodl-tmp/databases 目录（注意：数据占用 627 GB；autodl-tmp 挂载点必须至少有 700 GB 的可用空间）。
3. 下载数据库后，运行命令 `./run-af3_conda-alphafold3.sh` 处理 `af_input` 目录中的 JSON 文件。
4. `af_input` 是输入目录（可包含多个 JSON 文件），`af_output` 是输出目录（结果），`models` 是模型参数，而 `run-af3_conda-alphafold3.sh` 是运行 alphafold3 程序的入口点。

