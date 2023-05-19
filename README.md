# IntelModelZooDockerfile
ModelZoo代码库: https://github.com/IntelAI/models/tree/master  
  
本项目主要为了构建intel model zoo可执行docker环境, 降低部署成本.  
代码库中列出的镜像均已传到了dockerhub上, 地址在下面每个模型的介绍里有.  
启动docker镜像后只需要按文档从quickstart下的脚本启动即可.  
  
**统一执行命令**:  
(1) 启动镜像  
`docker run --name [your_name] --privileged -itd --net=host --ipc=host [image:tag]`  
(2) 进入镜像  
`docker exec -it [your_name] bash`  
  
工作目录默认都在/root下, 包括/root/models, /root/output以及下载的数据和模型等  
  
### recommendation
#### DIEN
**简介**: 推荐领域常见的用户兴趣模型, DIN升级版.  
**Dockerfile**: dockerfiles/Dockerfile.dien  
**DockerHub**: `docker pull nightwang/intel_model_zoo:dien_v1`  
**执行**: `cd /root/models && ./quickstart/recommendation/tensorflow/dien/inference/cpu/inference.sh`  
**使用说明**: https://github.com/IntelAI/models/blob/master/benchmarks/recommendation/tensorflow/dien/inference/README.md  

### text_to_speech
#### WaveNet
**简介**: 语音合成模型.  
**Dockerfile**: dockerfiles/Dockerfile.wavenet  
**DockerHub**: `docker pull nightwang/intel_model_zoo:wavenet_v1`  
**执行**: `cd /root/models && ./quickstart/text_to_speech/tensorflow/wavenet/inference/cpu/fp32/fp32_inference.sh`  
**使用说明**: https://github.com/IntelAI/models/blob/master/benchmarks/text_to_speech/tensorflow/wavenet/inference/fp32/README.md  
