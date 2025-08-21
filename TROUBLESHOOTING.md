# 《错位的礼物》故障排除指南

## 常见问题

### 1. 点击"开始游戏"按钮无反应

**症状：**
- 点击开始游戏按钮后，游戏没有开始
- 音频文件没有加载（在浏览器开发者工具的Network面板中看不到mp3文件）
- 在匿名/隐身模式下可以正常游玩

**原因：**
浏览器缓存了旧版本的JavaScript文件

**解决方案：**

#### 方法一：强制刷新（推荐）
- Windows/Linux: `Ctrl + F5` 或 `Ctrl + Shift + R`
- Mac: `Cmd + Shift + R`

#### 方法二：使用缓存清理工具
1. 打开 `clear_cache.html` 文件
2. 点击"清理浏览器缓存"按钮
3. 等待页面自动刷新

#### 方法三：手动清理浏览器缓存
1. 打开浏览器开发者工具 (F12)
2. 右键点击刷新按钮
3. 选择"清空缓存并硬性重新加载"

#### 方法四：清理localStorage（如果上述方法无效）
在浏览器控制台执行：
```javascript
localStorage.removeItem('misplacedGifts_settings');
localStorage.removeItem('misplacedGifts_saves');
location.reload(true);
```

### 2. 游戏加载错误

**症状：**
- 页面显示空白
- 控制台出现JavaScript错误

**解决方案：**
1. 确保所有文件都已正确下载
2. 检查文件结构是否完整：
   - index.html
   - game.js
   - story-data.js
   - audio-manager.js
   - style.css
   - theme.css
   - audio/forest_mixtape.mp3

### 3. 音频无法播放

**症状：**
- 游戏正常运行但没有声音

**解决方案：**
1. 检查游戏设置中的"音效"选项是否开启
2. 检查浏览器是否允许自动播放音频
3. 确保音频文件存在于 `audio/` 目录

## 调试工具

- **test_game_start.html** - 测试游戏组件加载状态
- **debug.html** - 实时监控游戏运行状态
- **clear_cache.html** - 清理缓存和游戏数据

## 浏览器兼容性

推荐使用以下浏览器的最新版本：
- Chrome / Edge (推荐)
- Firefox
- Safari

## 需要更多帮助？

如果问题仍未解决，请尝试：
1. 在浏览器控制台查看具体错误信息
2. 尝试在其他浏览器中打开游戏
3. 确保没有浏览器扩展干扰游戏运行