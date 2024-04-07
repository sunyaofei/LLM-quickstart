# 模型下载加速
```shell
pip install -U huggingface_hub
conda activate py3.10
export HF_ENDPOINT=https://hf-mirror.com
# 下载模型
huggingface-cli download --resume-download gpt2 --local-dir gpt2
# 下载数据集
#huggingface-cli download --repo-type dataset --resume-download wikitext --local-dir wikitext
huggingface-cli download --resume-download Qwen/Qwen-7B-Chat-Int4 --local-dir Qwen-7B-Chat-Int4 --local-dir-use-symlinks=False --revision main
huggingface-cli download --resume-download THUDM/chatglm2-6b --local-dir chatglm2-6b --local-dir-use-symlinks=False --revision main

huggingface-cli download --repo-type dataset --resume-download mozilla-foundation/common_voice_11_0 --local-dir common_voice_11_0 --local-dir-use-symlinks=False --revision main --include 'audio/zh-CN/*' 'transcript/zh-CN/*'
while ; do huggingface-cli download --repo-type dataset --resume-download mozilla-foundation/common_voice_11_0 --local-dir common_voice_11_0 --local-dir-use-symlinks=False --revision main --include 'audio/zh-CN/*' 'transcript/zh-CN/*'; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done
while ; do huggingface-cli download --repo-type model --resume-download facebook/opt-2.7b --local-dir opt-2.7b --local-dir-use-symlinks=False --revision main --exclude 'flax_model.msgpack' 'tf_model.h5'; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done
while ; do huggingface-cli download --repo-type model --resume-download facebook/opt-6.7b --local-dir opt-6.7b --local-dir-use-symlinks=False --revision main --exclude '*.msgpack' '*.h5'; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done



while ; do huggingface-cli download --resume-download THUDM/chatglm3-6b --local-dir chatglm3-6b --revision main --exclude '*.safetensors' '*.bin'; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done



huggingface-cli download --repo-type dataset --resume-download shibing624/AdvertiseGen --local-dir AdvertiseGen --local-dir-use-symlinks=False --revision main


while ; do huggingface-cli download --resume-download THUDM/chatglm3-6b --local-dir chatglm3-6b-safetensors --revision main --include '*.safetensors'; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done
while ; do huggingface-cli download --resume-download THUDM/chatglm3-6b --local-dir chatglm3-6b-bak --revision main --include 'pytorch_model-00007-of-00007.bin'; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done





while ; do huggingface-cli download --repo-type dataset --resume-download wikitext --local-dir wikitext --revision main --include "wikitext-2-raw-v1/*"; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done
while ; do huggingface-cli download --repo-type dataset --resume-download wikitext --local-dir wikitext --local-dir-use-symlinks=False --revision main --include "wikitext-2-raw-v1/*"; e=$?; echo $e; if [ $e -eq 0  ]; then echo $e; break; else echo 'y'; fi; sleep 1; done



```