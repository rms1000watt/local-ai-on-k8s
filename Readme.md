# Local AI on K8s

## Introduction

Run AI (ollama currently..) on your local K8s setup.

(This is just for me, but making it public because YOLO)

## Install Ollama on k8s

```bash
helmfile -f helmfile.yaml apply


curl ollama.rms1000watt.com:31434/api/generate -d '{
  "model": "qwen2.5-coder:0.5b",
  "system": "You are a code generation tool",
  "prompt": "Create a typescript express server for a user admin dashboard. Do not be verbose, only generate the code ",
  "stream": false
}' | jq .response | sed 's/\\n/\n/g'
```
