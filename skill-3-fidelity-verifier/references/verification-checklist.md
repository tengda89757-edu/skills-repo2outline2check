# 跨学科验证检查清单详细指南

## 声明类型分类

### 类型A: AI技术声明
涉及算法、模型、代码、性能的技术性声明。

**验证重点**:
- 代码实现存在性
- 算法逻辑一致性
- 性能数值准确性

### 类型B: 实证研究声明
涉及研究设计、样本、方法、结果的实证性声明。

**验证重点**:
- 数据/文档支持
- 统计计算正确性
- 伦理合规性

### 类型C: 跨学科声明
涉及理论整合、贡献、意义的跨学科声明。

**验证重点**:
- 两领域证据支持
- 整合逻辑合理性
- 贡献声明适度性

---

## AI技术声明验证清单

### 算法/模型声明

```
□ 算法名称和描述
  声明: "We propose [算法名称]..."
  验证:
  □ src/ 目录下存在对应实现
  □ 算法步骤与描述一致
  □ 参数设置与声明一致
  证据格式: src/algorithm.py:L10-L50

□ 模型架构
  声明: "Our model consists of..."
  验证:
  □ model.py 或类似文件存在
  □ 层结构与描述一致
  □ 超参数与配置一致
  证据格式: src/model.py:L20-L80

□ 形式化定义
  声明: 公式和符号定义
  验证:
  □ 符号与代码变量对应
  □ 公式实现正确
  □ 假设条件在代码中体现
  证据格式: src/[相关文件]:L[X]-L[Y]

□ 复杂度分析
  声明: 时间/空间复杂度
  验证:
  □ 分析有代码依据
  □ 或有理论推导文档
  证据格式: notebooks/analysis.ipynb:cell-X
```

---

### 性能声明

```
□ 主要性能指标
  声明: "Our method achieves XX.X% accuracy..."
  验证:
  □ results/ 目录下存在结果文件
  □ 数值精确匹配
  □ 计算方法正确
  证据格式: results/main.csv:L5

□ 基线对比
  声明: "We outperform [baseline] by X%..."
  验证:
  □ 基线结果存在
  □ 差值计算正确
  □ 对比条件公平
  证据格式: results/comparison.csv

□ 统计显著性
  声明: "p < 0.05" 或 "95% CI [...]"
  验证:
  □ 统计检验代码存在
  □ 计算正确
  □ 报告格式规范
  证据格式: notebooks/stats.ipynb:cell-X

□ 效应量
  声明: "Cohen's d = X.XX"
  验证:
  □ 效应量计算代码存在
  □ 计算正确
  证据格式: src/analysis.py:L[X]-L[Y]
```

---

### 创新声明

```
□ 技术创新点
  声明: "Our key innovation is..."
  验证:
  □ 创新点对应代码存在
  □ 与现有方法区别清晰
  □ 创新实质可验证
  证据格式: src/[创新模块].py

□ 与现有工作对比
  声明: "Unlike [prior work], our method..."
  验证:
  □ 对比描述准确
  □ 引用正确
  □ 区别实质存在
  证据格式: 文献引用 + 代码对比

□ 开源声明
  声明: "We release code at..."
  验证:
  □ 仓库公开可访问
  □ 代码完整可用
  □ 文档充分
  证据格式: GitHub URL
```

---

## 实证研究声明验证清单

### 研究设计声明

```
□ 设计类型
  声明: "We conducted a randomized controlled trial..."
  验证:
  □ docs/methods.md 描述一致
  □ 实验设计代码支持
  □ 符合设计类型特征
  证据格式: docs/methods.md + experiments/

□ 预注册
  声明: "The study was pre-registered at..."
  验证:
  □ 预注册链接有效
  □ 预注册内容与实际一致
  □ 偏离预注册的内容说明
  证据格式: OSF/ClinicalTrials.gov链接

□ 报告指南
  声明: "We followed CONSORT guidelines..."
  验证:
  □ 报告内容符合指南
  □ 必需项目齐全
  □ 流程图存在（如需要）
  证据格式: 论文内容对照检查表
```

---

### 样本声明

