# Embedded-Optimized Source Han Sans Pixel Font

专为嵌入式系统优化的精简版思源黑体点阵字库，特别适配ESP32平台的CircuitPython环境。

## 项目背景

本字体基于 [Adobe Source Han Sans-Light](https://github.com/adobe-fonts/source-han-sans) 进行深度优化，通过以下改进实现嵌入式场景的高效使用：
- 仅保留GB2312标准01-02和16-55以及部分08区的编码，共4041个汉字
- 精选基础拉丁字符集（ASCII可打印字符）
- 专为低资源环境优化字体数据结构
- 点阵12pt规格，适配嵌入式系统显示设备的渲染特性

## 核心特性

✅ **精准字符覆盖**  
- 支持GB2312汉字精简字符集（4041字）
- 包含英文数字及常用标点符号（ASCII 32-126）
- 总计约4278字符

🚀 **性能优化**  
- 采用PCF（Portable Compiled Format）字体格式
- 内存占用减少约65%（相较原版OTF）
- 针对ESP32的SPIRAM特性优化存储结构

## 快速开始

### 安装使用

1. 下载预编译的 `.pcf` 字体文件
2. 将字体文件放入CircuitPython设备的`/fonts`目录
3. 在代码中调用示例：

```python
from displayio import Bitmap
import terminalio
from adafruit_display_text import bitmap_label

font = terminalio.FONT.load("/fonts/SourceHanSansCN-Light_GB2312a_12pt.pcf")
label = bitmap_label.Label(font, text="你好 World!")
```

## 许可证

本项目遵循 [SIL OPEN FONT LICENSE](https://github.com/adobe-fonts/source-han-sans?tab=License-1-ov-file#readme) 开源协议：

完整协议见原字体的 [LICENSE](https://raw.githubusercontent.com/adobe-fonts/source-han-sans/refs/heads/master/LICENSE.txt) 文件。

### 注意事项

⚠️ 如需扩展字符集建议使用原版思源黑体
⚠️ 本项目参考了 [u8g2_wqy](https://github.com/larryli/u8g2_wqy) 项目

本项目基于Adobe Source Han Sans字体改造，原始字体版权归Adobe Systems Incorporated所有.