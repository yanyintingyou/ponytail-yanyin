# ponytail-yanyin

Prompt-only fork of [DietrichGebert/ponytail](https://github.com/DietrichGebert/ponytail) (MIT), adapted for my own agent setup.

Ponytail makes an agent write the smallest change that fully solves the task instead of the most impressive one.

## What is here

```
SKILL.md          the prompt, with local overrides
commands/*.toml   review, audit, debt, gain, help, level switching
LICENSE           MIT, original copyright
```

Nothing in this repo executes. No hooks, no statusline, no plugin manifests, no install script, no benchmarks. Everything else from upstream was removed on purpose.

## Differences from upstream

- No persistent test files by default; verify by running the code once.
- Slash commands are read from `commands/*.toml` on request, since the host does not register slash commands.
- Hook and activation machinery removed; the skill is active by being loaded, not by intercepting events.

## Install

Copy or clone this directory into your agent's skills folder, keeping `SKILL.md` and `commands/` side by side. The skill name is `ponytail-yanyin`.

## Upstream

```sh
git remote add upstream https://github.com/DietrichGebert/ponytail.git
git fetch upstream
git diff upstream/main -- skills/ponytail/SKILL.md commands/
```

Read the diff before merging. Upstream releases rewrite the prompt regularly and reference hooks this fork does not have.

---

## 中文说明

[上游 ponytail](https://github.com/DietrichGebert/ponytail) 的纯提示词分支，MIT 许可，保留原版权声明。

只保留 `SKILL.md` 与 `commands/`，去掉全部 hook、状态栏、插件清单、素材、基准测试和安装脚本。相对上游的个人改动：默认不写常驻测试文件（跑一次验证即可）；命令改为按需读取 `commands/*.toml`；不再依赖事件拦截来激活。

上游更新时先看 diff 再合，不要整包覆盖，否则会把 hook 引用带回来并冲掉本地改动。
