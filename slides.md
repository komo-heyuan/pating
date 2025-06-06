---
# Android 绘图应用项目  
## 及其 MCP 架构实践
---

## 项目简介

- **项目名称**：Android 绘图应用
- **项目定位**：简洁易用的移动端绘图工具
- **主要功能**：
  - 支持轨迹、直线、矩形、圆形等多种绘图模式
  - 颜色切换、线宽调节、填充/描边切换
  - 一键清空画布、图片保存本地

---

## 项目界面展示

- 主界面包含绘图区、功能按钮、线宽调节滑块
- 操作直观，用户体验友好

---

## 项目结构

- `MainActivity.java`：主界面与交互逻辑
- `DrawingView.java`：自定义绘图视图
- `res/`：资源文件（布局、图片、字符串等）

---

## MCP 架构简介

- **MCP**（Model-Controller-Presenter）是一种分层架构思想
- 主要分为三层：
  - **Model**：数据与业务逻辑
  - **Controller**：用户交互与逻辑控制
  - **Presenter/View**：界面展示与反馈

---

## MCP 在本项目中的应用

| 层级         | 代码实现                        | 主要职责                         |
| ------------ | ------------------------------ | -------------------------------- |
| Model        | 绘图数据、图片保存逻辑          | 管理绘图内容、处理图片存储       |
| Controller   | MainActivity.java              | 处理按钮、滑动条等用户交互事件   |
| Presenter/View | DrawingView.java              | 绘图渲染、界面反馈               |

---

## 代码片段示例

```java
// Controller: MainActivity.java
btnColor.setOnClickListener(v -> {
    // 切换颜色，通知 DrawingView
    drawingView.setColor(currentColor);
});

// Presenter/View: DrawingView.java
@Override
protected void onDraw(Canvas canvas) {
    canvas.drawBitmap(bitmap, 0, 0, null);
    canvas.drawPath(path, paint);
}
```

---

## MCP 架构优势

- **分层解耦**：界面与逻辑分离，便于维护和扩展
- **职责清晰**：每一层只关注自身职责
- **易于测试**：业务逻辑与界面分离，单元测试更方便

---

## 项目特色与创新

- 极简设计，操作零学习成本
- 结构清晰，便于后续功能扩展
- 适用场景广泛：涂鸦、笔记、流程图、教学等

---

## 总结与展望

- 项目实现了一个实用、易用的绘图工具
- 通过 MCP 架构实现了良好的结构解耦
- 未来可增加更多绘图工具和特效，提升用户体验

---

## 谢谢聆听  
欢迎提问！ 