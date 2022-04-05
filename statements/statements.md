# 冰雪杯

## 游戏介绍

“冰雪杯”组由软件学院主导开发的即时对抗游戏。

3名选手各控制一支至多四个队员的队伍在圆形滑冰场上进行即 时对抗，队员需要推冰橇来收集场地上刷新的“冰墩墩”和“雪容融”(下简称“冰墩墩”)，并送回自己的球门 内;同时，还要防止其他队伍偷窃自己的“冰墩墩”。在规定时间内收集到最多数量的队伍将胜出。

[题面下载](https://cdn.jsdelivr.net/gh/ssast-tech/thuai-egg-releases@2e3134fe/statements.pdf) // 这里的链接要改

本次比赛支持平台：win32(x64), Linux(x64), macOS(x64)

支持语言：C/C++、Python


## 参赛流程

### 初赛截止时间

2022年4月24日

### 加入小组

请在小组页面加入本次比赛的小组。

### 下载游戏包

在右上角的「下载游戏包」按钮下载游戏包。游戏包内含：

- 开发`SDK`与简单的样例AI；
- 本地评测程序；
- 开发说明和游戏详细规则。

同时，您也可以在 https://gitee.com/panda2134/thuai2021-egg-aisdk/releases 下载最新构建的上述内容。

### 编写 AI

请参考游戏包中的开发说明与样例，选择你喜欢的语言编写 AI。详细的配置说明在开发说明中都有提及。

### 提交代码

在「我的AI」处提交自己的 AI，可根据实际情况选择对应编译语言，编译成功后便可将 AI 派遣到对应比赛。

### 派遣 AI

您可以在天梯上派遣AI，并发起对战，以观测己方与其他选手的策略博弈。天梯成绩仅供参考，不计入最终比赛名次成绩。

### 观看回放

您也可以使用 Saiblo 在对局结束后打开的窗口中的播放器，或者点击右上角的「下载回放」按钮将回放文件下载后，在Saiblo的「网页播放器」中家在回放文件。

### 决出名次

初赛时间截止后，我们会在选手间发起大量对局并统计积分，直至排名收敛为止。

## 测试方法

### 本地测试

我们提供了一个本地裁判程序 `./game/Judger/judger.py` 用于评测两个本地 AI，具体使用方法为：在 `codes` 文件夹下输入指令

```bash
python <judger.py位置> <启动游戏逻辑指令> <启动AI0指令> <启动AI1指令> <启动AI2指令> <配置信息> <生成录像文件路径>
```

例如，游戏评测逻辑文件为 `./game/logic/main`，两个 AI 分别为 `./example` 和 `./game/smartAI`。可在 Linux下使用以下命令：

```bash
python ./game/Judger/judger.py ./game/logic/main ./example ./game/smartAI ./game/smartAI snow replay.bin
```

AI将使用C++编写。对局完成后，会将对局文件存入 `replay.bin` 。

### 评测逻辑文件下载

出于安全考虑，评测逻辑只提供构建好的Linux版本，可在 https://github.com/ssast-tech/thuai-egg-releases 进行下载，也可以直接采用下列链接。下载后即可采用 judger.py 和评测逻辑文件配合，进行测试。Windows可以使用WSL，Mac用户可以使用直接使用网页测评器。（如果后续需求较大，我们会额外提供Windows和Mac的版本）

- [Ubuntu 16.04 x86_64](https://cdn.jsdelivr.net/gh/ssast-tech/thuai-egg-releases@2e3134fe/eggs-ubuntu-16.04-x86_64) // 需要改链接
  - 注：Linux版本下载后需要手动授予可执行权限
