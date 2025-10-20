# GEO Agent MVP 产品需求文档 (PRD)

## 1. 项目概述

### 1.1 项目背景
基于DL委托的GEO（生成式引擎优化）服务需求，开发一个半自动化的AI Agent工具，帮助客户在ChatGPT等AI助手的联网检索结果中优化品牌和产品的推荐率、曝光率，并促成流量转化。

### 1.2 产品定位
基于Dify平台的半自动化GEO分析工具，集成Gemini Pro模型、Semrush API和Google Analytics API，通过Docker容器化部署，提供从需求分析到报价确定的完整工作流程。

## 2. 用户需求分析

### 2.1 核心用户群体
- GEO服务提供商的分析师
- 数字营销顾问
- 品牌优化专员

### 2.2 用户痛点
- 手动分析效率低下
- 数据源分散，难以整合
- 缺乏标准化的分析流程
- 需要人工审核确保质量控制

### 2.3 DL特定要求
- ✅ 简单交互界面，降低使用门槛
- ✅ 半自动化流程，减少人工干预环节
- ✅ 优先使用Gemini Pro模型
- ✅ 通过API集成Semrush和Google Analytics
- ✅ 快速交付，3-4周内完成MVP
- ✅ Docker容器化部署，易于环境管理

## 3. 产品目标

### 3.1 业务目标
- 提高GEO分析效率50%以上
- 标准化分析流程，确保服务质量
- 降低人工错误率
- 提升客户满意度

### 3.2 产品目标
- 构建完整的GEO分析工作流
- 实现数据自动化采集和处理
- 提供智能化的分析建议
- 保持人工控制关键决策点

## 4. 功能需求

### 4.1 核心功能模块

#### 模块1: 需求Brief生成器
**功能描述**: 基于客户信息自动生成标准化需求Brief

**输入数据**:
- 客户基础信息（公司名称、行业、联系人等）
- 问卷调研结果
- Google Analytics流量数据截图或API数据
- 客户业务描述

**处理流程**:
1. 数据预处理和结构化
2. 调用Gemini Pro分析客户需求
3. 生成标准化Brief模板

**输出结果**:
- 结构化的客户档案
- 项目核心目标
- 现状分析报告
- 预算和周期建议

**人工介入点** (仅关键决策):
- Brief最终确认 (一键确认)

#### 模块2: 业务背景分析器
**功能描述**: 深度分析客户业务背景和竞争环境

**输入数据**:
- 客户Brief
- 公司官网URL
- 主要竞争对手信息
- 目标市场区域

**处理流程**:
1. 使用Gemini DeepResearch功能研究客户业务
2. 竞争对手分析
3. 行业趋势分析
4. 初步关键词清单生成

**输出结果**:
- 客户业务概览报告
- 竞争格局分析
- 市场定位分析
- 初步关键词清单（按优先级排序）

**人工介入点** (自动化处理):
- 无需人工介入，自动生成结果

#### 模块3: 关键词深度分析器
**功能描述**: 基于Semrush数据进行关键词扩展和用户意图分析

**输入数据**:
- 初步关键词清单
- 目标地区设置
- Semrush API配置

**处理流程**:
1. 调用Semrush API获取关键词数据
2. 关键词扩展和关联分析
3. 使用Gemini Pro进行用户意图分类
4. 搜索量和竞争度分析

**输出结果**:
- 完整关键词列表（包含搜索量、竞争度）
- 用户意图分类（信息型、商业型、事务型等）
- Query优先级排序（P0/P1/P2）
- 推荐Query List

**人工介入点** (智能推荐):
- Query List确认 (系统推荐+一键确认)

#### 模块4: AI产品测试器
**功能描述**: 自动化测试目标Query在各AI产品中的表现

**输入数据**:
- 确定的Query List
- 目标AI产品列表（ChatGPT、Claude、Gemini等）
- 测试地区配置（VPN设置）

**处理流程**:
1. 自动化访问各AI产品
2. 批量提交Query测试
3. 结果采集和存储
4. 品牌出现情况分析

**输出结果**:
- 各Query的AI回答结果
- 品牌提及情况统计
- 排名位置分析
- 竞争对手出现情况

