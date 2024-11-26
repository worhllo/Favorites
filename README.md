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
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>链接一键生成</title>
</head>
<body>
  <h1>链接一键生成</h1>
  <button onclick="generateText()">生成文本</button>
  <button onclick="clearText()">清除文本</button>
  <pre id="output"></pre>
  <button onclick="copyText()">复制文本</button>

  <script>
    // 用来保存之前的文本
    let accumulatedText = '';

    function generateText() {
      // 获取用户输入
      const title = prompt("请输入 title:");
      const url = prompt("请输入 url:");
      const logo = prompt("请输入 logo:");
      const description = prompt("请输入 description:");

      // 格式化生成的文本
      const result = `- title: ${title}\n  url: ${url}\n  logo: ${logo}\n  description: ${description}\n`;

      // 将新生成的文本追加到之前的文本后面
      accumulatedText += result;

      // 更新页面上的显示区域
      document.getElementById('output').textContent = accumulatedText;
    }

    function copyText() {
      // 获取输出区域的文本
      const outputText = document.getElementById('output').textContent;

      // 创建一个临时的文本输入框来执行复制操作
      const textArea = document.createElement('textarea');
      textArea.value = outputText;  // 将生成的文本赋值给文本框
      document.body.appendChild(textArea);

      // 选中文本并执行复制
      textArea.select();
      document.execCommand('copy');

      // 删除临时文本框
      document.body.removeChild(textArea);

      // 提示用户已复制
      alert("文本已复制到剪贴板！");
    }

    function clearText() {
      // 清除 accumulatedText 和页面上显示的内容
      accumulatedText = '';
      document.getElementById('output').textContent = accumulatedText;
    }
  </script>
</body>
</html>


```

   

