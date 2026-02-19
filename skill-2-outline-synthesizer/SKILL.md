---
name: ai-empirical-outline-synthesizer
description: |
  AI+实证研究代码仓库转论文大纲合成器。从代码仓库中自动提炼结构化信息，生成符合跨学科期刊/会议标准的完整论文大纲，同时满足AI技术报告和实证研究论文的规范要求。
  Use when: 从代码生成论文大纲、跨学科论文写作规划、期刊投稿准备
---

# AI + Empirical Research Outline Synthesizer

从代码仓库自动生成符合跨学科标准的论文大纲。

## 核心定位

该Skill专为**AI+实证研究**论文设计，支持以下期刊/会议类型：

| 类型 | 代表性期刊/会议 | 特点 |
|------|----------------|------|
| AI顶会 | NeurIPS, ICLR, ICML, ACL | 强调技术创新 |
| 教育期刊 | Computers & Education, BJET | 强调教育价值 |
| 医学期刊 | JAMIA, NPJ Digital Medicine | 强调临床验证 |
| 社科期刊 | JCSS, Computational Sociology | 强调方法论严谨 |
| 跨学科期刊 | Nature/Science子刊, PNAS | 强调综合贡献 |

---

## 前置条件

**必须先通过Skill 1检查，得分 ≥ 75分**

```
┌─────────────────────────────────────────┐
│  Skill 1: AI+Empirical Checker          │
│  Score: ≥ 75                            │
└─────────────────────────────────────────┘
              ↓ Pass
┌─────────────────────────────────────────┐
│  Skill 2: Outline Synthesizer           │
└─────────────────────────────────────────┘
```

---

## 输入要求

### 必需输入
| 输入项 | 格式 | 说明 |
|--------|------|------|
| GitHub仓库URL | string | 完整访问权限 |
| README.md | text | 完整内容 |
| 研究领域 | enum | education/medicine/social_science |
| 目标期刊/会议 | string | 决定大纲格式 |

### 可选输入
- IRB/伦理审批文件
- 预注册方案
- 作者贡献声明
- 已有论文草稿片段

---

## 输出格式

### 跨学科论文大纲

```markdown
# [Title]

## Abstract
<!-- 结构: 背景-方法-结果-意义 -->
<!-- 对应证据: README.md:L[X]-L[Y] -->

## 1. Introduction
<!-- 对应证据: README.md:L[X]-L[Y] -->
### 1.1 Background
### 1.2 Problem Statement
### 1.3 Research Questions/Hypotheses
### 1.4 Contributions

## 2. Literature Review
<!-- 对应证据: README.md:L[X]-L[Y] -->
### 2.1 AI/Technical Background
### 2.2 Domain-Specific Background
### 2.3 Interdisciplinary Research Gap

## 3. Theoretical Framework
<!-- 对应证据: docs/theory.md 或 README.md -->
### 3.1 AI Theory Foundation
### 3.2 Domain Theory Foundation
### 3.3 Integrated Framework

## 4. Methods
<!-- 对应证据: src/, configs/, docs/ -->
### 4.1 Research Design
### 4.2 AI System/Algorithm
### 4.3 Participants and Data
### 4.4 Measures and Instruments
### 4.5 Procedure
### 4.6 Data Analysis

## 5. Results
<!-- 对应证据: results/, experiments/ -->
### 5.1 Descriptive Statistics
### 5.2 Primary Outcomes
### 5.3 Secondary Outcomes
### 5.4 AI System Performance
### 5.5 Exploratory Analyses

## 6. Discussion
<!-- 对应证据: README.md:L[X]-L[Y] -->
### 6.1 Summary of Findings
### 6.2 Interpretation
### 6.3 Theoretical Implications
### 6.4 Practical Implications
### 6.5 Limitations
### 6.6 Future Directions

## 7. Conclusion
<!-- 对应证据: README.md:L[X]-L[Y] -->

## 8. Ethics Statement
<!-- 对应证据: ETHICS.md, IRB文件 -->

## References

## Appendices
<!-- 对应证据: appendix/, supplementary/ -->
### A. Supplementary Methods
### B. Supplementary Results
### C. Code and Data Availability
```

