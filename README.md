# L4D2-8-Player-Local-Coop
Left 4 Dead 2 - 8 Player Local Co-op Mod Pack &amp; Chinese Installation Guide

（有图版本见word 和 pdf 版）


求生之路2   8人本地联机补丁包 
By bilibili_蒜头头头

版本说明：根据 2026-10-21 实机成功进行 6 人战役的配置整理（本地）。本包设置最多 8 名幸存者，但 6~8 名玩家的实际稳定性仍需安装后逐一验证。
仅房主需要安装，安装后无法加入官方服务器以及其余需要vac的服务器
 


安装步骤（认真看完还不会，砍死你）
一，	从steam安装L4D2并确认可以正常打开游戏，然后退出
（仅实验过steam正版，盗版局域网未实验）
 
二，	右键l4d2，打开游戏的安装根目录
 
在根目录里打开left4dead2文件夹 
如果愿意，可以备份addons和cfg文件夹（并非必要，因为未来想要卸载这个模组可以直接重装l4d2）
 
三，	打开本压缩包，将本压缩包内的addons，cfg两个文件夹，拖入到上一步打开的文件夹内，
 
如果有替换窗口，那就点击替换目标中的文件（没有是正常的）
 
之后检查游戏目录中的addons文件夹里，需要存在红框的6个文件
 
再检查cfg文件夹中需要有红圈中的两个文件
 
 
四，	进入steam创意工坊，搜索订阅“8 slots lobby fixed”模组
 
 
 
订阅时提示额外必须物品，点击全部订阅
 
五，	回到steam库，右键l4d2，选择属性
 
在下方启动选项中输入“-insecure”，然后点击右上角叉叉关闭
 
届时安装步骤已经完成，推荐继续进行验证。
不想验证的跳步骤7。
六，	验证安装是否成功
点击开始游戏
 
游戏启动之后会显示这个页面，点击确定就行（如果这个警告没有出现，先继续执行控制台验证）
 
如果附加内容左边在转圈，那就等他转完，否则创意工坊内容无法完全安装
 
如果没有打开控制台，就进入选项→键盘/鼠标→允许使用开发者控制台→启用
 
 
回到游戏主菜单，按键盘左上角的“~”打开控制台， 
在控制台下方输入map c1m1_hotel 回车， 游戏会打开死亡中心的地图
 
等载入完成，再按“~“打开控制台，
 
依次输入下列命令（每一行之后按回车输入）
meta version
meta list
plugin_print
sm plugins list
sv_maxplayers
sv_visiblemaxplayers
l4d_multislots_max_survivors
最后的输出应该会长这样
 
如果一模一样，那就已经成功了，跳到下一步就行。
如果不一样，特别是其中有Error，或者Unknow command，则代表上述步骤有出入，检查对应插件与日志，优先排查启动参数、文件位置、依赖和缺失配置。懒人方式是再次安装。（如下两张图所示）
 
 
七，	开房方式，回到游戏菜单，点击完成战役→与好友一起玩游戏
 
创建新战役大厅
 
确保服务器类型为本地服务器，然后创建大厅
 
届时房间内会有8个空位，测试第五个玩家能否进入游戏。
 
安装步骤结束

可能故障
- `Unknown command: sv_maxplayers`：优先检查 `-insecure`、游戏启动后是否已进入地图，以及 `addons/l4dtoolz.dll`、`addons/l4dtoolz.vdf` 是否放对目录；用 `plugin_print` 验证加载。

- `Unknown command: l4d_multislots_max_survivors`：检查 `meta list` 和 `sm plugins list`；确认 `addons/sourcemod/plugins/l4dmultislots.smx` 存在。

- CreateSurvivorBot 显示 `<Error>`：确认 `addons/sourcemod/gamedata/l4d_CreateSurvivorBot.txt` 存在，再检查 `addons/sourcemod/logs/errors_*.log`。

- 大厅已有 8 个位置但进图失败：优先检查房主是否真的选择“本地服务器”、服务器插件是否全部加载，以及 `-insecure`；大厅 8 槽位不等于服务端 8 人功能已经生效。

- 第 5 人只能观战：检查 MultiSlots、CreateSurvivorBot、Left4DHooks 加载及游戏内 `sm_join` / `sm_js` 的插件使用说明。

- 安装后影响官方服务器：关闭游戏、移除 `-insecure` 并暂时移走第三方服务端插件（之前做好备份，或者重装游戏），恢复正常联机环境。

版本以及来源
包内包含 MetaMod:Source 1.12.0-dev+1227、SourceMod 1.12.0.7255、L4DToolZ 2.5.1、Left4DHooks 1.174、CreateSurvivorBot 和 MultiSlots Improved 7.4。组件属于各自作者，详见随包保留的许可证及原项目：
- MetaMod:Source https://github.com/alliedmodders/metamod-source
- SourceMod https://github.com/alliedmodders/sourcemod
- L4DToolZ https://github.com/lakwsh/l4dtoolz
- Left4DHooks https://github.com/SilvDev/Left4DHooks
- MultiSlots / CreateSurvivorBot https://github.com/fbef0102/L4D1_2-Plugins

本补丁只是社区插件的整理，不包含游戏本体。转发时请保留上游版权、许可说明，并遵守各组件的源代码提供条款。这里只做文件结构及配置核验，2026/10/22 在另外两台电脑上安装实测有效。
测试游戏版本
 
