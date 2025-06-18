# 🌐 SNMP 网络监控平台

<div align="center">

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Next.js](https://img.shields.io/badge/Next.js-15-black.svg)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue.svg)](https://www.typescriptlang.org/)
[![Go](https://img.shields.io/badge/Go-1.23-00ADD8.svg)](https://golang.org/)
[![Docker](https://img.shields.io/badge/Docker-Ready-2496ED.svg)](https://www.docker.com/)
[![Production Ready](https://img.shields.io/badge/Production-Ready-success.svg)](#)

**[🇨🇳 中文](README.md) | [🇺🇸 English](README_EN.md)**

</div>

> 🚀 **企业级SNMP网络设备监控和管理平台** - 基于现代化技术栈构建的生产级解决方案

## ✨ 核心特色

### 🎯 **完整的监控功能**
- 📊 **设备发现与管理** - 自动发现和管理网络设备
- 📈 **实时监控** - 基于SNMP协议的实时数据采集
- 🚨 **智能告警** - 灵活的告警规则和通知系统
- 📁 **MIB管理** - 完整的MIB文件管理和OID浏览
- ⚙️ **配置生成** - 自动生成监控配置文件

### 🏭 **企业级特性**
- 🔐 **多用户支持** - 完整的用户权限管理系统
- 🌐 **多语言界面** - 支持中文和英文
- 📱 **响应式设计** - 完美支持桌面和移动设备
- 🎨 **现代化UI** - 基于最新设计规范的用户界面
- 🚀 **高性能** - 优化的数据库查询和缓存策略

### 🔧 **技术栈**
- **前端**: Next.js 15 + React 19 + TypeScript + Tailwind CSS
- **后端**: Go 1.23 + Gin + GORM + PostgreSQL
- **缓存**: Redis
- **部署**: Docker + Docker Compose
- **监控**: Prometheus + Grafana (可选)

## 🚀 快速开始

### 📋 系统要求

- **操作系统**: Linux / macOS / Windows
- **内存**: 4GB+ (推荐8GB)
- **存储**: 20GB+ 可用空间
- **软件**: Docker 20.10+ 和 Docker Compose 2.0+

### ⚡ 一键部署

```bash
# 1. 克隆项目
git clone https://github.com/your-username/snmp-mib-ui.git
cd snmp-mib-ui

# 2. 一键部署 (推荐)
./deploy.sh

# 3. 或使用生产级部署
./scripts/production-deployment.sh
```

### 🔧 手动部署

```bash
# 1. 复制环境配置
cp .env.example .env

# 2. 启动服务
docker-compose up -d

# 3. 等待服务就绪 (约2-3分钟)
docker-compose logs -f

# 4. 访问系统
open http://localhost:3000
```

### 📱 访问地址

部署完成后，您可以通过以下地址访问系统：

| 服务 | 地址 | 说明 |
|------|------|------|
| 🌐 **Web界面** | http://localhost:3000 | 主要管理界面 |
| 🔌 **API接口** | http://localhost:8080 | RESTful API |
| 🏥 **健康检查** | http://localhost:3000/api/health | 系统状态检查 |

## 📖 功能介绍

### 🎛️ 核心功能模块

#### 📊 设备管理 (`/devices`)
- **设备发现**: 自动扫描和发现网络中的SNMP设备
- **设备注册**: 手动添加设备和批量导入
- **状态监控**: 实时显示设备在线状态和关键指标
- **分组管理**: 按网段、类型或用途对设备进行分组

#### 📁 MIB管理 (`/mibs`)
- **文件上传**: 支持拖拽上传MIB文件
- **解析验证**: 自动解析MIB文件并验证语法
- **OID浏览**: 树形结构浏览OID对象
- **搜索功能**: 快速搜索MIB对象和描述

#### ⚙️ 配置生成 (`/config-gen`)
- **SNMP Exporter**: 生成Prometheus SNMP Exporter配置
- **Categraf**: 生成Categraf监控配置
- **模板管理**: 预定义和自定义配置模板
- **批量生成**: 支持批量设备配置生成

#### 🚨 告警管理 (`/alert-rules`)
- **规则编辑**: 可视化的告警规则编辑器
- **多种通知**: 邮件、短信、Webhook等通知方式
- **告警历史**: 完整的告警记录和统计
- **抑制规则**: 智能的告警抑制和聚合

#### 🛠️ 监控安装 (`/monitoring-installer`)
- **智能安装**: 自动检测和安装监控组件
- **远程部署**: SSH远程部署到目标主机
- **状态检查**: 实时监控安装进度和组件状态
- **配置管理**: 统一管理监控配置文件

#### 🔧 工具集 (`/tools`)
- **SNMP浏览器**: 实时查询SNMP设备数据
- **批量操作**: 批量设备配置和管理
- **配置对比**: 配置文件版本对比和差异分析
- **性能测试**: 设备响应性能测试工具

### 🎨 用户界面特性

- **🌓 主题切换**: 支持明亮和暗黑主题
- **📱 移动优化**: 完美的移动端体验
- **🔍 智能搜索**: 全局搜索和快速导航
- **📊 数据可视化**: 丰富的图表和仪表板
- **⌨️ 快捷键**: 完整的键盘快捷键支持

## 🏗️ 架构设计

### 📁 项目结构

```
snmp-mib-ui/
├── app/                    # Next.js 应用目录
│   ├── api/               # API 路由
│   ├── components/        # React 组件
│   ├── devices/           # 设备管理页面
│   ├── mibs/              # MIB管理页面
│   ├── config-gen/        # 配置生成页面
│   └── ...
├── backend/               # Go 后端服务
│   ├── controllers/       # 控制器
│   ├── models/           # 数据模型
│   ├── services/         # 业务逻辑
│   └── utils/            # 工具函数
├── components/            # 共享组件
├── lib/                  # 工具库
├── types/                # TypeScript 类型定义
├── docker-compose.yml    # Docker 编排文件
├── deploy.sh            # 一键部署脚本
└── README.md            # 项目文档
```

### 🌐 技术架构

```mermaid
graph TB
    A[Web Browser] --> B[Next.js Frontend]
    B --> C[Go Backend API]
    C --> D[PostgreSQL Database]
    C --> E[Redis Cache]
    C --> F[SNMP Devices]
    
    G[Docker Compose] --> B
    G --> C
    G --> D
    G --> E
    
    H[Monitoring Stack] --> I[Prometheus]
    H --> J[Grafana]
    H --> K[VictoriaMetrics]
```

## 🔧 配置说明

### 🌍 环境变量

```bash
# 数据库配置
DATABASE_URL=postgresql://user:pass@localhost:5432/snmp_platform
POSTGRES_DB=snmp_platform
POSTGRES_USER=snmp_user
POSTGRES_PASSWORD=your_password

# Redis配置
REDIS_URL=redis://localhost:6379

# 应用配置
NEXT_PUBLIC_API_URL=http://localhost:8080
JWT_SECRET=your-super-secret-jwt-key
API_PORT=8080

# SNMP配置
SNMP_DEFAULT_COMMUNITY=public
SNMP_DEFAULT_VERSION=2c
SNMP_TIMEOUT=5s
```

### 🐳 Docker配置

主要服务端口配置：

```yaml
services:
  frontend:     # 前端服务
    ports: ["3000:3000"]
  backend:      # 后端API
    ports: ["8080:8080"]
  postgres:     # 数据库
    ports: ["5432:5432"]
  redis:        # 缓存
    ports: ["6379:6379"]
```

## 📊 监控集成

### 🔗 支持的监控系统

- **Prometheus + SNMP Exporter**: 原生支持
- **Categraf**: 完整集成
- **VictoriaMetrics**: 推荐的时序数据库
- **Grafana**: 可视化仪表板
- **Zabbix**: 通过配置导出支持

### 📈 监控指标

- **设备指标**: CPU、内存、网络接口流量
- **系统指标**: 应用性能、响应时间、错误率
- **业务指标**: 设备在线率、告警统计
- **基础设施**: 数据库性能、缓存命中率

## 🔒 安全特性

- **认证授权**: JWT令牌 + 会话管理
- **权限控制**: 基于角色的访问控制(RBAC)
- **数据加密**: 传输和存储数据加密
- **安全审计**: 完整的操作日志记录
- **输入验证**: 严格的输入参数验证
- **SQL注入防护**: ORM框架安全查询

## 📚 文档

- **[部署指南](docs/deployment.md)**: 详细的部署说明
- **[API文档](docs/api.md)**: 完整的API接口文档
- **[开发指南](docs/development.md)**: 开发环境搭建
- **[用户手册](docs/user-guide.md)**: 功能使用说明
- **[常见问题](docs/faq.md)**: 常见问题解答

## 🤝 贡献指南

我们欢迎社区贡献！请查看 [CONTRIBUTING.md](CONTRIBUTING.md) 了解详情。

### 🐛 问题报告

- **Bug报告**: 通过 GitHub Issues 提交
- **功能建议**: 通过 GitHub Discussions 讨论
- **安全问题**: 请通过私有渠道联系

### 🔄 开发流程

1. Fork 项目
2. 创建功能分支 (`git checkout -b feature/AmazingFeature`)
3. 提交更改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 创建 Pull Request

## 📄 许可证

本项目基于 MIT 许可证开源 - 查看 [LICENSE](LICENSE) 文件了解详情。

## 🙏 致谢

感谢以下开源项目的支持：

- [Next.js](https://nextjs.org/) - React 全栈框架
- [Go](https://golang.org/) - 高性能后端语言
- [PostgreSQL](https://postgresql.org/) - 关系型数据库
- [Redis](https://redis.io/) - 内存数据库
- [Tailwind CSS](https://tailwindcss.com/) - CSS 框架

## 📞 联系方式

- **项目主页**: [GitHub Repository](https://github.com/your-username/snmp-mib-ui)
- **技术支持**: 通过 GitHub Issues 获取帮助
- **文档**: 查看 docs 目录下的详细文档

---

<div align="center">

**⭐ 如果这个项目对您有帮助，请给我们一个 Star！**

**🚀 SNMP网络监控平台 - 让网络监控变得简单高效**

</div>