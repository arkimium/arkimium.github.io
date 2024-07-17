---
layout: post
title:  Weekly Linux News Translation Blog No.1
date:   2024-07-17 14:00:00 +0800
categories: linux-news update
usemathjax: false
---

# Linux新闻每周翻译·第一期
### 牧安 译

## 来自：9to5linux

### Linux内核6.10版本正式发布，有哪些新功能？
#### 正式引入mseal()系统，进行内存密封，以保护映射本身免遭修改并缓解内存损坏问题。
### 作者：Marius Nestor
#### Linus Torvalds今天宣布发布 Linux 6.10，作为最新的稳定内核分支，它引入了几个新功能和改进的硬件支持

Linux 内核 6.10 的亮点包括用于内存密封的新 mseal() 系统调用、对RISC-V架构的 Rust 语言支持、对 EROFS 文件系统的 Zstandard 压缩支持、对 x32 子架构的影子堆栈支持、TPM 总线加密和完整性保护，以及对设置 PFCP（数据包转发控制协议）过滤器的初始支持。

Linux 6.10 还为 PowerPC BPF JIT 编译器添加了 kfuncs 支持、ring_buffer 内存映射（用于将跟踪环形缓冲区直接映射到用户空间）、一种用于控制内核中的 NFS 服务器的基于 netlink 的新协议、用于将策略应用于 ioctl() 调用的 Landlock 支持，以及对 FUSE 文件系统的完整性保护支持。

Linux 内核 6.10 中也引入了基本的 bpf_wq 支持，使 BPF 程序能够使用内核中的等待队列，还添加了 Rust 抽象以处理内核中的时间，并且现在支持 AArch64（ARM64）系统的 userfaultfd() 写保护功能。

同样新的是 ntsync 子系统，用于为 Linux/Wine 游戏提供 Windows NT 同步原语，以及用于 32 位 ARCv2 处理器的 BPF 即时编译器和用于 dm-crypt 设备映射器的新 high_priority 选项，用于在处理期间设置高优先级工作队列，这可能会提高大型系统的性能。

除此之外，Rust 支持已更新至 Rust 1.78.0，ARM 架构获得了对 Clang CFI（控制流完整性）和 LPAE 特权访问永不支持的支持，OverlayFS 文件系统获得了使用 O_TMPFILE 选项创建临时文件的能力，还有一个名为“init_mlocked_on_free”的新启动选项，它会在释放时将任何锁定到 RAM 中的页面清零。

正如预期的那样，Linux 内核 6.10 通过添加新驱动程序或更新现有驱动程序来改进硬件支持。值得注意的亮点包括对 Radxa ROCK 3C 开发板、英特尔 Arrow Lake-H 处理器、联想 Thinkbook 13x Gen 4、联想 Thinkbook 16P Gen 5 和联想 Thinkbook 13X 笔记本电脑、华硕 ROG 2024 笔记本电脑和 Machenike (机械师) G5 Pro 游戏控制器的支持。

Linux 6.10 还应通过在现代 x86_64 CPU 上更快的 AES-XTS、区域写入插入来大大提高区域设备的性能，大大提高使用 io_uring 的发送零拷贝性能，并提高 OCFS2（Oracle Cluster File-System v2，甲骨文云Oracle推出的第二代集群文件系统）文件系统的写入性能，在各种平台上提供一些不错的性能改进。

Linux 内核 6.10 可从 Linus Torvalds 的git 树或kernel.org网站下载，它将是一个仅支持几个月的短暂分支。它将被 Linux 内核 6.11 取代，Linus Torvalds 现已正式打开其合并窗口。Linux 内核 6.11 预计将于 2024 年 9 月中下旬发布。

<figure>
  <img src="{{ ![kernel](https://github.com/user-attachments/assets/c7987d2a-8016-4b79-8524-d809abfc0fa9)  }}" alt="Linux内核发行官网kernel.org截图，版本6.10已经发行">
  <figcaption>kernel.org - Linux内核发行官网截图</figcaption>
</figure>

##### 原网站：https://9to5linux.com/linux-kernel-6-10-officially-released-this-is-whats-new




### 跨平台开源音频编辑软件 Audacity 3.6 版本正式发布，将支持 Master Effects 和 FFmpeg 7
### 作者: Marius Nestor
#### Audacity 3.6 开源、免费、跨平台音频编辑器今天作为重要更新发布，引入了多项新功能、全新外观和各种改进。

在Audacity 3.5发布近三个月后，Audacity 3.6 版本引入了主效果（可同时应用于整个项目的效果）、新的压缩器和限制器效果（当用作实时效果时具有增益减少历史记录），以及新的和改进的深色和浅色主题。

> “您可以通过“首选项”->“界面”在主题之间切换。以前使用的主题仍是经典主题，甚至更旧的主题也可以选择安装为自定义主题，”开发人员解释道。

此版本还增加了对最新、最好的FFmpeg 7开源多媒体框架的支持、使用 Ctrl+V 将音频文件粘贴到 Audacity 的支持、Extras > Export 选项中的新“导出选定的音频”、对大于 2 GB 的偏移量的支持，以及在 View 菜单中显示/隐藏波形中 RMS 的选项。

