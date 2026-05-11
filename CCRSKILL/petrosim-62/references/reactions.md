# 反应系统参考

## 反应类型

### 1. 转化反应 (Conversion Reaction)
简单的一次反应，指定转化率。

**参数**:
- 转化率 (Conversion)
- 反应组分
- 反应温度/压力

### 2. 平衡反应 (Equilibrium Reaction)
基于化学平衡常数的反应。

**方程**:
```
Keq = Π [activity_i]^νi
```

**参数**:
- 化学计量系数
- 平衡常数 Keq 或温度关联
- 反应方向

### 3. 动力学反应 (Kinetic Reaction)
基于反应动力学的反应，需要阿伦尼乌斯参数。

**方程**:
```
r_A = k_f * Π [C_i]^ni - k_r * Π [C_i]^nj
k = A * exp(-E/RT)
```

**参数**:
- 正向/反向频率因子 (A)
- 活化能 (E)
- 反应级数
- 化学计量系数

### 4. 异构化催化反应 (Heterogeneous Catalytic)
多相催化反应模型。

## 添加反应集步骤

1. **Simulation Basis → Reactions**
2. **Add Reaction Set**
3. 选择反应类型
4. 定义组分和化学计量
5. 设置动力学参数

## 参数标签页

| 标签 | 内容 |
|------|------|
| Stoichiometry | 化学计量系数 |
| Basis | 反应基准 (浓度/分压) |
| Parameters | 动力学参数 (A, E) |
| Keq | 平衡常数温度关联 |

## 常见问题

**不收敛**: 检查初始估计值，尝试调整动力学参数

**结果偏差**: 校准频率因子和活化能