```
□ 样本量
  声明: "A total of N participants..."
  验证:
  □ data/participants.csv 数量匹配
  □ 或样本量计算文档存在
  证据格式: data/participants.csv

□ 样本特征
  声明: "Mean age was XX.X years..."
  验证:
  □ 描述统计代码存在
  □ 数值匹配
  □ 分组数据正确
  证据格式: results/descriptive.csv

□ 纳入排除
  声明: "Participants were included if..."
  验证:
  □ 筛选记录存在
  □ 流程图数据匹配
  □ 排除原因记录
  证据格式: data/screening_log.csv

□ 抽样方法
  声明: "Participants were recruited through..."
  验证:
  □ 招募过程描述存在
  □ 方法与声明一致
  证据格式: docs/methods.md
```

---

### 效果声明

```
□ 主要效果
  声明: "Treatment group showed significantly higher..."
  验证:
  □ 统计检验结果存在
  □ 数值匹配
  □ 方法和声明一致
  证据格式: results/primary.csv

□ 效应量
  声明: "Effect size d = X.XX"
  验证:
  □ 效应量计算存在
  □ 计算正确
  □ 解释合理
  证据格式: src/analysis.py + results/

□ 置信区间
  声明: "95% CI [X.XX, X.XX]"
  验证:
  □ CI计算存在
  □ 计算正确
  证据格式: results/primary.csv

□ p值
  声明: "p < .05"
  验证:
  □ 统计检验代码存在
  □ 计算正确
  □ 报告规范
  证据格式: notebooks/stats.ipynb
```

---

### 伦理声明

```
□ IRB批准
  声明: "Approved by [Institution] IRB (Protocol #XXXX)"
  验证:
  □ IRB批准文件存在
  □ 批准号匹配
  □ 机构名称正确
  证据格式: docs/IRB_approval.pdf

□ 知情同意
  声明: "All participants provided informed consent"
  验证:
  □ 同意书模板存在
  □ 过程描述存在
  □ 特殊人群同意（如适用）
  证据格式: docs/consent_form.pdf

□ 数据保护
  声明: "Data were de-identified..."
  验证:
  □ 数据管理计划存在
  □ 脱敏代码/流程存在
  □ 存储安全措施说明
  证据格式: docs/data_management.md

□ 利益冲突
  声明: "The authors declare no conflicts of interest"
  验证:
  □ 利益冲突声明存在
  □ 资金来源说明
  证据格式: README.md 或 COI声明文件
```

---

## 跨学科声明验证清单

### 理论整合声明

```
□ AI理论基础
  声明: "Building on [AI theory]..."
  验证:
  □ 引用正确
  □ 理论解释准确
  □ 与方法对应
  证据格式: docs/theory.md + 参考文献

□ 领域理论基础
  声明: "Grounded in [domain theory]..."
  验证:
  □ 引用正确
  □ 理论解释准确
  □ 与设计对应
  证据格式: docs/theory.md + 参考文献

□ 理论整合框架
  声明: "We integrate [AI theory] with [domain theory]..."
  验证:
  □ 整合框架图存在
  □ 映射关系清晰
  □ 逻辑合理
  证据格式: docs/theory.md + figures/framework.png

□ 理论驱动假设
  声明: "Based on [theory], we hypothesize..."
  验证:
  □ 假设推导逻辑清晰
  □ 可检验
  □ 与实验对应
  证据格式: docs/hypotheses.md
```

---

### 贡献声明

```
□ 技术贡献
  声明: "We contribute a novel [algorithm/method]..."
  验证:
  □ 代码实现存在
  □ 与现有方法区别清晰
  □ 创新实质可验证
  证据格式: src/ + 对比分析

□ 领域贡献
  声明: "We provide evidence for..."
  验证:
  □ 实证结果存在
  □ 领域价值可论证
  □ 与领域问题对应
  证据格式: results/ + 领域分析

□ 跨学科贡献
  声明: "We bridge [AI field] and [domain field]..."
  验证:
  □ 两领域证据存在
  □ 整合价值可论证
  □ 不过度声明
  证据格式: docs/theory.md + 两领域分析

□ 实践贡献
  声明: "Our system can be used for..."
  验证:
  □ 实施可行性论证
  □ 用户/利益相关者反馈
  □ 实践价值论证
  证据格式: deployment/ 或 user_feedback/
```

---

## 领域专属验证清单

### AI+教育验证

