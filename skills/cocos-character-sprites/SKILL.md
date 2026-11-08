---
name: cocos-character-sprites
description: 整理《隋唐行纪》俯视角色的待机或行走帧。用于拆分已有透明 PNG 条带、检查不同方向的角色比例和落脚点、制作预览并导入 Cocos Creator 3.8。
---

# Cocos 角色精灵

1. 以批准的角色帧核对各方向的服饰、体型和游戏内显示尺寸。先确定每个方向的帧顺序、画布尺寸和地面接触点。
2. 只有当输入是单行等宽帧、帧之间无重叠，而且各帧可按可见像素底部对齐时，才使用下面的拆分脚本。脚本按单条带统一缩放并对齐到底部中央。包含离地动作、影子或长袍摆动的帧应保留原作者的落脚基准，避免自动对齐改变动作。已有正确画布和锚点的逐帧 PNG 可直接预览。
3. 将每个方向的结果与批准帧放在同一显示尺度比较。检查空帧、截断、透明背景、帧顺序和脚底抖动。脚本分别处理每条带，各方向的缩放比例需单独核对。
4. 将批准的帧导入为 SpriteFrame。检查 Sprite 的 Trim 与 Size Mode 是否保留帧间位移关系，在固定角色位置播放循环，确认碰撞点与角色落脚点对齐。 [Cocos 3.8 SpriteFrame](https://docs.cocos.com/creator/3.8/manual/en/asset/sprite-frame.html) · [Sprite 组件](https://docs.cocos.com/creator/3.8/manual/en/ui-system/components/editor/sprite.html)

## 本地工具

脚本依赖 Python 3.10+ 和 Pillow。以下命令从仓库根目录运行。示例用四帧和 64 像素画布，实际以素材约定为准。每个方向使用独立的空输出目录，预览图放在帧目录外。

```powershell
python skills/cocos-character-sprites/scripts/normalize_sprite_strip.py --input walk-south.png --out-dir preview/south --frames 4 --frame-size 64
python skills/cocos-character-sprites/scripts/render_sprite_preview_sheet.py --frames-dir preview/south --out preview/south-contact.png --columns 4
```

[拆分脚本](scripts/normalize_sprite_strip.py) · [预览脚本](scripts/render_sprite_preview_sheet.py)
