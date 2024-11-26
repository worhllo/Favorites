# 本网站源于[Hugo-Webstack网址导航网站构建模板](https://github.com/oulh/nav)


完整的hugo目录结构，可以直接拷贝使用，不需要本地生成。结合自动构建，可在线编辑，自动发布；编辑自己的网站内容并Commit，每次提交修改都会触发自动构建。

详细内容请看主题 [hugo-webstack](https://github.com/oulh/hugo-webstack)

访问链接：[链接直达](https://worhllo.github.io/favorites)

## 可自定义编辑的内容

   - 网站配置：/hugo.toml

   - 主页面：/data/webstack.yml

   - 子页面：/content/xxx.md

   - “关于”页面：/content/about.md
   
   - 网站logo：/static/images/logo.png
   
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
## 获取网站图标
   - 方案1：[api.uomg.com](https://api.uomg.com/doc-get.favicon.html)

   - 方案2：[favicon.im](https://favicon.im/)

   

