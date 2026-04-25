基于 FastAPI 的居家血压监测系统后端
一个为居家场景设计的血压监测系统后端服务，提供用户管理、血压数据记录与趋势分析等核心功能，支持后续扩展移动端或 Web 前端。
📌 项目简介
本项目为居家血压监测系统的后端实现，基于 Python + FastAPI 开发，提供了用户认证、血压数据增删改查、历史趋势分析、异常提醒等接口。可对接血压计硬件、小程序 / APP 前端，帮助用户长期管理血压健康数据。
🛠️ 技术栈
语言：Python 3.8+
框架：FastAPI
数据库：MySQL（可替换为 SQLite、PostgreSQL）
认证：JWT
依赖管理：requirements.txt
📁 项目结构
plaintext
elder-hypertension-monitor/
├── api/
│   ├── __init__.py
│   ├── auth.py         # 用户认证相关接口（登录、注册）
│   └── device.py       # 设备与血压数据接口
├── service/
│   ├── auth_service.py # 用户业务逻辑
│   ├── bp_service.py   # 血压数据业务逻辑
│   └── push_service.py  # 推送提醒逻辑
├── utils/
│   ├── db.py           # 数据库连接工具
│   ├── jwt_util.py     # JWT 生成与校验
│   └── result.py       # 统一响应格式封装
├── main.py             # 项目入口
├── requirements.txt    # 依赖清单
└── sql.sql             # 数据库初始化脚本
✨ 功能特性
用户管理
用户注册 / 登录
JWT 身份认证与权限控制
血压数据管理
单条 / 批量血压数据录入
历史数据查询与分页
血压数据趋势统计（周 / 月 / 年）
健康分析
血压等级自动判定（正常 / 偏高 / 高血压）
异常血压记录提醒
扩展能力
支持对接蓝牙血压计硬件
支持小程序 / APP 前端对接
可扩展推送提醒、数据导出等功能
🚀 快速开始
1. 安装依赖
bash
运行
pip install -r requirements.txt
2. 初始化数据库
执行 sql.sql 脚本，创建所需的数据库表（用户表、血压记录表等）。
3. 配置数据库连接
在 utils/db.py 中修改你的数据库配置：
python
运行
DB_CONFIG = {
    "host": "localhost",
    "user": "你的数据库用户名",
    "password": "你的数据库密码",
    "database": "elder_monitor"
}
4. 启动服务
bash
运行
python main.py
