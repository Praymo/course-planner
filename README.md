# CFI DIY Course Planner

一个无需构建的静态选课沙盘，用来把课程班次、时间、校区和个人偏好放在同一张周课表里检查。

## 功能

- 从课程池拖拽或点击加入课表，支持同一课程的班次替换
- 检查时间冲突、早课、周六课程、学分预警、TBA 和培养方向待确认项
- 显示班号、校区、教室和已整理的公开课程简介
- 选择保存在浏览器 `localStorage`，支持清空和打印课表
- 通过官方 SIS 链接回到正式系统；本工具不会提交选课或退课

## 快速运行

本项目没有 npm 依赖。进入仓库目录后运行：

```bash
python3 -m http.server 8080
```

然后打开 <http://localhost:8080/>。也可以直接打开 `index.html`，但本地静态服务器更适合测试浏览器存储和复制课程代码功能。

运行静态检查：

```bash
node check-planner.cjs
```

检查脚本会验证 HTML/JavaScript 语法、课程数量、地点完整性、重复课程处理、冲突拒绝、早课硬约束和公开版本隐私边界。

## 数据边界

页面使用 2026-08-27 整理的历史课程时间与地点快照，并引用公开课程页面的简介。它不是 SIS 的实时接口，也不代表当前学期的完整课程池、容量、资格或最终教室安排。正式选课前请以学校最新 SIS 和通知为准。

页面不要求登录，不读取账号、Cookie 或凭证；课表选择只保存在当前浏览器中。它是规划工具，不是正式注册工具。

## English

CFI DIY Course Planner is a zero-build static prototype for comparing course sections, meeting times, campuses, rooms, and personal planning preferences on a weekly calendar.

It supports drag-and-drop planning, section replacement, conflict checks, morning/Saturday preferences, credit warnings, TBA and uncertain-requirement alerts, local browser storage, printing, and a link back to the official SIS. It never submits enrollment actions.

The included data is a historical snapshot prepared on 2026-08-27, supplemented with public course-page summaries. It is not a live SIS integration and must not be treated as an authoritative source for current enrollment. No login, cookies, credentials, or personal notes are included.

## 验证与贡献

发布检查通过核心规则测试，并在浏览器中验证加入课程后课表和学分同步更新。项目使用 Codex 辅助开发，聚焦课程约束建模、可解释提示和浏览器本地交互。

原创代码使用 MIT License；学校课程信息及链接的权利归其各自权利人。
