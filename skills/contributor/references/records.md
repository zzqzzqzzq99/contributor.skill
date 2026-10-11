# 私有任务记录与公开输出

仅在需要跨会话继续或保存候选时使用。记录放在用户的私有工作目录，不放入准备贡献的上游仓库或待发布 skill 目录；不要默认写入宿主长期记忆。已有项目记录可承载这些信息时不另建文件。

完整记录用下面的 YAML 语义；字段按需要填写，`null` 表示未知。事实有变化时更新 current status，保留必要的历史依据。输出给用户时用自然语言，不强制展示 YAML。

```yaml
schema_version: 1
updated_at: null
request:
  objective: null
  stage: discover # discover | prepare | submit | follow-up
  allowed_sources: [] # 本地引用，不复制敏感原文
  constraints: []
  authorization: null # 用户实际授权的目标/动作；不能由模板产生授权
profile:
  - domain: null
    recurring_task: null
    insight_or_sop: null # 可公开的抽象方法
    evidence:
      - source: null
        status: null # artifact-tested | user-reported | discussed
    public_query: null # 仅通用关键词
candidates:
  - repository: null
    checked_at: null
    base_commit: null
    origin: null # technology | personal-practice | ai-analysis，可多项
    user_fit: null
    affected_user_and_trigger: null
    evidence_links: []
    license_and_contribution_rules: null
    existing_fix_or_pr: null
    smallest_useful_change: null
    verification_plan: null
    maintenance_cost_and_unknowns: null
    decision: null # pursue | investigate | skip
contribution:
  repository: null
  branch: null
  head_commit: null
  private_evidence_location: null
  validation:
    passed: []
    failed: []
    not_run: []
  pr_url: null
  status: null
  checked_at: null
  maintainer_feedback: []
  learned: []
  next_action: null
```

## 候选卡

默认一张推荐卡，必要时增加最多两张备选。给出仓库链接、与个人积累的关系、当前问题证据、具体改动、验证办法、成本/限制。不要把用户行业概括当作问题证据，也不要仅凭旧 Issue 宣称问题仍存在。

## PR 正文

遵循目标仓库模板。无模板时，只需要：

1. 触发条件、原行为与影响。
2. 修改后的行为和必要的取舍。
3. 实际完成的验证及未验证部分。

引述公共 Issue/日志用链接，测试材料说明为合成或获授权。避免公开个人画像、私有证据路径、对话内容或未经证实的效率数字。不在正文默认承诺维护周期。

## 贡献经历

合成写法示例：

> 为文书处理项目补充跨平台输出修复及回归测试，解决重定向输出时的编码错误；本地测试通过，PR 已提交，尚未合并。

仅在远端证据更新后改为“已合并”。经验可用于简历或作品集，但生成文本不等于授权自动发到社交媒体、招聘平台或个人网站。
