# IntelModelZooDockerfile
ModelZoo代码库: https://github.com/IntelAI/models/tree/master  
  
本项目主要为了构建intel model zoo可执行docker环境, 降低部署成本.  
启动docker镜像后只需要按文档从quickstart下的脚本启动即可.  
  
**统一执行命令**:
(1) 启动镜像  
`docker run --name [your_name] --privileged -itd --net=host --ipc=host [image:tag]`  
(2) 进入镜像  
`docker exec -it [your_name] bash`  
  
工作目录默认都在/root下  
  
### recommendation
#### DIEN
**简介**: 推荐领域常见的用户兴趣模型, DIN升级版.  
**Dockerfile**: dockerfiles/Dockerfile.dien  
**DockerHub**:  
**使用说明**: https://github.com/IntelAI/models/blob/master/benchmarks/recommendation/tensorflow/dien/inference/README.md  

### text_to_speech
#### WaveNet
**简介**: 语音合成模型.  
**Dockerfile**: dockerfiles/Dockerfile.wavenet  
**DockerHub**:  
**使用说明**: https://github.com/IntelAI/models/blob/master/benchmarks/text_to_speech/tensorflow/wavenet/inference/fp32/README.md  