**人工介入点** (自动化测试):
- 无需人工介入，自动执行测试

#### 模块5: 结果分析与建议器
**功能描述**: 基于测试结果生成优化建议和问题诊断

**输入数据**:
- AI产品测试结果
- 客户业务目标
- 竞争基准数据

**处理流程**:
1. 使用Gemini Pro分析测试结果
2. 问题优先级分类（P0紧急修正/P1机会抓取/P2优化提升）
3. 生成具体优化建议
4. ROI估算分析

**输出结果**:
- 问题诊断报告
- 优化建议列表（按优先级）
- 预期效果评估
- 执行难度评估

**人工介入点** (智能分析):
- 无需人工介入，自动生成建议

#### 模块6: 报价方案生成器
**功能描述**: 基于分析结果和客户预算生成报价方案

**输入数据**:
- 分析结果报告
- 客户预算范围
- 执行难度评估
- 预期工作量

**处理流程**:
1. 工作量评估
2. 资源需求计算
3. 报价方案生成
4. 执行计划制定

**输出结果**:
- 详细报价方案
- 项目执行计划
- 里程碑节点
- 预期交付成果

**人工介入点**:
- 全程人工决策
- 商务谈判支持
- 方案最终确认

### 4.2 辅助功能

#### 配置管理
- API密钥管理（Gemini、Semrush、Google Analytics）
- VPN配置管理
- 模板自定义设置

#### 数据管理
- 项目数据持久化存储
- 历史记录查询
- 数据导出功能（Excel、PDF）

#### 日志系统
- 操作日志记录
- 错误日志追踪
- 性能监控

## 5. 技术架构

### 5.1 整体架构（基于Dify）
```
┌─────────────────────────────────────────────────────────────────┐
│                          Docker Container                       │
├─────────────────────────────────────────────────────────────────┤
│                        Dify Platform                            │
│                                                                 │
│ - AI Agent 编排和对话界面                                    │
│ - 工作流自动化和API集成                                   │
│ - 知识库管理和模板系统                                   │
│ - 多模型支持和人工介入点                                │
│ - 定时任务调度和错误处理                                │
└─────────────────────────────────────────────────────────────────┘
                                 │
              ┌─────────────────────────────────────┐
              │            Data Layer               │
              │                                     │
              │ - PostgreSQL (项目数据)             │
              │ - Redis (缓存和队列)                │
              │ - Volume 挂载 (文件存储)            │
              │ - 配置文件持久化                    │
              └─────────────────────────────────────┘

              ┌─────────────────────────────────────┐
              │        External APIs              │
              │                                     │
              │ - Gemini Pro API                    │
              │ - Semrush API                       │
              │ - Google Analytics API              │
              │ - VPN 代理服务                      │
              └─────────────────────────────────────┘
```

### 5.2 技术栈
- **AI编排平台**: Dify
- **AI模型**: Gemini Pro API
- **数据库**: PostgreSQL + Redis
- **容器化**: Docker + Docker Compose
- **Web界面**: Dify内置界面
- **文件存储**: Docker Volume
- **监控日志**: Dify内置日志系统

### 5.3 关键组件（Dify架构）

#### Dify Agent 配置
```yaml
name: "GEO分析助手"
type: "chatbot"
model: "gemini-pro"
tools:
  - name: "Semrush数据获取"
    type: "api"
  - name: "Google Analytics数据获取"
    type: "api"
  - name: "项目状态管理"
    type: "function"
knowledge_base:
  - "GEO分析方法论"
  - "行业标准模板"
  - "客户案例库"
workflow:
  - "Brief生成流程"
  - "关键词分析流程"
  - "Query测试流程"
  - "报告生成流程"
```

## 6. 数据流设计

### 6.1 主数据流（优化后）
```
客户信息 → Brief生成 → 业务分析 → 关键词分析 → Query测试 → 结果分析 → 报价生成
    ↓         ↓                                   ↓                     ↓
  数据输入   Brief确认                        Query确认            最终报价确认
```

**人工介入点精简为3个关键节点**:
1. **Brief确认** - 确保客户需求理解正确
2. **Query确认** - 确认分析重点和测试范围
3. **报价确认** - 最终商务决策

