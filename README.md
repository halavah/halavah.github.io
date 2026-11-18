# 一屏只留一件事

个人介绍网站，正式地址：https://halavah.us/ 。

## 目录

- `docs/index.html`：页面正文、标签栏标题和TroyeKK手写签名。
- `docs/assets/personal/`：照片、CSS、字体、字体许可和图标。
- `docs/.nojekyll`：静态发布标记。
- `docs/assets/personal/favicon.svg`：深色圆角屏幕轮廓与单道琉璃横线组成的标签栏标识，不含文字字形依赖；HTML图标链接使用内容指纹防止旧图标缓存。
- `docs/CNAME`：GitHub Pages自定义域名halavah.us。
- `scripts/check-personal-page.mjs`：网页内容、资源路径与发布边界检查。
- `package.json`：检查命令，无运行依赖。

网站使用深色底，电脑和手机统一按完整4:3照片、问候语、三段正文、签名排列。正文最大620px，使用本地霞鹜文楷网页子集，17px字号、约30px行高、20px段距，左对齐且不额外拉大字间距。电脑照片宽330～390px，手机完整显示。优先阅读舒适，短屏和文字放大时自然滚动，不强行缩字或裁切正文；手机左右24px；正文底部左端为GitHub主页图标，右端为手写签名，二者与正文左右边界对应；仅提供一个GitHub入口，新标签页打开，含键盘焦点与44px点击区域；没有简历、管理或其他社交入口，也没有后端接口。

## 检查与本地预览

需要Node.js和Python 3，无需安装依赖：

```bash
npm run build
python3 -m http.server 18886 --bind 127.0.0.1 --directory docs
```

打开 http://127.0.0.1:18886/ ，结束时按Ctrl+C。

## 发布

GitHub Pages从本仓库master分支的/docs目录发布。使用用户站点仓库名halavah.github.io，默认地址为https://halavah.github.io/，自定义主域名为halavah.us；docs/CNAME仅写域名，不含协议或路径。Cloudflare的根域名使用GitHub Pages四条A记录（185.199.108.153、185.199.109.153、185.199.110.153、185.199.111.153），www的CNAME指向halavah.github.io；这些记录使用仅DNS模式，由GitHub签发证书并强制HTTPS。邮箱和其他子域名记录保持原状。图片、字体和CSS使用相对路径。

本仓库只维护网站，不包含账号贡献动画和旧Hexo归档。网站正文为已确认的三段个人介绍，去除作品窗口介绍段；原始手写签名入场书写一次，随后整笔琉璃亮光与星点每2秒循环，不显示控制文字，点击签名可暂停或继续，减少动态效果设置下保持静态；更新不增加未经确认的个人事实。文楷子集覆盖当前标题和三段正文及基本ASCII字符，文件为docs/assets/personal/wenkai-reading.woff2，许可为WenKai-OFL.txt，源自https://github.com/lxgw/LxgwWenKai的常规字重；更新正文时重新检查字形覆盖并生成子集。保留字体许可。不要提交凭据、私有配置或Git历史bundle。