此外，Audacity 3.6 带来了重新设计的“新功能”对话框、支持从 [Audacity OpenVINO官网](audacityteam.org/download/openvino/) 下载 OpenVINO AI 效果、支持通过自定义主题支持可主题化的替代波形颜色，以及脚本中的新“GetInfo：Type=Selection”选项。还解决了各种错误，包括一个可能以错误的采样率打开项目的错误、一个导致使用高对比度主题时出现杂散橙色线条的错误、一个影响 Linux 系统上 Ogg 导出质量滑块的错误、一个宏管理器中的错误导致它无法将无参数操作显示为可编辑，以及一个在录制到新轨道时导致它无法再次滚动回视图的错误。

您现在可以从官方网站下载 Audacity 3.6作为 AppImage 二进制文件，您可以在几乎任何 GNU/Linux 发行版上运行它，而无需在个人计算机上安装任何东西。查看发行说明以获取有关此版本中包含的更改的更多详细信息。

##### 原网站：https://9to5linux.com/audacity-3-6-open-source-audio-editor-released-with-master-effects-ffmpeg-7-support



## 来自： It's Foss

### FOSS周报 #2024年第28期：掌握 Nano、Xfce 发行版、Proton 的 Google Docs 竞争对手等
#### 这对我来说很少见。但如果你喜欢某个主题的较长视频，也许我可以制作有关 Linux 命令和 Bash 脚本的视频。请告诉我你的反馈 😄


#### 让我们看看你在这个版本中还能获取到什么消息
- Google Docs的新竞争对手
- Linux Mint 22发布日期被推迟
- Fedora将推出仅限Wayland的ISO安装镜像
- GNOME正在转向不同的默认字体。
- 还有其他Linux新闻、视频，当然还有表情包！


#### 本周Linux新闻简讯
- 谷歌已经扩展了对Android的Linux内核支持。
- Proton已为Drive推出了一个安全文档编辑器。
- Linux Mint 22发布由于棘手的错误而被推迟。
- Peppermint OS现在为新用户提供了一个新的“已加载”版本。
- GNOME的目标是将默认字体更改为更易于维护的字体。
- 即将推出的Fedora 41 Workstation GNOME镜像将仅限于使用Wayland桌面服务器

### 谷歌已经扩展了对Android操作系统的Linux内核支持。
### 作者：SOURAV RUDRA

Linux 内核是一个奇妙的东西，它为这个技术驱动的世界里许多被很多人忽视的事物提供动力。

您现在手中很可能正拿着一块平板电脑，它很可能运行的是Android系统。它使用Google的Linux LTS（长期支持）版本作为坚实的基础，为您提供出色的智能手机体验。

早在2023年，Linux内核的维护者就决定缩短其LTS内核版本的支持期。他们将支持期从之前的六年缩短为更短的两年，此后他们将停止为其推送错误修复，并额外增加一年提供安全补丁。

此举背后的两个主要原因一是**解决维护人员倦怠的关键问题**，二是**没有多少人使用旧版本的Linux内核**。

当时，我们预计依赖旧版Linux内核的系统*会因这一举措而受到不利影响*。现在看来,Google并没有坐等内核支持周期缩短而陷入困境，而是加大了支持力度。

