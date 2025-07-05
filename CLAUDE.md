
# CLAUDE.md更新用Todo: Flutterアプリのアイコン・スプラッシュスクリーン生成手順

## 📝 概要
このドキュメントでは、Flutterアプリのアイコンおよびスプラッシュスクリーン生成の手順をまとめます。特に、環境による画像変換ツールの有無に応じた補足情報を含めます。

---

## ✅ 必要ツールと準備
- **Flutterパッケージ**
  - `flutter_launcher_icons`: アイコン自動生成
  - `flutter_native_splash`: スプラッシュスクリーン生成
- **画像生成・変換**
  - デザインツール（Figma、GIMP、Inkscape など）
  - 変換ツール（ImageMagick、rsvg-convert、Python cairosvg など）
  - **⚠️ 環境不足時はオンラインツールで代用可（例：Canva、SVG→PNGコンバータ）**

---

## 🛠 手順

### 1️⃣ アプリアイコン（512x512 PNG）作成
1. アプリコンセプトに基づいてデザインを作成（背景透過PNG推奨）。
2. デザインツールで512x512 PNGを書き出し。  
   ⚠️ 環境不足（ImageMagick未導入）の場合はオンラインツールで変換。
3. 画像ファイルを `assets/images/icon.png` に配置。

### 2️⃣ flutter_launcher_iconsで全サイズ自動生成
1. `pubspec.yaml`に以下を追加：
   ```yaml
   dev_dependencies:
     flutter_launcher_icons: ^0.13.1
   flutter_icons:
     android: true
     ios: true
     image_path: "assets/images/icon.png"
   ```
2. コマンド実行：
   ```bash
   flutter pub get
   flutter pub run flutter_launcher_icons:main
   ```
3. 出力先確認（Android/iOSの各アイコンディレクトリ）。

### 3️⃣ flutter_native_splashでスプラッシュスクリーン設定
1. `pubspec.yaml`に以下を追加：
   ```yaml
   dev_dependencies:
     flutter_native_splash: ^2.3.2
   flutter_native_splash:
     color: "#ffffff" # 背景色
     image: assets/images/icon.png # 画像パス
     android: true
     ios: true
   ```
2. コマンド実行：
   ```bash
   flutter pub get
   flutter pub run flutter_native_splash:create
   ```
3. 出力先確認（Android/iOSのスプラッシュ用ディレクトリ）。

---

## ⚠️ 注意点
- **画像生成環境の制約**：現状、ImageMagick等のローカル変換ツールは未導入。そのため、  
  ➡️ オンラインSVG→PNG変換ツールやデザインツールでPNG作成を推奨。  
- アイコンとスプラッシュ画像はアプリコンセプトに基づき統一感を持たせること。

---
