# siri-glsl

用 WebGL / GLSL 学习复刻 **Apple 新版 Siri 动画**与 **Liquid Glass** 效果。

每个 demo 都是单文件 HTML,零依赖,浏览器直接打开就能跑。

A GLSL study recreating Apple's new Siri animation and the Liquid Glass effect.
Each demo is a single self-contained HTML file — no dependencies, just open it in a browser.

## Demos

| Demo | 文件 | 说明 |
|------|------|------|
| 🌊 Siri Wave | [`siri-wave.html`](siri-wave.html) | 新版 Siri 声波 (siriWaveCore) 与流体圆点 (siriFluidDotsCore):光谱色散、Lorentzian 发光线、metaball + smin 平滑融合、欠阻尼弹簧动画 |
| 🫧 Liquid Glass | [`liquid-glass.html`](liquid-glass.html) | QuartzCore `glass_background` 重建:透镜折射、色差、backdrop 模糊、黑顶镜面、赤道亮线,支持上传截图实时折射,所有参数可调 |

## 技术点 / Techniques

- 纯 fragment shader 绘制,单个大三角形全屏覆盖
- 多光谱采样做色散 (chromatic aberration)
- `1/(d+t)` 发光线 + Lorentzian 衰减
- metaball SDF + smooth-min 流体融合
- 欠阻尼弹簧 `1 − e^(−lt)·cos(wt)` 做自然回弹
- 透镜位移场折射 + 两 pass 高斯模糊

## License

MIT
