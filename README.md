# suc-lmcahe






ubuntu24

rtx5060ti16gb

python3.12

cuda tookit 12.8




git clone https://github.com/LMCache/LMCache.git
cd LMCache


uv venv --python 3.12  
source .venv/bin/activate




uv pip install torch==2.7.1 torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128


uv pip install -r requirements/build.txt
uv pip install vllm==0.10.0

uv pip install -e . --no-build-isolation



















termenal1



LMCACHE_CHUNK_SIZE=8 \
vllm serve facebook/opt-125m \
    --port 8000 --kv-transfer-config \




    termenal2




        
 curl http://localhost:8000/v1/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "facebook/opt-125m",
    "prompt": "Qwen3 is the latest generation of large language models in Qwen series, offering a comprehensive suite of dense and mixture-of-experts",
    "max_tokens": 100,
    "temperature": 0.7
  }'
    '{"kv_connector":"LMCacheConnectorV1", "kv_role":"kv_both"}'
