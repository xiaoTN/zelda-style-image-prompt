# Codex Skills Collection

这个仓库用于开源和维护一组 Codex Skill。每个 skill 都放在 `skills/<skill-name>/` 下，后续新增 skill 时只需要追加同级目录。

当前包含：

- `zelda-style-image-prompt`：生成「塞尔达传说：旷野之息 / 王国之泪」原版游戏实况截图风格图片提示词

## 目录结构

```text
.
├── skills/
│   └── zelda-style-image-prompt/
│       ├── SKILL.md
│       ├── references/
│       │   └── zelda-visual-style.md
│       ├── agents/
│       │   └── openai.yaml
│       └── evals/
│           └── evals.json
├── LICENSE
├── README.md
└── .gitignore
```

## 安装某个 skill

Codex 识别的是单个 skill 目录，所以不要把整个集合仓库直接克隆到 `~/.codex/skills/` 当作一个 skill。推荐先克隆仓库，再复制需要的子目录。

### 安装到全局 Codex skills

```bash
git clone https://github.com/xiaoTN/zelda-style-image-prompt.git
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R zelda-style-image-prompt/skills/zelda-style-image-prompt \
  "${CODEX_HOME:-$HOME/.codex}/skills/zelda-style-image-prompt"
```

安装后重启 Codex，让新 skill 被重新扫描。

### 安装到某个项目

```bash
git clone https://github.com/xiaoTN/zelda-style-image-prompt.git
mkdir -p .codex/skills
cp -R zelda-style-image-prompt/skills/zelda-style-image-prompt \
  .codex/skills/zelda-style-image-prompt
```

## zelda-style-image-prompt

一个用于生成「塞尔达传说：旷野之息 / 王国之泪」原版游戏实况截图风格图片提示词的 Codex Skill。

它只负责写提示词，不包含任何游戏素材、图片、模型、字体、音频或任天堂资源。

### 适用场景

- 把真实地点转成塞尔达风格游戏截图提示词
- 写林克、塞尔达、海拉鲁探索、神庙、驿站、HUD 等场景提示词
- 把产品、物体或概念包装成 BOTW / TOTK 风格的游戏实况截图提示词
- 统一控制中文 UI、区域发现地名 UI、HUD、耐力轮和原版游戏元素

### 不适用场景

- 直接生成图片或视频
- 提供任天堂官方素材
- 复刻、提取或分发游戏资产
- 规避任何平台、模型或版权方的使用限制

### 使用方式

在 Codex 里直接提出类似需求：

```text
使用 zelda-style-image-prompt，帮我写一个北京故宫的塞尔达风格图片提示词，不用出图。
```

或：

```text
做一张只有塞尔达、没有林克的海边驿站风格图片提示词。
```

skill 会输出可直接交给图片生成模型的最终提示词代码块。

### 设计原则

- 只写稳定、简洁、可执行的提示词
- 默认靠近 BOTW / TOTK 原版游戏实况截图，而不是电影 CG、写实摄影或普通奇幻插画
- 所有可读 UI 默认中文化
- 真实地点的 UI 地名使用真实中文地名，不把游戏内地名硬塞进现实地点
- 尊重用户的角色边界，例如「不要林克」时改为塞尔达单主角

## 免责声明

本项目是非官方提示词写作工具集合，与 Nintendo、The Legend of Zelda、Breath of the Wild、Tears of the Kingdom 或其权利方没有关联、授权、赞助或背书关系。

项目中出现的游戏名称、角色名称和商标仅用于描述提示词风格与兼容场景。使用本仓库中的 skill 生成、发布或商用任何内容时，请自行确认是否符合相关平台规则、模型服务条款和知识产权要求。

## License

MIT
