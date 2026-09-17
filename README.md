# bartender-release

**Bartender for macOS 官方安装包自动镜像 | Automated mirror of official Bartender macOS installers.**

每 6 小时由 GitHub Actions 检查官方 Sparkle 更新源，发现新版本即下载官方原版更新包、计算 SHA-256、发布为一个 GitHub Release。**官方原版，未经任何修改，逐字节镜像**，仅作版本归档 / 离线留存。

- 覆盖 Bartender 7（生产 + 测试）与 Bartender 6。
- 每个 Release 内含官方 `Bartender-<ver>.<build>.zip` + `SHA256SUMS.txt`。
- 已归档清单见 [`MIRRORED.md`](MIRRORED.md)。

---

> Unaffiliated with Surtees Studios. Binaries are the unmodified official builds, redistributed for archival / offline use.
