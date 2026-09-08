# PHP 代码调用接口示例 📄

> [!IMPORTANT]
> 本文是**老版本接口**（无版本号 `/openapi/…`）的文档，仅供已接入的开发者查阅。新接入请使用 v1 接口文档：<https://docs.henghengmao.com/developer/code-example/php>；迁移指南：<https://docs.henghengmao.com/developer/migration>。
>
> This page documents the **legacy (unversioned) API** and is kept for developers who already integrated it. For new integrations use the v1 API docs: <https://docs.henghengmao.com/en/developer/code-example/php>; migration guide: <https://docs.henghengmao.com/en/developer/migration>.

以下为 PHP 语言调用提取接口的示例。示例代码中用到的 `API Key` 请前往[开发者接口管理中心](https://www.henghengmao.com/user/developer)获取。

```php
$api = "https://api.meowload.net/openapi/extract/post";   # 单个帖子提取接口，如果主页批量提取使用：https://api.meowload.net/openapi/extract/playlist

$apiKey = "dkyfevujkpxxsc9m-w4ewnqhv8l6g";   //这里改成你自己的 API Key

//参数
$url = "https://www.tiktok.com/@nike/video/7198345395863309611";

$params = array("url" => $url);
$options = array(
    "http" => array(
        "header"  => "content-type: application/json\r\nx-api-key: " . $apiKey . "\r\naccept-language: zh",
        "method"  => "POST",
        "content" => json_encode($params),
    ),
    "ssl" => array(
        "verify_peer" => false,
        "verify_peer_name" => false,
    ),
);

$result = file_get_contents($api,false, stream_context_create($options));
var_dump($result);
```
