# 隋唐行纪

使用 Cocos Creator 3.8.8 开发的 Android 横屏 2D RPG。 [项目约定](AGENTS.md)

## 打开和预览

1. 在 Cocos Dashboard 的「项目」页导入本仓库根目录，选择 Creator 3.8.8 打开。
2. 从资源面板打开 `assets/scenes/Main.scene`，使用编辑器顶部的预览按钮运行。横屏设计分辨率为 1920 × 1080，固定可视高度，随屏幕比例调整可视宽度。后续触控按钮和 HUD 按设备安全区布局。

## Android 构建

在构建面板导入本项目的 Android 构建配置，启用横屏左右两个方向。首次构建前，在编辑器中配置本机 SDK 与 NDK。包名暂用 `com.dynastyquest.game`。 [Android 构建配置](settings/build-android.json) · [Creator 3.8 Android 构建说明](https://docs.cocos.com/creator/3.8/manual/en/editor/publish/android/build-options-android)
