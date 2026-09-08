# Python 代码调用接口示例 📄

> [!IMPORTANT]
> 本文是**老版本接口**（无版本号 `/openapi/…`）的文档，仅供已接入的开发者查阅。新接入请使用 v1 接口文档：<https://docs.henghengmao.com/developer/code-example/python>；迁移指南：<https://docs.henghengmao.com/developer/migration>。
>
> This page documents the **legacy (unversioned) API** and is kept for developers who already integrated it. For new integrations use the v1 API docs: <https://docs.henghengmao.com/en/developer/code-example/python>; migration guide: <https://docs.henghengmao.com/en/developer/migration>.

以下为 Python 语言调用提取接口的示例。示例代码中用到的 `API Key` 请前往[开发者接口管理中心](https://www.henghengmao.com/user/developer)获取。

```python
import requests
hhm_api = 'https://api.meowload.net/openapi/extract/post'     # 单个帖子提取接口，如果主页批量提取使用：https://api.meowload.net/openapi/extract/playlist

api_key = 'dkyfevujkpxxsc9m-w4ewnqhv8l6g'         # 这里改成你自己的 API Key

# 参数
params = {
    'url': 'https://www.bilibili.com/video/BV1sG4y1p7TA/'
}

headers = {
    'x-api-key': api_key,        # 指定 API Key
    'accept-language': 'zh'      # 指定错误 message 返回的语言为中文
}

r = requests.post(hhm_api, json=params, headers=headers, verify=False)
print(r.json())
```