---

## 章节生成指南

### Title（标题）

#### 跨学科标题原则
- 同时体现AI方法和应用领域
- 突出跨学科贡献
- 避免过于技术化或过于应用化

#### 标题模板

**AI+教育**:
```
[AI Method] for [Educational Application]: A [Study Type]

示例:
- "Deep Learning for Automated Essay Scoring: A Randomized Controlled Trial"
- "Adaptive Learning Systems Using Knowledge Tracing: Effects on Mathematics Achievement"
- "Natural Language Processing in Education: A Systematic Review and Meta-Analysis"
```

**AI+医学**:
```
[AI System] for [Clinical Application]: [Validation Type]

示例:
- "Deep Learning for Diabetic Retinopathy Screening: A Prospective Validation Study"
- "Natural Language Processing for Clinical Documentation: A Multi-site Evaluation"
- "AI-Assisted Diagnosis in Radiology: A Systematic Review and Meta-Analysis"
```

**AI+社科**:
```
[AI Method] for [Social Phenomenon]: A [Methodological Approach]

示例:
- "Machine Learning for Predicting Social Outcomes: Challenges and Opportunities"
- "Computational Analysis of Political Discourse: A Mixed Methods Study"
- "AI and Social Inequality: A Critical Review and Research Agenda"
```

---

### Abstract（摘要）

#### 四段式结构（跨学科标准）

**第一段: 背景与问题**
```
[领域背景]. [具体问题]. [为何重要]. [现有方法局限].

示例 (AI+教育):
Automated writing feedback systems have shown promise in supporting student 
learning, yet their effectiveness in K-12 settings remains understudied. 
Existing systems often lack pedagogical grounding and fail to provide 
personalized feedback aligned with learning objectives.
```

**第二段: 方法**
```
We developed/tested [AI系统/方法], a [系统类型] that [核心功能]. 
Using [研究设计], we [研究对象/样本] [研究过程].

示例:
We developed WriteAssist, a deep learning-based writing feedback system 
grounded in cognitive apprenticeship theory. Using a cluster-randomized 
controlled trial, we evaluated the system with 1,200 students across 
24 schools over one academic semester.
```

**第三段: 结果**
```
[主要发现]. [量化结果]. [AI性能指标]. [统计显著性].

示例:
Students using WriteAssist showed significantly greater improvement in 
writing quality (d = 0.42, p < .001) compared to the control group. 
The system achieved 87% accuracy in error detection and 82% agreement 
with human raters on feedback quality.
```

**第四段: 意义**
```
These findings suggest [理论贡献]. [实践意义]. [推广限制].

示例:
These findings suggest that pedagogically-grounded AI systems can 
effectively support writing instruction. The results have implications 
for designing AI tools that integrate learning science principles. 
Limitations include the focus on English language arts in US schools.
```

---

### 1. Introduction（引言）

#### 跨学科引言结构

**1.1 Background**
```
% 对应证据: README.md:L[X]-L[Y]

结构:
1. 应用领域背景 (2-3段)
   - 领域重要性
   - 当前挑战
   - 社会需求

2. AI技术背景 (1-2段)
   - 相关AI技术发展
   - 技术机遇

3. 跨学科机遇 (1段)
   - AI与领域结合的潜力
   - 为何现在是时机
```

**1.2 Problem Statement**
```
% 对应证据: README.md:L[X]-L[Y]

结构:
1. 明确陈述研究问题
2. 说明问题的多维度
3. 解释为何需要跨学科方法

示例:
"Despite advances in AI-powered educational tools, three critical gaps 
remain: (1) limited empirical evidence of learning effectiveness, 
(2) insufficient integration of pedagogical theory, and (3) lack of 
attention to implementation barriers in real classrooms."
```

