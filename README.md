根据您提供的项目文件结构和配置文件（`pom.xml`, `package.json`），我为您编写了一份完整且详细的 **README.md** 文档。

这份文档涵盖了项目简介、技术栈、功能模块、环境要求、安装运行步骤以及项目结构说明。

---

# Nebula Commerce (星云电商系统)

## 📖 项目简介 | Project Overview

**Nebula Commerce** 是一个基于前沿技术栈构建的现代化全栈电商平台。项目采用前后端分离架构，致力于提供高性能、高扩展性的电商解决方案。

系统由以下三个核心子工程组成：

1. **`nebula-commerce` (后端 API)**：基于 Spring Boot 3.3 和 JDK 21 构建的核心业务服务，集成了 Spring Security、MyBatis Plus 和 Redis。
2. **`nebula-admin` (管理后台)**：基于 Vue 3 + TypeScript + Element Plus 构建的现代化后台管理系统，提供商品、订单、营销及用户管理功能。
3. **`nebula-store` (用户商城)**：面向终端用户的 C 端商城前台，采用最新的 Vue 3 技术栈，提供流畅的购物体验。

---

## 🛠 技术栈 | Tech Stack

### 🔙 后端 (nebula-commerce)

| 技术 | 说明 | 版本 |
| --- | --- | --- |
| **Java** | 编程语言 | JDK 21 |
| **Spring Boot** | 核心框架 | 3.3.0 |
| **MyBatis Plus** | ORM 框架 | 3.5.6 |
| **MySQL** | 关系型数据库 | 8.0+ |
| **Redis** | 缓存中间件 | Latest |
| **Spring Security** | 安全认证框架 | (Spring Boot Starter) |
| **JWT** | Token 认证 | 0.12.5 |
| **Hutool** | Java 工具库 | 5.8.26 |
| **Lombok** | 代码简化工具 | Latest |

### 🖥️ 管理后台 (nebula-admin)

| 技术 | 说明 | 版本 |
| --- | --- | --- |
| **Vue.js** | 前端框架 | 3.4.21 |
| **TypeScript** | 编程语言 | 5.4.5 |
| **Vite** | 构建工具 | 5.2.8 |
| **Element Plus** | UI 组件库 | 2.7.0 |
| **Pinia** | 状态管理 | 2.1.7 |
| **ECharts** | 数据可视化 | 5.5.1 |
| **Axios** | HTTP 客户端 | 1.6.8 |

### 🛍️ 用户商城 (nebula-store)

| 技术 | 说明 | 版本 |
| --- | --- | --- |
| **Vue.js** | 前端框架 | 3.x |
| **TypeScript** | 编程语言 | ~5.9.3 |
| **Vite (Rolldown)** | 构建工具 | 7.2.5 (Rolldown-vite) |
| **Element Plus** | UI 组件库 | 2.13.0 |
| **Swiper** | 轮播图插件 | 11.1.5 |
| **Pinia** | 状态管理 | 3.0.4 |

---

## 🧩 功能模块 | Features

根据代码结构分析，系统包含以下核心模块：

### 1. 认证与权限 (Auth & System)

* **用户注册/登录**：支持普通用户与管理员登录，集成 JWT 令牌认证。
* **权限控制**：基于角色的访问控制 (RBAC)。
* **系统日志**：记录操作日志 (SysLog)。
* **系统公告**：发布和管理平台通知 (Notice)。

### 2. 商品中心 (Product)

* **商品管理**：商品的增删改查、上下架管理。
* **类目管理**：多级商品分类配置。
* **SKU 管理**：商品规格与库存管理。
* **商品评价**：用户对商品的评论与回复管理。

### 3. 营销中心 (Marketing)

* **优惠券**：优惠券的创建、发放与领取逻辑。
* **秒杀活动**：高并发场景下的秒杀商品配置与管理 (Seckill)。

### 4. 订单中心 (Order)

* **购物车**：添加商品、数量调整、购物车结算。
* **订单流程**：创建订单、订单支付、发货、收货流程。
* **支付模块**：集成支付接口 (PayController)。

### 5. 会员中心 (Member)

* **用户管理**：会员信息维护。
* **收货地址**：用户多地址管理。
* **商家管理**：商户入驻与管理 (Merchant)。

---

## 🚀 快速开始 | Getting Started

### 环境要求 (Prerequisites)

* **JDK**: 21
* **Node.js**: 18+ (建议 20.x)
* **MySQL**: 8.0+
* **Redis**: 5.0+
* **Maven**: 3.6+

### 1. 后端启动 (Backend)

1. 克隆项目并进入后端目录：
```bash
cd nebula-commerce

```


2. 配置数据库：
修改 `src/main/resources/application.yml` (或 `.properties`)，配置您的 MySQL 和 Redis 连接信息。
3. 导入数据库脚本（如有 `sql` 文件）。
4. 运行服务：
```bash
mvn spring-boot:run

```



### 2. 管理后台启动 (Admin Frontend)

1. 进入管理端目录：
```bash
cd nebula-admin

```


2. 安装依赖：
```bash
npm install
# 或者使用 pnpm
pnpm install

```


3. 启动开发服务器：
```bash
npm run dev

```



### 3. 商城前台启动 (Store Frontend)

1. 进入商城目录：
```bash
cd nebula-store

```


2. 安装依赖：
```bash
npm install

```


3. 启动开发服务器：
```bash
npm run dev

```



---

## 📂 项目结构 | Project Structure

```text
nebulapuls8888/
├── nebula-commerce/             # ☕ 后端工程 (Spring Boot)
│   ├── src/main/java/com/nebula/commerce/
│   │   ├── infrastructure/      # 基础设施 (Config, Security, Web Utils)
│   │   ├── modules/             # 业务模块
│   │   │   ├── auth/            # 认证模块
│   │   │   ├── marketing/       # 营销模块 (Coupon, Seckill)
│   │   │   ├── member/          # 会员模块 (User, Merchant, Address)
│   │   │   ├── order/           # 订单模块 (Cart, Pay)
│   │   │   ├── product/         # 商品模块 (Category, Review)
│   │   │   └── system/          # 系统模块 (Log, Notice)
│   └── pom.xml                  # Maven 依赖配置
│
├── nebula-admin/                # 🖥️ 管理后台 (Vue 3)
│   ├── src/
│   │   ├── api/                 # API 接口定义
│   │   ├── layout/              # 布局组件
│   │   ├── stores/              # Pinia 状态库
│   │   ├── views/               # 页面视图 (Dashboard, Login, System...)
│   │   └── utils/               # 工具函数
│   ├── vite.config.ts           # Vite 配置
│   └── package.json
│
└── nebula-store/                # 📱 用户商城 (Vue 3)
    ├── src/
    │   ├── api/                 # 商城 API
    │   ├── components/          # 公共组件 (Header, EmptyState)
    │   ├── views/               # 页面视图 (Home, Cart, Profile, ProductDetail...)
    │   └── stores/              # 状态管理
    ├── vite.config.ts           # Vite (Rolldown) 配置
    └── package.json

```

---

## 🤝 贡献指南 | Contribution

欢迎提交 Pull Requests 或 Issues 来改进本项目。

1. Fork 本仓库
2. 新建 Feat_xxx 分支
3. 提交代码
4. 新建 Pull Request

---

## 📄 版权说明 | License

本项目采用 MIT 许可证，详情请参阅项目中的 LICENSE 文件。
