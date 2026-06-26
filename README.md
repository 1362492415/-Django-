# 在线课程学习平台 (Online Education Platform)

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.x-blue.svg" alt="Python">
  <img src="https://img.shields.io/badge/Django-5.x-success.svg" alt="Django">
  <img src="https://img.shields.io/badge/MySQL-Supported-orange.svg" alt="MySQL">
</p>

这是一个基于 Python Django 框架开发的在线教育与课程学习平台。系统包含了学生、教师和管理员等多个角色，提供了从课程发布、视频学习、作业提交到退款申请的完整业务闭环。适合作为毕业设计或学习 Django 实战的项目参考。

## 🌟 核心功能

- **多角色系统**：支持学生、教师、管理员登录与权限控制。
- **课程与视频学习**：支持章节和课节管理，内置视频播放器，并记录学习进度。
- **互动与作业**：支持课程评论、视频点赞收藏，以及课后作业的发布、提交与批改。
- **订单与退款**：实现课程购买流程及退款申请审批流程。
- **后台管理**：管理员/教师面板，可管理用户、课程、订单、轮播图（Banner）和系统公告。
- **富文本编辑**：集成 TinyMCE，用于编辑图文并茂的课程详情。

## 🛠️ 技术栈

- **后端**：Python 3, Django 5.x
- **数据库**：MySQL (通过 `mysqlclient` 或 `PyMySQL` 连接)
- **前端**：HTML5, CSS3, JavaScript (结合原生 JS 与模板引擎渲染)
- **部署配置**：内置 `vercel.json` 支持 Serverless 部署

## 🚀 快速启动

### 1. 环境准备
确保本机已安装 Python 3.x 和 MySQL 数据库。

### 2. 配置数据库
在 MySQL 中创建一个名为 `bishe` 的数据库。
在 `myproject/myproject/settings.py` 中，修改 `DATABASES` 配置以匹配你本机的 MySQL 账号密码：
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'bishe',
        'USER': 'root',          # 你的 MySQL 用户名
        'PASSWORD': '123456789', # 你的 MySQL 密码
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 3. 安装依赖与数据库迁移
打开终端，在项目根目录运行以下命令：
```bash
# 执行数据库表结构迁移
python manage.py makemigrations
python manage.py migrate
```

### 4. 快速生成测试账号 (推荐)
项目提供了一个自动化脚本，可以一键生成学生和管理员的测试账号：
```bash
python create_test_user.py
```
*生成的账号信息会在控制台输出。*

### 5. 启动本地服务器
```bash
python manage.py runserver
```
启动成功后，在浏览器访问：
- **前台页面 (学生/用户)**: `http://127.0.0.1:8000/`
- **后台管理 (管理员)**: `http://127.0.0.1:8000/admin/`

## 🧰 实用工具脚本

项目根目录下提供了几个便捷脚本：
- `create_test_user.py`：一键创建测试用的学生 (`student`/`123456`) 和管理员 (`admin`/`admin123`) 账号。
- `reset_password.py`：如果你忘记了某个测试账号的密码，可以运行此脚本通过终端快速重置为新密码。

## 🤝 贡献与参与
如果你觉得这个项目对你有帮助，欢迎 Fork 和 Star ⭐️！

## 📄 许可证
本项目采用 MIT License，可以自由用于学习、参考和二次开发。
