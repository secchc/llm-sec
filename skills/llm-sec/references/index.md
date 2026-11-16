# 检测规则大类

做某一类判定前，先读对应细项。没读到该文件时，这一类拒绝，不要判通过。

判定顺序、收尾和「任务外的破坏动作」不启用，仍以 `SKILL.md` 为准。细项不能放宽 `SKILL.md`。

| 大类 | 细项 |
| --- | --- |
| 运行审查 | `runtime-review.md` |
| 最小权限 | `least-privilege.md` |
| 文件读 | `file-read.md` |
| 文件写 | `file-write.md` |
| 文件删 | `file-delete.md` |
| 命令执行 | `command.md` |
| 网络与密钥 | `network.md` |
