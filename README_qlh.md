## 版本
    v0.1.0 langchain-ChatCLM 升级为 0.2.10版本
    v2.1.0  langchat-chatcaht版本升级为v0.3.0 并删除原有修改

## 启动命令
    nohup python3 -u -m fastchat.serve.controller >/opt/logs/controller.log 2>&1 &
    
    CUDA_VISIBLE_DEVICES=0 nohup python3 -u -m fastchat.serve.model_worker --model-name 'chatglm2-6b' --model-path /opt/model/chatglm2-6b >/opt/logs/model_worker.log 2>&1 &
   
    nohup python3 -u -m fastchat.serve.openai_api_server --host 0.0.0.0 --port 8001 >/opt/logs/openai_api.log 2>&1 &

    nohup python3 -u webui.py >/opt/logs/webui.log 2>&1 &

    nohup python3 -u api.py --port 7862 >/opt/logs/api.log 2>&1 &

    nvidia-smi

    nohup python3 -u startup.py -a >/opt/logs/startup.log 2>&1 &

    ps aux|grep python|grep -v grep|cut -c 9-16|xargs kill -9

