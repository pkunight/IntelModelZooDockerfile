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
**Dockerfile**: dockerfiles/dien/Dockerfile.dien  
**DockerHub**: `docker pull nightwang/intel_model_zoo:dien_v1`  
**执行预测**:  
`cd /root/models && ./quickstart/recommendation/tensorflow/dien/inference/cpu/inference.sh`  
**执行训练**:  
`cd /root/models && ./quickstart/recommendation/tensorflow/dien/training/cpu/training.sh  
注: training.sh中, 末尾的launch_benchmark.py需要增加一个参数--num-cores=1, 否则会报错. 而且不知为何脚本只识别一个核, 配置多core就报错`  
**使用说明**: https://github.com/IntelAI/models/blob/master/benchmarks/recommendation/tensorflow/dien/inference/README.md  
  
### text_to_speech
#### WaveNet
**简介**: 语音合成模型.  
**Dockerfile**: dockerfiles/wavenet/Dockerfile.wavenet  
**DockerHub**: `docker pull nightwang/intel_model_zoo:wavenet_v1`  
**执行**: `cd /root/models && ./quickstart/text_to_speech/tensorflow/wavenet/inference/cpu/fp32/fp32_inference.sh`  
**使用说明**: https://github.com/IntelAI/models/blob/master/benchmarks/text_to_speech/tensorflow/wavenet/inference/fp32/README.md  
  
### language_modeling
#### BERT large
**简介**: 自然语言处理领域常见模型.  
**Dockerfile**: dockerfiles/bert/Dockerfile.bert_large  
**DockerHub**: `docker pull nightwang/intel_model_zoo:bert_large_v1`  
**执行**: `cd /root/models && ./quickstart/language_modeling/tensorflow/bert_large/inference/cpu/inference.sh`  
**使用说明**: https://github.com/IntelAI/models/tree/master/benchmarks/language_modeling/tensorflow/bert_large/inference  