```
□ 学习效果声明
  声明: "Students improved by X%..."
  验证:
  □ 学习评估数据存在
  □ 前后测对比正确
  □ 效应量报告
  证据格式: results/learning_outcomes.csv

□ 教育理论应用
  声明: "Based on [learning theory]..."
  验证:
  □ 理论到设计的映射清晰
  □ 实施符合理论原则
  □ 理论验证讨论
  证据格式: docs/theory.md + 设计文档

□ 教育伦理
  声明: "Student data were protected..."
  验证:
  □ 学生/家长同意文件
  □ 数据保护措施
  □ 学校批准文件
  证据格式: docs/consent/ + data_management.md

□ 实施可行性
  声明: "Teachers found the system useful..."
  验证:
  □ 教师反馈数据
  □ 实施过程记录
  □ 可行性讨论
  证据格式: results/teacher_feedback.csv
```

---

### AI+医学验证

```
□ 临床验证声明
  声明: "Validated in clinical settings..."
  验证:
  □ 临床试验注册
  □ 验证数据存在
  □ 符合报告指南
  证据格式: ClinicalTrials.gov + results/

□ 诊断性能声明
  声明: "Sensitivity = XX%, Specificity = XX%..."
  验证:
  □ 混淆矩阵数据
  □ 计算正确
  □ 置信区间报告
  证据格式: results/diagnostic_performance.csv

□ 安全性声明
  声明: "No adverse events were observed..."
  验证:
  □ 安全性监控记录
  □ 不良事件报告
  □ 风险讨论
  证据格式: results/safety_report.pdf

□ 临床意义
  声明: "The system has clinical utility for..."
  验证:
  □ 临床效用分析
  □ 医生接受度数据
  □ 工作流整合讨论
  证据格式: results/clinical_utility.md
```

---

### AI+社科验证

```
□ 社科方法论声明
  声明: "Using [qualitative/quantitative/mixed] methods..."
  验证:
  □ 方法论描述充分
  □ 符合社科规范
  □ 方法选择合理
  证据格式: docs/methodology.md

□ 定性发现（如适用）
  声明: "Participants reported..."
  验证:
  □ 访谈/焦点小组记录
  □ 编码过程文档
  □ 引用支持
  证据格式: data/qualitative/ + analysis/

□ 社会影响声明
  声明: "Our findings have implications for..."
  验证:
  □ 影响讨论充分
  □ 论证合理
  □ 不过度推广
  证据格式: discussion/impact.md

□ 伦理审查
  声明: "Approved by ethics committee..."
  验证:
  □ 伦理批准文件
  □ 参与者保护措施
  □ 敏感话题处理
  证据格式: docs/ethics_approval.pdf
```

---

## 高风险声明专项验证

### Critical Fail 判定标准

```
AI技术维度 Critical Fail:
1. 核心算法无代码实现
2. 性能声明无任何结果支持
3. 与基线对比条件明显不公平
4. 创新声明完全无法验证

实证研究维度 Critical Fail:
1. 声称有人类被试但无IRB批准
2. 效果声明无任何统计支持
3. 样本声明与数据严重不符
4. 伦理声明虚假

跨学科维度 Critical Fail:
1. 理论整合完全无依据
2. 贡献声明严重过度夸大
3. 两领域证据完全缺失
```

---

## 证据记录格式

### 标准格式

```
| 声明内容 | 验证结果 | 精确证据位置 | 备注 |
|----------|----------|--------------|------|
| [声明摘要] | ✅/⚠️/❌ | [文件路径]:[行号] | [说明] |
```

### 证据位置格式

```
代码文件: src/method.py:L10-L50
数据文件: results/main.csv:L5 (数值: 95.3)
文档文件: docs/methods.md:L30-L45
图像文件: figures/framework.png
Notebook: notebooks/analysis.ipynb:cell-3
PDF文件: docs/IRB_approval.pdf
```

---

## 执行流程

```
Step 1: 解析大纲
├── 提取所有声明性语句
├── 分类声明类型（AI/实证/跨学科）
└── 识别需要验证的关键点

Step 2: 仓库扫描
├── 获取完整目录结构
├── 识别关键文件位置
└── 建立文件索引

Step 3: 分类验证
├── AI技术声明验证
├── 实证研究声明验证
├── 跨学科声明验证
└── 领域专属验证

Step 4: 汇总判定
├── 统计验证结果
├── 识别Critical Fail
├── 生成修正建议
└── 输出最终判定
```
