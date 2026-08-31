# galgame-build（安卓壳工程 + 云端打包配方）

本仓库内容：

- `app/` —— 一个极简 WebView 安卓壳，加载 `app/src/main/assets/www/index.html`，完全离线运行
- `.github/workflows/build-apk.yml` —— 云端打包配方（GitHub Actions）
- 不要手改 `app/src/main/assets/www/`（每次打包会被游戏内容覆盖）
- 应用图标：`app/src/main/res/drawable/ic_launcher_foreground.xml` + `mipmap-anydpi-v26/`
- 应用名：每次打包时由"应用名"输入自动写入，不用手动改

## 触发方式

- 自动：由 `packaging-service`（打包机）调用 GitHub API 触发
- 手动测试：仓库页面 → **Actions** → 左侧 **build-apk** → **Run workflow** → 填 zip_url 和 app_name → Run

## 打包结果

产物 APK 由打包机取回并转存，不留在本仓库。
