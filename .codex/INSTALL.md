# Installing On My SDD for Codex

通过 Codex 原生技能发现机制启用 on-my-sdd skills。

## 系统要求

- Git
- Codex CLI 或 Codex App

## 安装

1. **Clone 仓库：**
   ```bash
   git clone https://github.com/9Ashwin/on-my-sdd.git ~/.codex/on-my-sdd
   ```

2. **创建 skills 符号链接：**
   ```bash
   mkdir -p ~/.agents/skills
   ln -s ~/.codex/on-my-sdd/skills ~/.agents/skills/on-my-sdd
   ```

   **Windows (PowerShell)：**
   ```powershell
   New-Item -ItemType Directory -Force -Path "$env:USERPROFILE\.agents\skills"
   cmd /c mklink /J "$env:USERPROFILE\.agents\skills\on-my-sdd" "$env:USERPROFILE\.codex\on-my-sdd\skills"
   ```

3. **重启 Codex**（退出并重新启动 CLI）以发现技能。

## 更新

```bash
cd ~/.codex/on-my-sdd && git pull
```

Skills 通过符号链接即时更新。

## 卸载

```bash
rm ~/.agents/skills/on-my-sdd
```

可选删除 clone：`rm -rf ~/.codex/on-my-sdd`。

## 平台差异说明

On My SDD skills 不依赖 Claude Code 专属工具，可直接在 Codex 中使用。

| 概念 | 说明 |
|------|------|
| Skill 加载 | Codex 原生 skills 发现，直接跟随指令 |
| OpenSpec CLI (`/opsx:*`) | 需在 Codex 环境中安装 OpenSpec (`npm i -g @anthropic/openspec`) |
| Superpowers skills | 需在 Codex 中另行安装 Superpowers |
| `<SUBAGENT-STOP>` 指令 | Codex 子 agent 直接跳过 sdd-workflow，无需特殊处理 |