**1.3 Research Questions/Hypotheses**
```
% 对应证据: README.md:L[X]-L[Y], docs/hypotheses.md

格式:
Research Questions:
RQ1: [AI技术问题]
RQ2: [应用效果问题]
RQ3: [机制/过程问题]

Hypotheses (如适用):
H1: [假设1]
H2: [假设2]

示例:
RQ1: How does the proposed deep learning model perform in detecting 
     writing errors compared to existing systems?
RQ2: What is the effect of AI-generated feedback on student writing 
     quality compared to teacher feedback alone?
RQ3: Through what mechanisms does AI feedback influence student 
     revision behaviors?

H1: Students receiving AI feedback will show greater improvement in 
    writing quality than those receiving teacher feedback alone.
H2: The effect of AI feedback will be mediated by students' 
    self-regulation skills.
```

**1.4 Contributions**
```
% 对应证据: README.md:L[X]-L[Y], src/

跨学科贡献声明格式:

Our contributions are as follows:

1. **Technical Contribution**: We propose [AI方法], which [技术创新].
   % 对应证据: src/method.py:L[X]-L[Y]

2. **Empirical Contribution**: We provide [实证贡献], demonstrating 
   [实证发现].
   % 对应证据: results/main.csv

3. **Theoretical Contribution**: We integrate [理论整合], offering 
   [理论洞见].
   % 对应证据: docs/theory.md

4. **Practical Contribution**: We develop [实践贡献], enabling 
   [实践价值].
   % 对应证据: README.md, deployment/

5. **Open Science**: We release [代码/数据/材料] to facilitate 
   replication and extension.
   % 对应证据: GitHub仓库
```

---

### 2. Literature Review（文献综述）

#### 跨学科文献综述结构

**2.1 AI/Technical Background**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 相关AI技术综述
2. 技术发展脉络
3. 技术挑战与局限
4. 本研究的AI定位

注意:
- 使用领域研究者可理解的语言
- 避免过度技术化
- 突出与领域应用的关联
```

**2.2 Domain-Specific Background**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 应用领域核心概念
2. 领域主要理论框架
3. 领域研究方法传统
4. 领域实践挑战

注意:
- 引用领域经典文献
- 遵循领域术语规范
- 识别领域研究空白
```

**2.3 Interdisciplinary Research Gap**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 现有跨学科研究综述
2. 跨学科研究空白识别
3. 本研究如何填补空白
4. 跨学科贡献定位

关键问题:
- AI研究忽视了什么领域问题？
- 领域研究忽视了什么技术机遇？
- 跨学科研究有什么不足？
```

---

### 3. Theoretical Framework（理论框架）

#### 跨学科理论框架结构

**3.1 AI Theory Foundation**
```
% 对应证据: docs/theory.md 或 README.md

内容:
1. AI方法的理论基础
2. 技术假设说明
3. 模型选择依据

示例:
"Our AI system is grounded in the transformer architecture (Vaswani 
et al., 2017), which enables capturing long-range dependencies in 
text through self-attention mechanisms. We build upon recent advances 
in prompt-based learning (Liu et al., 2023) to adapt pre-trained 
language models for educational feedback generation."
```

**3.2 Domain Theory Foundation**
```
% 对应证据: docs/theory.md 或 README.md

内容:
1. 应用领域核心理论
2. 理论对设计的指导
3. 理论预测的假设

示例 (AI+教育):
"Our design is guided by cognitive apprenticeship theory (Collins 
et al., 1989), which emphasizes modeling, scaffolding, and fading 
in skill acquisition. We operationalize these principles through: 
(1) expert writing models, (2) graduated feedback complexity, and 
(3) progressive release of AI support."
```

**3.3 Integrated Framework**
```
% 对应证据: docs/theory.md

内容:
1. 理论整合框架图
2. AI与领域理论的映射
3. 跨学科假设推导