### 6.2 数据存储结构
```sql
-- 项目表
CREATE TABLE projects (
    id INTEGER PRIMARY KEY,
    client_name TEXT,
    created_at TIMESTAMP,
    status TEXT,
    brief_data JSON,
    analysis_data JSON,
    keywords_data JSON,
    test_results JSON,
    final_proposal JSON
);

-- 关键词表
CREATE TABLE keywords (
    id INTEGER PRIMARY KEY,
    project_id INTEGER,
    keyword TEXT,
    search_volume INTEGER,
    competition_score REAL,
    intent_category TEXT,
    priority_level TEXT
);

-- 测试结果表
CREATE TABLE test_results (
    id INTEGER PRIMARY KEY,
    project_id INTEGER,
    query TEXT,
    ai_platform TEXT,
    response_text TEXT,
    brand_mentioned BOOLEAN,
    rank_position INTEGER,
    tested_at TIMESTAMP
);
```

### 6.3 API集成规范

#### Gemini Pro API集成
```python
class GeminiClient:
    def __init__(self, api_key):
        self.api_key = api_key
        self.client = genai.GenerativeModel('gemini-pro')

    def analyze_brief(self, client_data):
        prompt = self.build_brief_prompt(client_data)
        response = self.client.generate_content(prompt)
        return self.parse_brief_response(response)

    def analyze_keywords(self, keywords_data):
        prompt = self.build_keyword_prompt(keywords_data)
        response = self.client.generate_content(prompt)
        return self.parse_keyword_response(response)
```

#### Semrush API集成
```python
class SemrushClient:
    def __init__(self, api_key):
        self.api_key = api_key
        self.base_url = "https://api.semrush.com/"

    def get_keyword_overview(self, keyword, database="us"):
        params = {
            "type": "phrase_this",
            "key": self.api_key,
            "phrase": keyword,
            "database": database
        }
        return self.make_request(params)

    def get_related_keywords(self, keyword, limit=100):
        params = {
            "type": "phrase_related",
            "key": self.api_key,
            "phrase": keyword,
            "export_columns": "Ph,Nq,Cp,Co",
            "display_limit": limit
        }
        return self.make_request(params)
```

## 7. 人工介入点设计

### 7.1 介入点类型

#### 确认类介入
- **触发条件**: 系统生成结果需要用户确认
- **交互方式**: 显示结果 + Y/N确认
- **示例**: Brief生成后的内容确认

#### 选择类介入
- **触发条件**: 多个选项需要用户选择
- **交互方式**: 列表选择 + 数字输入
- **示例**: 关键词优先级调整

#### 编辑类介入
- **触发条件**: 内容需要用户修改
- **交互方式**: 文本编辑器调用
- **示例**: Brief内容修改

#### 决策类介入
- **触发条件**: 关键业务决策点
- **交互方式**: 详细说明 + 多选项决策
- **示例**: 最终报价方案确定

### 7.2 介入点实现
```python
class InterventionPoint:
    def __init__(self, name, type, description):
        self.name = name
        self.type = type  # confirm, select, edit, decide
        self.description = description

    def execute(self, data, context):
        if self.type == "confirm":
            return self.confirm_data(data)
        elif self.type == "select":
            return self.select_option(data, context)
        elif self.type == "edit":
            return self.edit_data(data)
        elif self.type == "decide":
            return self.make_decision(data, context)
```

## 8. MVP功能优先级

### P0 (核心功能 - 第一阶段)
1. ✅ 需求Brief生成器
2. ✅ 基础业务分析
3. ✅ 关键词收集和分析
4. ✅ 简单AI测试功能
5. ✅ 基础人工介入点

### P1 (重要功能 - 第二阶段)
1. 完整的Semrush API集成
2. 多AI平台自动化测试
3. 高级分析和建议生成
4. 数据可视化展示
5. 报价方案生成

### P2 (优化功能 - 第三阶段)
1. Google Analytics集成
2. 高级数据分析
3. 自定义模板系统
4. 批量项目管理
5. 性能优化

## 9. 技术实现方案

