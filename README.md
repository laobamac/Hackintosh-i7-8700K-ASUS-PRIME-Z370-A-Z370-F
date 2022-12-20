# i7-8700K-ASUS-PRIME-Z370-A


|   规格   | 状态  |                   详细信息                 |
| :-----: | ---- | :---------------------------------------: |
|  型号  | ✅    |     i7-8700K-ASUS-PRIME-Z370-A      |
|  系统  | ✅    |   10.15-13.2     |
|  CPU   | ✅    |    Intel Core i7-8700K 6C12T Processor    |
|  主板  | ✅    |     华硕PRIME-Z370-A(可刷Z370-F）（BIOS更新3004）     |
|  eGPU   |   ✅  |   XFX Radeon RX 580 2304SP     |
|  iGPU  | ✅    |              Intel UHD 630（无输出，辅助硬解）             |
|  内存  | ✅    |         Deler DDR4-16G 宇瞻黑豹8G-2667Mhz（X.M.P.）       |
|  硬盘  | ✅    |       华南金牌 Nvme 128GB         |
|  屏幕  | ✅    | Aigon 1920*1080 FHD  |
|  声卡  | ✅    |         Realtek ALCS1220A（内建）          |
|  无线网卡 | ✅    |  博通BCM943224PCIEBT2    |
|  有线网卡 |  ✅  |   Intel i219-V千兆以太网  |
|  睡眠  | ✅    |                原生休眠               |

# 目前情况
<ul dir="auto">
</ul>
</li>
<li><strong>睡眠</strong> 完全支持 同时实现<strong>电源小憩</strong></li>
</ul>
</li>
<li><strong>USB的S3唤醒</strong> 完全支持（仅测试华硕PRIME-Z370-A）</li>
</ul>
</li>
<li><strong>隔空投送-接力</strong> 在<code>macOS Big Sur</code>完全支持，在<code>macOS Monterey</code><code>macOS Ventura</code>只能单向，更换CS2、CD网卡解决</li>
</ul>
</li>
<li><strong>随航</strong>支持！核显UHD同时实现硬解加速</li>
</ul>
</li>
<li><strong>HDMI</strong> 完全支持
<ul dir="auto">
<li>最低分辨率1366*768，不支持1680*1050，否则可能会损坏你的显示器。3*DP与HDMI工作正常，DVI无法输出</li>
</ul>
</li>
<li><strong>独立显卡</strong> 完全支持  报错请刷VBIOS
<ul dir="auto">
<li>可以使用 <code><strong>AGPMInjector.kext</strong></code> 来获得更好的电源管理支持</li>
</ul>
</li>
<ul dir="auto">
</ul>
</li>
<li><strong>博通蓝牙</strong> 完全支持 如果是94360CS2、CD等免驱卡请自行删除<code>BlueToolFixup.kext</code><code>BrcmPatchRAM3.kext</code><code>BrcmFirmwareData.kext</code>
<ul dir="auto"> 
</ul>
</li>
<li>支持原生<strong>CPU电源管理</strong>等其他功能,已经使用<code>iMac19，1</code>来获得<code>H264</code>以及<code>HEVC</code>硬解支持</li>
</ul>
<ul dir="auto"> 
</ul>
</li>


# BIOS设置
<li>Disabe</li>
<li>Fast Boot</li>
<li>VT-D</li>
<li>CSM</li>
<li>Intel SGX</li>
<li>CFG Lock</li>
</br>
<li>Enable</li>
<li>VT-x</li>
<li>Above 4G decoding</li>
<li>Hyper-Threading</li>
<li>EHCI/XHCI Hand-off</li>
<li>OS type: Windows UEFI Mode (Clear Secure Boot Keys or choose Other type)</li>

# 使用方法
<ul dir="auto">
<li>准备安装U盘：参考OC官方配置，十分好用：<a href="https://dortania.github.io/OpenCore-Install-Guide/installer-guide/mac-install.html#setting-up-opencore-s-efi-environment" rel="nofollow">USB Creation</a>，包含macOS、Windows、Linux的U盘制作。</li>
<li>(重要)使用OCAT打开我提供的EFI的config.plist 重新生成SystemSerialNumber/SystemUUID/MLB</li>
<li>将当前提供的EFI放入U盘EFI磁盘目录下，表示使用当前EFI进行引导</li>
<li>开机配置主板各项配置，以及设置U盘UEFI启动顺序第一</li>
<li>插入U盘，选择U盘UEFI启动，进行安装系统</li>
<li>安装完成进入系统，成功!</li>
</ul>

# 双系统时间错误
<li>这是一个很常见的macOS + Windows的冲突，因为计时方式不同。</li></br>
<li>解决方式也很简单，在Windows下管理员cmd执行</li></br>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto" data-snippet-clipboard-copy-content="Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1"><pre class="notranslate"><code>Reg add HKLM\SYSTEM\CurrentControlSet\Control\TimeZoneInformation /v RealTimeIsUniversal /t REG_DWORD /d 1</code></pre></div>

# 设置默认启动项
<ul dir="auto">
<li>
<p dir="auto"><code>config.plist</code>勾上仿冒苹果快捷键<code>PollAppleHotKey</code>，在启动选择界面，先选中要启动的项，然后按键盘的 <code>Ctrl</code> + <code>Enter</code> 进入系统即可</p>
</li>
<li>
<p dir="auto">也有看到说在 <code>设置</code>-<code>启动磁盘</code> 可选择默认启动项,修改后重启</p>
</li>
</ul>

## 鸣谢
- [Acidanthera](https://github.com/acidanthera) 开发的 [OpenCore](https://github.com/acidanthera/OpenCorePkg) 和 [其他驱动](https://github.com/acidanthera)
- [Apple](https://www.apple.com) 开发的 [macOS](https://www.apple.com/macos)
