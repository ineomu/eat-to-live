# Tests · 测试用例

> 6 个真实场景测试，覆盖所有 4 个入口。
>
> **隐私声明**：所有测试案例均基于真实咨询场景改写，已做匿名化处理（隐去城市、职业等身份信息），不指向任何真实个人。

## 测试清单

| # | 文件 | 入口 | 难度 | 关键验证点 |
|---|---|---|---|---|
| 1 | [test-30yo-female.md](test-30yo-female.md) | 🚪 体检 | 中 | BMI 关键诊断 + 重新定义"减肥"目标 + 一周食谱 |
| 2 | [test-male-runner.md](test-male-runner.md) | 🚪 体检 | 高 | 运动量计算 + 训练日/休息日分别 + 训练后窗口 |
| 3 | [test-bone-soup-myth.md](test-bone-soup-myth.md) | 🚪 拍砖 | 低 | 数字反驳 + 沟通技巧 |
| 4 | [test-oral-ulcer.md](test-oral-ulcer.md) | 🚪 反查 | 中 | 4 大组织 + 多种营养素 + 反模式自查 |
| 5 | [test-grandpa-diabetes.md](test-grandpa-diabetes.md) | 🚪 综合 | 高 | 多病叠加 + 老年 + 4 大反模式 |
| 6 | [test-insulin-resistance-metaphor.md](test-insulin-resistance-metaphor.md) | 🚪 反查 | 中 | 比喻化解复杂机制 |

## 跑测试的方法

### 手动跑

1. 把 `SKILL.md` 加载到你的 AI 助手里
2. 复制 `test-xxx.md` 里的"输入"段落给 AI
3. 对照"期望输出"段落
4. 检查"验证清单"是否全部通过

### 自动跑（规划中）

```bash
# TODO: 接入 LLM 测试框架
pytest tests/
```

## 测试设计原则

每个测试都覆盖：
- ✅ **必问 8 个信息**（用户应主动反问）
- ✅ **必查 3 个雷区**（食物种类≠营养丰富 等）
- ✅ **必扫 26 条反模式**
- ✅ **必给数字口诀**（100 分 / 三足鼎立 / 35:65 / 减负三法则 等）
- ✅ **必给权威依据**（引用 references.md 的源）
- ✅ **必给可执行**（每天几次 / 一次多少 / 多久复查）
- ✅ **人称语气**（临床腔 + 比喻 + 故事开场）

## 添加新测试

提交 PR 时，请：
1. 在 `tests/` 下加 `test-新场景名.md`
2. 文件结构跟现有测试一致：输入 / 期望输出 / 验证清单
3. 至少覆盖 1 个反模式或 1 个慢病专项
4. 更新本 README.md 的"测试清单"