示例:
"Figure 1 presents our integrated framework, which maps AI 
capabilities to learning processes. The framework predicts that 
AI-generated feedback will be most effective when it: (1) aligns 
with cognitive load principles, (2) supports self-regulated 
learning cycles, and (3) maintains appropriate challenge levels."
```

---

### 4. Methods（方法）

#### 跨学科方法结构

**4.1 Research Design**
```
% 对应证据: docs/methods.md, configs/

内容:
1. 研究设计类型
2. 设计选择理由
3. 报告指南遵循声明

示例:
"We employed a cluster-randomized controlled trial design, with 
schools as the unit of randomization to prevent contamination. 
The study followed CONSORT guidelines and was pre-registered 
on OSF (https://osf.io/xxxxx)."
```

**4.2 AI System/Algorithm**
```
% 对应证据: src/, configs/

内容:
1. 系统架构概述
2. 算法形式化定义
3. 实现细节
4. 伪代码

格式:
\begin{algorithm}
\caption{[算法名称]}
\begin{algorithmic}
[伪代码]
\end{algorithmic}
\end{algorithm}

注意:
- 技术细节充分但不冗余
- 非技术读者可理解核心思想
- 提供架构图
```

**4.3 Participants and Data**
```
% 对应证据: data/, docs/participants.md

内容:
1. 参与者/数据来源
2. 纳入排除标准
3. 样本量依据
4. 人口统计学特征

表格格式:
| Characteristic | Treatment (n=XX) | Control (n=XX) |
|----------------|------------------|----------------|
| Age, M (SD)    | XX.X (X.X)       | XX.X (X.X)     |
| Female, n (%)  | XX (XX%)         | XX (XX%)       |
```

**4.4 Measures and Instruments**
```
% 对应证据: docs/measures.md, src/evaluation/

内容:
1. 主要结局变量
2. 测量工具说明
3. 信效度证据
4. AI评估指标

表格格式:
| Measure | Description | Reliability | Validity Evidence |
|---------|-------------|-------------|-------------------|
| [变量1] | [描述]      | α = .XX     | [效度证据]        |
```

**4.5 Procedure**
```
% 对应证据: docs/procedure.md, experiments/

内容:
1. 研究流程图
2. 干预/实验条件
3. 数据收集过程
4. 质量控制措施

流程图:
使用标准流程图（如CONSORT flow diagram）
```

**4.6 Data Analysis**
```
% 对应证据: src/analysis/, notebooks/

内容:
1. 统计分析方法
2. AI评估方法
3. 显著性水平
4. 软件说明

示例:
"We analyzed data using intention-to-treat principles. Primary 
outcomes were analyzed using mixed-effects models with random 
intercepts for schools. AI performance was evaluated using 
accuracy, F1-score, and AUC. All tests used α = .05 (two-tailed)."
```

---

### 5. Results（结果）

#### 跨学科结果结构

**5.1 Descriptive Statistics**
```
% 对应证据: results/descriptive.csv

内容:
1. 样本特征描述
2. 基线比较
3. 数据质量报告

表格格式:
| Variable | Overall (N=XX) | Treatment (n=XX) | Control (n=XX) | p |
|----------|----------------|------------------|----------------|---|
```

**5.2 Primary Outcomes**
```
% 对应证据: results/primary.csv

内容:
1. 主要假设检验结果
2. 效应量报告
3. 置信区间

表格格式:
| Outcome | Treatment | Control | Difference (95% CI) | d | p |
|---------|-----------|---------|---------------------|---|---|
```

**5.3 Secondary Outcomes**
```
% 对应证据: results/secondary.csv

内容:
1. 次要结局结果
2. 探索性分析
3. 亚组分析（如预指定）
```

**5.4 AI System Performance**
```
% 对应证据: results/ai_performance.csv

内容:
1. 模型性能指标
2. 与基线对比
3. 错误分析

表格格式:
| Metric | Our Model | Baseline 1 | Baseline 2 |
|--------|-----------|------------|------------|
| Accuracy | XX.X% | XX.X% | XX.X% |
| F1 | X.XX | X.XX | X.XX |
```

**5.5 Exploratory Analyses**
```
% 对应证据: results/exploratory/

内容:
1. 机制分析
2. 调节效应
3. 中介效应
4. 定性发现（如适用）
```

---

### 6. Discussion（讨论）

#### 跨学科讨论结构

**6.1 Summary of Findings**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 主要发现概述
2. 对研究问题的回答
3. 假设验证总结

注意:
- 简洁明了
- 不引入新信息
- 与结果一致
```

**6.2 Interpretation**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 结果解释
2. 与理论预期的对比
3. 意外发现讨论

跨学科视角:
- AI技术视角的解释
- 应用领域视角的解释
- 跨学科整合的解释
```

**6.3 Theoretical Implications**
```
% 对应证据: docs/theory.md

内容:
1. 对AI理论的贡献
2. 对领域理论的贡献
3. 对跨学科理论的贡献

示例:
"Our findings extend cognitive apprenticeship theory by demonstrating 
how AI can operationalize scaffolding at scale. The results also 
contribute to the AI literature by showing how pedagogical principles 
can improve the effectiveness of language models in educational contexts."
```

**6.4 Practical Implications**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 对实践的指导
2. 实施建议
3. 政策启示

利益相关者视角:
- 对从业者的启示
- 对政策制定者的启示
- 对用户的启示
```

**6.5 Limitations**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 方法局限
2. 样本局限
3. 测量局限
4. 推广限制

注意:
- 诚实承认局限
- 说明影响方向
- 提出改进方向
```

**6.6 Future Directions**
```
% 对应证据: README.md:L[X]-L[Y]

内容:
1. 技术改进方向
2. 研究扩展方向
3. 跨学科合作建议
```

---

### 7. Conclusion（结论）

```
% 对应证据: README.md:L[X]-L[Y]

结构:
1. 核心贡献总结
2. 跨学科意义
3. 最终声明

注意:
- 简洁有力
- 不引入新内容
- 适度不过度声明
```

---

### 8. Ethics Statement（伦理声明）

```
% 对应证据: ETHICS.md, IRB文件

内容:
1. 伦理审批信息
2. 知情同意过程
3. 数据保护措施
4. 利益冲突声明
5. 风险缓解措施

格式:
"This study was approved by [Institution] IRB (Protocol #XXXX). 
All participants provided informed consent. Data were de-identified 
and stored securely following [standard]. The authors declare no 
conflicts of interest."
```

---

## 执行约束

### 零幻觉原则
```
强制要求:
1. 每项声明必须有对应的仓库证据
2. 不允许推断或虚构
3. 缺失信息标记为"[待补充]"
4. 所有数值必须来自实际结果文件
```

### 跨学科平衡原则
```
强制要求:
1. AI技术内容和领域内容比例合理
2. 术语兼顾两领域读者
3. 引用平衡覆盖两领域
4. 贡献声明体现跨学科价值
```

### 证据映射格式
```
% 对应证据: [文件路径]:[行号/单元格]
或
% 对应证据: [文件路径] - [内容描述]
```

---

## 工作流集成

```
┌─────────────────────────────────────────────────────────────┐
│                    Pipeline Stage 2                         │
├─────────────────────────────────────────────────────────────┤
│  Input: Repository (passed Skill 1) + Target Venue          │
│     ↓                                                        │
│  ┌─────────────────────────────────────┐                    │
│  │  Skill 2: Outline Synthesizer       │                    │
│  │  - 识别目标期刊格式                  │                    │
│  │  - 生成跨学科平衡大纲                │                    │
│  │  - 映射仓库证据                      │                    │
│  └─────────────────────────────────────┘                    │
│     ↓                                                        │
│  Output: Paper Outline                                       │
│     ↓                                                        │
│  ┌─────────────────────────────────────┐                    │
│  │  Skill 3: Fidelity Verifier         │                    │
│  └─────────────────────────────────────┘                    │
└─────────────────────────────────────────────────────────────┘
```