### 9.1 项目结构（Docker容器化）
```
geo-agent-platform/
├── docker-compose.yml          # 容器编排配置
├── .env                        # 环境变量配置
├── dify/
│   ├── dsl/                   # Dify应用配置
│   │   ├── geo-agent.yml      # Agent配置文件
│   │   └── workflows/         # 工作流定义
│   └── knowledge-base/        # 知识库文件
├── data/
│   ├── postgres/              # 数据库数据
│   ├── redis/                 # 缓存数据
│   └── uploads/               # 文件上传
├── config/
│   ├── nginx.conf             # 反向代理配置
│   └── init-scripts/          # 初始化脚本
└── docs/
    ├── deployment.md          # 部署文档
    └── user-guide.md          # 使用指南
```

### 9.2 交互界面设计（Dify Web界面）

#### 主要交互流程:
1. **访问Dify界面**: http://localhost/geo-agent
2. **对话式交互**: 自然语言描述客户需求
3. **确认节点**: 系统自动弹出确认界面
4. **进度跟踪**: 实时显示工作流执行状态
5. **结果下载**: 一键下载分析报告

#### 示例对话:
```
用户: 我需要为JollyMax游戏公司做GEO分析
助手: 我来帮您分析JollyMax的GEO需求。请提供以下信息：
      1. 公司基本信息
      2. 目标市场区域
      3. 主要竞争对手
      4. Google Analytics数据

用户: [上传相关文件]
助手: 信息已收集完成，正在生成需求Brief...
      [显示生成的Brief]
      请确认信息是否准确？ [确认] [修改]

用户: 确认
助手: Brief已确认，开始执行完整分析流程...
      [显示进度条和各阶段状态]
```

### 9.3 Docker配置文件

#### docker-compose.yml
```yaml
version: '3.8'
services:
  # Dify服务
  dify-api:
    image: langgenius/dify-api:latest
    environment:
      - SECRET_KEY=${SECRET_KEY}
      - DB_USERNAME=postgres
      - DB_PASSWORD=${POSTGRES_PASSWORD}
      - REDIS_HOST=redis
    depends_on:
      - postgres
      - redis
    volumes:
      - ./dify:/app/dsl

  dify-web:
    image: langgenius/dify-web:latest
    ports:
      - "80:3000"
    depends_on:
      - dify-api

  # 数据库服务
  postgres:
    image: postgres:15
    environment:
      - POSTGRES_DB=geo_agent
      - POSTGRES_USER=postgres
      - POSTGRES_PASSWORD=${POSTGRES_PASSWORD}
    volumes:
      - ./data/postgres:/var/lib/postgresql/data

  redis:
    image: redis:7-alpine
    volumes:
      - ./data/redis:/data

volumes:
  postgres_data:
  redis_data:
```

#### .env环境变量
```bash
# 数据库配置
POSTGRES_PASSWORD=your_secure_password

# API密钥
GEMINI_API_KEY=your_gemini_api_key
SEMRUSH_API_KEY=your_semrush_api_key
GOOGLE_ANALYTICS_KEY=your_ga_api_key

# Dify配置
SECRET_KEY=your_secret_key_here
```

## 10. 项目计划

### 10.1 开发阶段（3-4周）

#### 第1-2周: 环境搭建和基础配置
- [x] Docker环境搭建和容器配置
- [x] Dify平台部署和基础配置
- [ ] 数据库和Redis缓存配置
- [ ] 基础API集成测试
- [ ] 知识库和模板初始化

#### 第2-3周: 核心工作流开发
- [ ] Dify Agent对话流程设计
- [ ] Brief生成工作流开发
- [ ] 关键词分析功能实现
- [ ] Query测试自动化流程
- [ ] 3个人工介入点实现

#### 第4周: 集成测试和优化
- [ ] 端到端流程测试
- [ ] 性能优化和错误处理
- [ ] 用户界面优化
- [ ] 部署文档和用户指南
- [ ] 交付和培训

### 10.2 快速交付计划
- **MVP版本**: 3周后交付核心功能
- **完整版本**: 4周后交付全部功能
- **部署和培训**: 第4周并行进行

### 10.3 关键里程碑
- **第2周末**: 平台环境就绪，可演示DL基础交互
- **第3周末**: 核心工作流完成，可处理完整案例
- **第4周末**: 生产就绪，完成部署和文档

