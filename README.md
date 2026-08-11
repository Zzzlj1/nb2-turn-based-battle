# nb2-turn-based-battle
文字版回合制PVE战斗引擎

基于 NoneBot2 + OneBot V11 的 QQ 群文字 PVE 回合制战斗插件，支持自定义技能 DSL、动态副本与复杂状态机。
核心：
自研技能：支持 18 种效果类型 + 动态公式计算（如 `普攻*140%`）
完整回合状态机：随机行动序 / 冻结跳过 / 被动多时机触发 / 防卡死保护
线程安全存储：SQLite WAL 模式 + RLock 封装，JSON 序列化复杂嵌套结构
异步指令：三级权限模型 / 长文本自动分片 / 配置热加载

结构
`config.py` - 配置管理与热加载
`engine.py` - 战斗核心引擎与状态机
`handlers.py` - 消息路由与指令处理
`skill_parser.py` - 技能 DSL 解析器
`storage.py` - 数据库访问层
