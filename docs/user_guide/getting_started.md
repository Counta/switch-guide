# 开始操作

### 看看序列号

第一件事情就是知道 Switch 能不能用 fusee-gelee，此漏洞用于启动 CFW.

该漏洞是由几个不同的 Switch 黑客团队独立发现的，并且在 90 天的披露期结束后，2018 年 4 月向公众发布了多种变体。 因此，任天堂和英伟达在公众发布之前就意识到了这个问题，2018 年 7 月就有人发现 Switch 不再可以瞎搞。 英伟达也同时在四月 [公开承认缺陷](https://nvidia.custhelp.com/app/answers/detail/a_id/4660/~/security-notice%3A-nvidia-tegra-rcm-vulnerability)  2019 年 7 月 任天堂发布了一个名为 Switch Lite (HDH-001) 的新机，还有续航升级的原版 Switch (HAC-001-01) 。二者都用了新的名为 T210b01 (也叫 T214 和 Mariko) 的新处理器。那些 Switch 当时不能破解。

补丁机和 Mariko 机可以用序列号识别。序列号可以从 Switch 充电口旁边或者设置的 ** 主机 -> 序列号信息 ** 找到。

&nbsp;

!!! tip ""
    ![序列号在设置的位置](../user_guide/img/getting_started_serial_location.jpg)

!!! tip ""
    ![序列号在机身的位置](../user_guide/img/serial_switch.png)

&nbsp;

### 确定到底能不能破解

自制软件社区有一张判断能不能利用 fusee-gelee 漏洞的表。

- 如果下面的表确定了你的 Switch 可破，那你可以继续跟着教程走
- 如果确定你的 Switch 已经打了补丁，那你就去硬破，这里不写硬破教程，破完了可以继续来看看怎么瞎玩。
- 如果系统打了补丁，建议把系统版本能留就留在 7.0.1 。这个版本有很多漏洞 ** 如果想要搞破解就千万不要更新！**，不过谁到现在还没更新呢。

!!! tip "注意"
    如果下面的表也不确定能不能破解，没买 Switch 的也别尝试拼一枪，买了的读一读 [这篇](emummc/sending_payload.md) ，万一能破呢。

-----

&nbsp;

### 列表

该表根据 [这个 GBAtemp 帖子制作](https://gbatemp.net/threads/switch-informations-by-serial-number-read-the-first-post-before-asking-questions.481215/).

|  序列号  | <span style="color:green">未打补丁 </span> | <span style="color:orange"> 可能打补丁 </span> | <span style="color:red"> 已打补丁</span> |
| :----|:---------------------------------|:---------------------------------|:----------------------|
| XAW1 | XAW10000000000 到 XAW10074000000 | XAW10074000000 到 XAW10120000000 | XAW10120000000 以上 |
| XAW4 | XAW40000000000 到 XAW40011000000 | XAW40011000000 到 XAW40012000000 | XAW40012000000 以上 |
| XAW7 | XAW70000000000 到 XAW70017800000 | XAW70017800000 到 XAW70030000000 | XAW70030000000 以上 |
| XAJ1 | XAJ10000000000 到 XAJ10020000000 | XAJ10020000000 到 XAJ10030000000 | XAJ10030000000 以上 |
| XAJ4 | XAJ40000000000 到 XAJ40046000000 | XAJ40046000000 到 XAJ40060000000 | XAJ40060000000 以上 |
| XAJ7 | XAJ70000000000 到 XAJ70040000000 | XAJ70040000000 到 XAJ70050000000 | XAJ70050000000 以上 |
| XAK1 | **N/A** | XAK10000000000 以上 | **N/A** |

如果上表没有列出，那也是不可软破的。


&nbsp;


### 主机准备

!!! danger "重要（译者：其实很没用）"
    一切开始之前最好有任意游戏 (比如 [辐射: 避难所](https://www.nintendo.com/games/detail/fallout-shelter-switch/)), 软件 (比如 [YouTube](https://www.nintendo.com/games/detail/youtube-switch/) 或者 [Hulu](https://www.nintendo.com/games/detail/hulu-switch/)), 再或者试玩版游戏 [10 Second Run RETURNS](https://www.nintendo.com/games/detail/10-second-run-returns-switch). 卡带版游戏也行，但是要插着。破解不会删掉这些东西也不会覆盖这些东西 (安装的软件和插入的游戏卡也能正常使用). 你有游戏 / 软件的话就继续吧。
    ** 译者注：这一步根本可以不做。**

&nbsp;

-----



&nbsp;

| 系统版本 | 未打补丁的机子 (HAC-001) | 打了补丁的机子 (HAC-001) | "续航版" Switch (HAC-001-01)   | Switch Lite (HDH-001)  |
|:---------------|:--------------------------------|:---------------------------|:----------------------------|:-----------------------|
| 1.0.0          | Nereba 或者 [**RCM**](rcm.md)     | **N/A**                    | **N/A**                     | **N/A**                |
| 2.0.0 - 3.0.2  | Caffeine 或者 [**RCM**](rcm.md)   | **N/A**                    | **N/A**                     | **N/A**                |
| 4.0.0 - 4.1.0  | Caffeine 或者 [**RCM**](rcm.md)   | Caffeine                   | **N/A**                     | **N/A**                |
| 5.0.0 - 7.0.0  | [**RCM**](rcm.md)               | 去硬破               | **N/A**                     | **N/A**                |
| 7.0.1          | [**RCM**](rcm.md)               | 去硬破               | 插张能更新系统到 8.1.0 的卡        | **N/A**                |
| 8.0.1          | [**RCM**](rcm.md)               | 去硬破          | 去硬破           | 去硬破      |
| 8.1.0 - 14.1.2 | [**RCM**](rcm.md)               | 去硬破     | 去硬破      | 去硬破 |

&nbsp;

!!! note "OLED 机"
    OLED 机 (HEG-001) 目前无法软破。

&nbsp;

#### [如果 Switch 没打补丁，继续到 RCM <i class="fa fa-arrow-circle-right fa-lg"></i>](rcm.md)