## 11. 环境部署方案

### 11.1 Docker部署架构

#### 系统要求
- **操作系统**: Linux/macOS/Windows (支持Docker)
- **内存**: 最小8GB，推荐16GB
- **存储**: 最小50GB可用空间
- **网络**: 需要访问外部API (Gemini、Semrush等)

#### 一键部署脚本
```bash
#!/bin/bash
# deploy.sh - GEO Agent一键部署脚本

echo "开始部署GEO Agent平台..."

# 检查Docker环境
if ! command -v docker &> /dev/null; then
    echo "请先安装Docker"
    exit 1
fi

# 克隆项目配置
git clone https://github.com/your-org/geo-agent-platform.git
cd geo-agent-platform

# 复制环境变量模板
cp .env.example .env
echo "请编辑.env文件配置API密钥"

# 启动所有服务
docker-compose up -d

# 等待服务启动
echo "等待服务启动..."
sleep 30

# 导入初始配置
docker-compose exec dify-api python manage.py import_dsl /app/dsl/geo-agent.yml
docker-compose exec n8n n8n import:workflow /home/node/.n8n/workflows/

echo "部署完成！访问 http://localhost 开始使用"
```

#### 服务健康检查
```bash
# health-check.sh
#!/bin/bash

services=("dify-web" "dify-api" "postgres" "redis")

for service in "${services[@]}"; do
    if docker-compose ps $service | grep -q "Up"; then
        echo "✅ $service 运行正常"
    else
        echo "❌ $service 运行异常"
    fi
done
```

### 11.2 环境配置管理

#### 开发环境
```yaml
# docker-compose.dev.yml
version: '3.8'
services:
  dify-api:
    environment:
      - DEBUG=true
      - LOG_LEVEL=debug
    volumes:
      - ./dify:/app/dsl:rw  # 开发时可写
```

#### 生产环境
```yaml
# docker-compose.prod.yml
version: '3.8'
services:
  dify-api:
    environment:
      - DEBUG=false
      - LOG_LEVEL=info
    restart: unless-stopped
    volumes:
      - ./dify:/app/dsl:ro  # 生产环境只读
```

### 11.3 备份和恢复

#### 数据备份脚本
```bash
#!/bin/bash
# backup.sh
DIR="backup-$(date +%Y%m%d-%H%M%S)"
mkdir -p $DIR

# 备份数据库
docker-compose exec -T postgres pg_dump -U postgres geo_agent > $DIR/database.sql

# 备份配置文件
cp -r ./dify $DIR/
cp -r ./n8n $DIR/
cp .env $DIR/

tar -czf "$DIR.tar.gz" $DIR
rm -rf $DIR
echo "备份完成: $DIR.tar.gz"
```

## 12. 风险评估与应对

### 12.1 技术风险
- **API限制**: Gemini和Semrush API的调用限制
  - 应对: 实现请求队列和重试机制
- **数据准确性**: AI分析结果的准确性
  - 应对: 多重人工验证点
- **网络稳定性**: VPN和国际API访问稳定性
  - 应对: 错误重试和降级处理

### 12.2 业务风险
- **用户接受度**: CLI界面的用户体验
  - 应对: 详细的使用文档和培训
- **流程适应**: 现有工作流程的改变
  - 应对: 渐进式迁移和并行运行

## 13. 成功指标

### 13.1 功能指标
- ✅ 完整流程执行成功率 > 95%
- ✅ 人工介入点响应时间 < 30秒
- ✅ API调用成功率 > 99%
- ✅ 数据准确性 > 90%

### 13.2 业务指标
- ✅ 分析效率提升 > 50%
- ✅ 用户满意度 > 4.5/5
- ✅ 错误率降低 > 70%
- ✅ 项目交付时间缩短 > 30%

## 15. 后续迭代规划

### 版本2.0规划
- 更多AI平台支持
- 高级数据可视化
- 自动化报告生成
- 多语言支持

### 版本3.0规划
- 机器学习优化建议
- 实时监控面板
- 企业级部署支持
- API开放平台

---

---

**文档版本**: v1.0
**最后更新**: 2025-01-20
**技术架构**: Dify + Docker
**负责人**: GEO Agent开发团队