# AGENTS.md（blo-platform）

角色：BLO 通信框架的父 POM / 版本与依赖管理（Maven reactor）。

## 构建（推荐）
在多 repo workspace 根目录下：

```bash
cd blo-platform
mvn -q -DskipTests install
```

> 说明：`blo-platform/pom.xml` 的 modules 指向 `../blo-comm-*`，因此需要这些目录与本 repo 同级存在。

## 质量门禁（最低要求）
```bash
mvn -q test
```

## Review / 任务实现时必须关注
- dependencyManagement：版本锁定是否会影响 ArcX（Spring Boot / security / jackson 等）
- 任何“版本升级/依赖替换”都属于高风险变更，建议写 ADR，并在 ArcX 侧跑全量编译与关键链路回归。