- 谷歌加强对 Android 的支持：有何期待？
该表的屏幕截图显示了各种ack分支的支持寿命
![ACK分支支持周期表](https://news.itsfoss.com/content/images/2024/07/ACK_Support_Period.png)
谷歌以非常**秘密**的方式将其稳定内核的支持期延长至四年，从Linux内核6.6开始。

他们在ACK文档中分享的上表反映了他们目前支持的许多内核的各种EOL（生命周期终止）日期，一直可以追溯到2018年发布的Linux 4.19。

他们还提到：

> ACK的支持时间可能比[Linux内核发行网](kernel.org)上对应的上游稳定内核更长。在这种情况下，Google会提供延长支持，直至本部分所示的停更(EOL)日期。内核停更后，Google将不再支持这些内核，运行这些内核的设备将被视为易受攻击。

ACK是什么？它们代表“Android通用内核”，它位于Linux内核的下游，并且包含Linus Torvalds（Linux创始人兼主要开发人员）维护的主线Linux上没有的Android专用补丁。

更长的支持时间应该有助于Google解决错误，更重要的是，***安全漏洞***，这些漏洞如今比比皆是，而且每隔一天就会出现新的漏洞。

- 想知道作为用户你应该做什么吗？ 🤔

其实很简单。如果你的设备仍在接收重要的安全更新和主要操作系统更新，那么我强烈建议你保持设备更新。

除此之外，了解您或使用您设备的其他任何人安装的应用程序也有帮助。对于这样的事情，您再怎么小心也不为过。

建议您阅读FOSS官方去年9月20日发布的[Linux 内核支持即将发生重大变化……](https://news.itsfoss.com/linux-kernel-support/)新闻来了解更多。

##### 原网站：https://news.itsfoss.com/google-linux-kernel-support





### 著名云网盘产品Proton Drive中的文档编辑器Proton Docs首次亮相，将与Google Docs一较高下
### 作者：SOURAV RUDRA

Proton最近发展势头强劲，收购了Standard Notes，让Android用户更方便使用VPN 。他们计划在2024年继续改进现有服务，同时推出新服务。

他们延续了这一传统，现在推出了一个人们长期要求的功能，即在Proton Drive上拥有一个安全文档编辑器，使其成为Google Drive或微软OneDrive等产品的可行替代品。

他们只是称之为“Proton Drive中的文档”，但我发现随着它越来越受欢迎，许多人都称它为“Proton Docs”，也许这可能会促使Proton以“*Proton Create*”这样的新名字提供功能齐全的办公套件？🤔

不管怎样，我有一点 *痴心妄想* (delulu) 😆。跟我一起了解Proton Docs提供的内容。

- Proton Drive 中的文档：值得等待吗？
Docs被誉为“在大多数流行产品忽略（neglect）隐私的市场中的独特解决方案”，它是Proton Drive的端到端（end-to-end, backend to front end的意思）加密文档编辑器，旨在兼具安全性和用户友好性。

通过此功能，用户可以**创建新文档**、**编辑现有文档**，甚至可以利用以下协作功能与他人协作：
- **添加评论**
- **回复评论**
- **查看还有谁在实时查看文档（使用协作光标）**
- **邀请新的合作者**。

![Proton Docs Introduction](https://news.itsfoss.com/content/images/2024/07/Docs_In_Proton_Drive_b.jpg)

至于编辑体验如何，支持**富文本编辑**，使用户能够以他们熟悉的方式创建/编辑文档。

他们拥有多种先进的格式化工具，并具有广泛的文件兼容性，支持Microsoft的`.DOCX`文件格式，使互操作性变得轻而易举。

在发布会上，Proton Drive 产品负责人Anant Vijay Singh补充道：

> Proton Drive 中的文档可让您轻松保持安全和私密。用户无需费心或担心复杂的安全措施 — Proton 已为您做好一切准备。

Proton 还指出，所有用户数据都存储在*他们拥有和管理的服务器*上，*并由他们负责维护*，避免将这些责任外包给第三方提供商。

我是否曾提到过，每个拥有 Proton 账户的人都可以使用它？

*是的*，*无需注册付费账户即可访问Proton Drive上的文档*，这是一个伟大的举措，为云存储服务开放了如此重要的功能。

当然，对于寻求注重隐私的在线文档编辑器的用户来说，Docs by Proton将是与Cryptpad一起的另一个不错的补充。

- 在 Proton Drive 中获取文档
尽管有些显而易见，但您可以通过注册或登录Proton Drive并打开现有文档或创建新文档来开始使用新的文档编辑器。
当然，如果您想使用与之结合的其他服务，请使用[Proton Mail](http://proton.go2cloud.org/aff_c?offer_id=15&aff_id=1173&ref=news.itsfoss.com)（合作伙伴链接）来替代Gmail和Google Docs。

##### 原网站：https://news.itsfoss.com/docs-in-proton-drive




### Linux Mint 22 发布因严重错误而延迟！
### 作者：SOURAV RUDRA

#### 自从Cinnamon 6.2发布以来，人们就开始竞相关注即将发布的Linux Mint 22“Wilma”版本，并在开发阶段尽可能地实现最高水平的改进。

#### 它是一个基于 Ubuntu 24.04 的长期支持版本（直到 2029 年），*对于开发人员按计划启动和运行来说是一个重要版本*。

#### 遗憾的是，他们遇到了一系列错误，导致发布日期被进一步推迟。

- Linux Mint 22：讨厌的bug消失
![Tux表示很生草 - Linux Mint 22的GUI界面](https://news.itsfoss.com/content/images/2024/07/LM_22_Beta.png)
Clement Lefebvre(CLEM)在博客中宣布，他们已经收到了超过100份报告，其中包含Linux Mint 22测试版的各种错误和怪癖。但有些比其他的更为严重。

例如
- Flatpak/Mint安装问题
- AppArmor 安全更改期间的崩溃以及硬件加速播放库导致Xorg桌面服务器崩溃。

不用说，开发人员很高兴在稳定版本发布之前收到了这种反馈，他们正在努力逐一解决问题，并在进展过程中推送更新。

如果所有这些都让你感到好奇，那么你可以自己看看并判断发生了什么。 GitHub上的mint22-beta仓库包含了各种用户发布的所有未解决和已解决的问题。

如果您想测试 Linux Mint 22 的测试版，那么您可以参考之前的博客进行测试。[Linux Mint 22 "Wilma" Beta](https://blog.linuxmint.com/?p=4725&ref=news.itsfoss.com)
不过，不用担心，Clem还提到Linux Mint 22仍将于2024年7月推出，只是推迟了几周，比通常的2周测试阶段要长。

##### 原网站：https://news.itsfoss.com/linux-mint-22-release-delayed/?ref=itsfoss.com

