# 前端代码规范

本项目前端代码规范参考 Google JavaScript Style Guide。

## 1. 命名规范

- 变量：小驼峰，如 expressionInput、historyList
- 函数：小驼峰，如 loadHistory、deleteRecord
- 常量：全大写，如 API_BASE
- 类名（CSS）：小写短横线，如 calc-card、history-item

## 2. 缩进

- 使用 2 个空格，不使用 Tab。

## 3. 分号

- 每条语句末尾加分号。

## 4. 引号

- 字符串统一使用单引号。

const API_BASE = 'https://eight32401123-calculator-backend-1.onrender.com';

## 5. 变量声明

- 优先使用 const，需要重新赋值时用 let，不使用 var。

## 6. 函数

- 使用 async/await 处理异步请求，不用回调嵌套。

async function loadHistory() {
  const response = await fetch(`${API_BASE}/api/history`);
  const data = await response.json();
}

## 7. DOM 操作

- 先获取元素引用，缓存在变量里，避免重复查询。

const expressionInput = document.getElementById('expression');
const calcBtn = document.getElementById('calcBtn');

## 8. 错误处理

- 网络请求用 try/catch 包裹，失败时给用户明确提示。

try {
  const response = await fetch(`${API_BASE}/api/calculate`, { ... });
} catch (error) {
  resultSpan.textContent = '无法连接后端服务';
}

## 9. HTML

- 标签小写，属性用双引号。
- 缩进 2 个空格。
- 语义化标签优先。

## 10. CSS

- 类名小写短横线。
- 属性顺序：定位、盒模型、排版、颜色、其他。