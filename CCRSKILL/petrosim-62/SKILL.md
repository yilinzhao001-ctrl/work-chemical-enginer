---
name: petrosim-62
description: >-
  Petro-SIM v6.2 process simulation assistant. Helps with building refinery simulations,
  configuring unit operations (columns, reactors, heat exchangers), stream management,
  fluid packages, reactions, and oil characterization. Use when users mention Petro-SIM,
  refining simulation, distillation columns, catalytic reformers, FCC, hydrocrackers,
  or general process engineering questions.
---

# Petro-SIM v6.2 Assistant

帮助你使用 Petro-SIM v6.2 进行炼油工艺模拟。

## 核心能力

- **流程建立**: 添加物料流、设置进料、连接单元操作
- **单元操作**: 蒸馏塔、反应器（催化重整、FCC、加氢裂化等）、换热器、分离器
- **物性包**: 设置组分、反应集、流体包
- **油品表征**: 馏程、属性预测、化验数据
- **校准与调优**: 反应器校准、塔板效率、换热器系数
- **结果分析**: 工艺参数、物料平衡、能量平衡

## 快速参考

### 添加单元操作
1. Home tab → Operations → Refining (或按 F4)
2. 选择并拖拽到流程图
3. 双击打开属性视图

### 添加物流
1. Home tab → Streams → Material
2. 定义组成、温度、压力、流量
3. 状态栏颜色: 绿色=完成, 黄色=可选信息缺失, 红色=必需信息缺失

### 常用操作路径

| 功能 | 路径 |
|------|------|
| 新建模拟 | File → New Case |
| 物料流 | Home → Streams → Material |
| 蒸馏塔 | Operations → Refining → Distillation Column |
| 催化重整 | Operations → Refining → Catalytic Reformer |
| 反应集 | Simulation Basis → Reactions |
| 组分 | Simulation Basis → Components |
| 流体包 | Simulation Basis → Fluid Package |
| 油品管理 | Oil Manager |

### 单元操作标签页通用结构

每个单元操作通常包含:
- **Connections**: 输入/输出连接
- **Operating Data**: 操作参数
- **Calibration**: 校准设置
- **Worksheet**: 数据表格
- **Results**: 计算结果

## 单元操作详情

### 蒸馏塔 (Distillation Column)

**添加方法**: Operations → Refining → Distillation Column (或 F4)

**关键参数**:
- 塔板数、进料位置、侧线抽出
- 回流比、再沸比
- 温度/压力分布
- 产品规格 (馏出率、纯度)

**故障排除**:
- 不收敛 → 检查进料状态、规格设定
- 塔顶/塔底产品不合格 → 调整回流量或侧线抽出
- 压降异常 → 检查塔板参数

### 催化重整 (Catalytic Reformer)

**添加方法**: Operations → Refining → Catalytic Reformer

**主要参数**:
- 反应器数量 (1-5个)
- 再生方式: 连续再生、半再生、不可再生
- 温控: 入口温度、催化剂床层温度
- 氢油比

**校准**:
- 使用 REF-SIM 技术手册
- 调整反应动力学参数
- 历史数据拟合

### 加氢裂化 (Hydrocracker)

**添加方法**: Operations → Refining → Hydrocracker

**主要参数**:
- 反应压力、温度
- 催化剂装填量
- 转化率/选择性
- 氢耗

### FCC 反应器

**添加方法**: Operations → Refining → FCCU Reactor

**主要参数**:
- 提升管温度、压力
- 催化剂/油比
- 再生条件
- 产品分布

### 延迟焦化 (Delayed Coker)

**添加方法**: Operations → Refining → Delayed Coker

**主要参数**:
- 焦炭塔数量
- 温度、压力
- 生焦率
- 产品切割方案

## 反应系统

### 添加反应集
1. Simulation Basis → Reactions
2. 选择反应类型:
   - **转化反应** (Conversion): 简单转化
   - **平衡反应** (Equilibrium): 化学平衡
   - **动力学反应** (Kinetic): 反应动力学
   - **异构化催化** (Heterogeneous Catalytic)

### 反应参数
- 动力学参数: 频率因子、活化能
- 平衡常数: Keq 温度相关性
- 转化率/选择性

## 油品表征

### 馏程 (Assay)
- 输入: 实沸点蒸馏数据
- 属性: 密度、硫含量、辛烷值等
- 虚拟组分生成

### 油品管理工具
- Oil Manager: 管理化验数据
- Blend: 混合计算
- Property Table: 属性表格

## 物性包 (Fluid Package)

### Peng-Robinson (PR)
- 通用烃类系统
- 气液平衡计算

### Soave-Redlich-Kwong (SRK)
- 类似 PR，适用于轻烃系统

### 特殊系统
- 电解质: 水/醇胺系统
- 聚合物: 高分子系统

## 求解与诊断

### 求解状态
- 绿色: 收敛
- 黄色: 警告/未收敛
- 红色: 错误

### 常见收敛问题
1. **检查输入**: 温度、压力、流量是否合理
2. **简化模型**: 从稳态开始
3. **调整容差**: Tolerances 页面
4. **初始化**: 良好初始估计
5. **诊断工具**: 查看 Trace 窗口

## 参考资料

详细操作指南见 references 目录:
- `references/reactions.md` - 反应系统详解
- `references/columns.md` - 蒸馏塔操作
- `references/reformers.md` - 催化重整
- `references/oil-management.md` - 油品表征