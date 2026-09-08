# JavaScript 代码调用接口示例 📄

> [!IMPORTANT]
> 本文是**老版本接口**（无版本号 `/openapi/…`）的文档，仅供已接入的开发者查阅。新接入请使用 v1 接口文档：<https://docs.henghengmao.com/developer/code-example/javascript>；迁移指南：<https://docs.henghengmao.com/developer/migration>。
>
> This page documents the **legacy (unversioned) API** and is kept for developers who already integrated it. For new integrations use the v1 API docs: <https://docs.henghengmao.com/en/developer/code-example/javascript>; migration guide: <https://docs.henghengmao.com/en/developer/migration>.

以下为 JavaScript 语言调用提取接口的示例。示例代码中用到的 `API Key` 请前往[开发者接口管理中心](https://www.henghengmao.com/user/developer)获取。

```javascript
const api = "https://api.meowload.net/openapi/extract/post"; // 单个帖子提取接口，如果主页批量提取使用：https://api.meowload.net/openapi/extract/playlist

const apiKey = "dkyfevujkpxxsc9m-w4ewnqhv8l6g"; //这里改成你自己的 API Key

const params = {
  url: "https://v.douyin.com/MGkSpJS/",
};

const xhr = new XMLHttpRequest();
xhr.open("POST", api, true);
xhr.setRequestHeader("content-type", "application/json;charset=UTF-8");
xhr.setRequestHeader("x-api-key", apiKey); // 指定 API Key
xhr.setRequestHeader("accept-language", "zh"); // 指定错误 message 返回的语言为中文
xhr.onreadystatechange = function () {
  if (xhr.readyState === 4) {
    console.log(xhr.responseText);
  }
};
xhr.send(JSON.stringify(params));
```
