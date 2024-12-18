# 本网站源于[Hugo-Webstack网址导航网站构建模板](https://github.com/oulh/nav)


完整的hugo目录结构，可以直接拷贝使用，不需要本地生成。结合自动构建，可在线编辑，自动发布；编辑自己的网站内容并Commit，每次提交修改都会触发自动构建。

详细内容请看主题 [hugo-webstack](https://github.com/oulh/hugo-webstack)


## 可自定义编辑的内容

   - 网站配置：/hugo.toml

   - 主页面：/data/webstack.yml

   - 子页面：/content/xxx.md

   - “关于”页面：/content/about.md
   
   - 网站logo：/static/images/logo.png

     - 方案1：[api.uomg.com](https://api.uomg.com/doc-get.favicon.html)

     - 方案2：[favicon.im](https://favicon.im/)
   
   - 导航网址默认logo：/static/images/favicon.png
   
   - 导航网址logo：/static/images/logos/（可自定义路径）
   
   - 导航网址二维码：/static/images/qrcodes/（可自定义路径）
   
   查看构建状态：Actions - All workflows

   如何希望提交后不触发构建，只需在 commit 信息中包含关键词：`[skip ci]`或`[no ci]`，包括[]符号。

## 附：webstack.yml编辑模板

title和url是必要属性，logo、description、qrcode可留空或删除。

```yaml
---
- taxonomy: 常用工具
  icon: fa-star
  links: 
    - title: 网络剪贴板
      url: https://netcut.cn/
      logo: images/logos/xxx.png
      qrcode: https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=https://netcut.cn/
      description: 在线跨屏剪切文字
          
- taxonomy: 影视影音
  icon: fa-video-camera
  list: 
    - term: 影视
      links:
        - title: 阿里小站
          url: https://pan666.cn
          description: 阿里云盘资源共享站。人人为我，我为人人的共享资源社区

    - term: 字幕
      links:
        - title: 字幕库
          url: https://zmk.pw/
        - title: SubHD
          url: https://subhd.tv/
    - term: 音乐
      links:
        - title: 果核音乐搜搜
          url: https://music.ghxi.com/
        - title: 音乐磁场
          url: https://www.hifini.com/

- taxonomy: 友情链接
  icon: fa-link
  friend:
    - title: 子页面一
      url: sub1
      description: 本站子页面一，对应content目录的sub1.md，可重命名、删除、复制。
    - title: 一为导航
      url: https://nav.iowen.cn/
      description: onenav主题演示站
    - title: 趣导航
      url: https://qssily.com/
      
---

```
## 附：链接一键生成模板
```
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>链接批量生成器</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background-color: #f4f4f9;
        }
        h1 {
            text-align: center;
        }
        .container {
            width: 80%;
            margin: 0 auto;
        }
        textarea {
            width: 100%;
            height: 150px;
            padding: 10px;
            margin-bottom: 10px;
            border-radius: 4px;
            border: 1px solid #ccc;
            font-size: 16px;
            font-family: monospace;
        }
        .button-container {
            margin-top: 10px;
            text-align: center;
        }
        .button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            margin: 5px;
        }
        .button.copy {
            background-color: #2196F3;
        }
        .output {
            margin-top: 20px;
            white-space: pre-wrap;
            background-color: #fff;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-family: monospace;
            word-wrap: break-word;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1>链接批量生成器</h1>

        <!-- 输入多个URL -->
        <textarea id="urls" placeholder="请输入多个URL，每行一个"></textarea>

        <div class="button-container">
            <button class="button" onclick="generateContent()">生成内容</button>
            <button class="button copy" onclick="copyToClipboard()">一键复制</button>
        </div>

        <h3>生成结果:</h3>
        <div id="output" class="output"></div>
    </div>

    <script>
        function generateContent() {
            // 获取用户输入的URL
            const urls = document.getElementById('urls').value.trim();
            if (!urls) {
                alert("请输入至少一个URL！");
                return;
            }

            // 将用户输入的URL按行拆分
            const urlArray = urls.split('\n').map(url => url.trim()).filter(url => url);

            // 固定的内容
            const title = "GitHub 文件加速";
            const logo = "";
            const description = "";

            // 生成内容
            let output = '';
            urlArray.forEach(url => {
                output += `- title: ${title}\n  url: ${url}\n  logo: ${logo}\n  description: ${description}\n\n`;
            });

            // 显示生成的内容
            document.getElementById('output').textContent = output.trim();
        }

        function copyToClipboard() {
            const outputText = document.getElementById('output').textContent;

            if (!outputText) {
                alert("请先生成内容！");
                return;
            }

            // 创建一个隐藏的文本框，将内容复制到这个文本框中
            const tempTextArea = document.createElement('textarea');
            tempTextArea.value = outputText;
            document.body.appendChild(tempTextArea);

            // 选中文本并复制到剪贴板
            tempTextArea.select();
            document.execCommand('copy');

            // 删除临时文本框
            document.body.removeChild(tempTextArea);

            alert("内容已复制到剪贴板！");
        }
    </script>

</body>
</html>



```

   

