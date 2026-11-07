# HTML 转 iOS App（无需 Mac）

## 步骤
1. 把你的网页放进 `www/`，入口必须是 `www/index.html`（多文件、图片、JS 都放这里，用相对路径引用）。
2. 在 GitHub 新建仓库，把本项目全部文件上传（注意 `.github` 文件夹也要上传）。
3. 打开仓库 Actions → Build IPA → Run workflow，等几分钟。
4. 在运行结果底部 Artifacts 下载 `HTMLApp-ipa`，解压得到 `HTMLApp.ipa`。
5. 用 Sideloadly / AltStore 登录你的 Apple ID 重签并安装（免费账号 7 天有效；TrollStore 可直接安装）。

## 自定义
- App 名称：`project.yml` 里的 `CFBundleDisplayName`
- 包名：`PRODUCT_BUNDLE_IDENTIFIER`
- 只想横屏/竖屏：改 `UISupportedInterfaceOrientations`

## 限制
iOS 的 WKWebView 不支持 Web Bluetooth、Web Serial；需要这类功能得写原生桥接。
