# bartender-release

**Bartender for macOS 官方安装包自动镜像（Sparkle appcast → GitHub Releases）**
**Automated mirror of official Bartender macOS installers, tracked from the Sparkle appcast.**

每 6 小时由 GitHub Actions 检查官方 Sparkle appcast，发现新版本即下载官方原版更新包、计算 SHA-256、发布为一个 GitHub Release。**官方原版，未经任何修改，逐字节镜像**，仅作版本归档 / 离线留存。

## 通道 Channels

| 通道 | tag 前缀 | 官方 appcast |
|---|---|---|
| Bartender 7 生产 stable | `b7-<ver>.<build>` | `https://downloads.macbartender.com/Bartender7/updates/AppcastB7.xml` |
| Bartender 7 测试 beta | `b7beta-<ver>.<build>` | `https://downloads.macbartender.com/Bartender7/updates/TestAppcastB7.xml` |

- 生产通道的最新版标记为 GitHub 的 **Latest**；beta 通道不抢 Latest。
- 每个 Release 内含官方 `Bartender-<ver>.<build>.zip`（Sparkle 更新包，universal，macOS 14.0+）+ `SHA256SUMS.txt`。
- 已归档清单见 [`MIRRORED.md`](MIRRORED.md)（workflow 自动刷新）。

## 运行 Run

- **定时**：`cron: 23 */6 * * *`（每 6 小时）。
- **手动**：Actions → `mirror` → *Run workflow*（可设 `max_per_run` 控制单次补齐数量）。
- 权限仅需内置 `GITHUB_TOKEN`（`contents: write`），无任何密钥。

## 说明 Notes

- 版本 = Sparkle `sparkle:shortVersionString`（如 `7.0.1`）；build = `sparkle:version`（如 `700008`）。
- 官方包为 **zip**（Sparkle 增量分发用），非 dmg。
- 分发的是 **官方未修改** 的安装包；不含任何破解 / 改动。
- 官方更新基础设施详见分析文档（另存）。

---

> Mirror is unaffiliated with Surtees Studios. Binaries are the unmodified official builds, redistributed for archival/offline use.
