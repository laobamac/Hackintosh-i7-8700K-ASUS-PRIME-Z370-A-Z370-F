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

#### 修改开始
- 重启到`WIndows`或者`WinPe`都可以
- 打开`DiskGenius`
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/DG-1.png)
- 找到你u盘的`ESP`分区并把`EFI`复制到桌面即可
- 然后找到你的`硬盘` `ESP`分区（注意是这里要是`WINDOWS的ESP`）
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/DG-2.png)
- 点开`EFI`文件夹把刚才拷贝到的桌面的`EFI`里面的`OC`文件夹丢到`EFI`里面
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/DG-3.png)
- 然后点击顶部菜单栏的`工具`-`设置` `UEFIBIOS`启动项
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/DG-4.png)
- 添加一个启动项，把路径指向`ESP-EFI-OC-OpenCore.efi`即可
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/DG-5.png)
- 把这个启动项修改一下名字上移到第一位`保存`即可
### 英特尔wifi
- WIFI请加载驱动包对应版本驱动
### 英特尔蓝牙
- bigsur：`IntelBluetoothFirmware.kext`
- Monterey：`IntelBluetoothFirmware.kext` `BlueToolFixup.kext`
- Ventura：`IntelBluetoothFirmware.kext` `BlueToolFixup.kext` `IntelBTPatcher.kext`
### 开机优化
- 三星硬盘`trim`会导致开机慢
- 解决方法：`SetApfsTrimTimeout`设置为`0`
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/%E7%A1%AC%E7%9B%98-1.png)

### 设置默认启动项
- `config.plist`勾上仿冒苹果快捷键`PollAppleHotKey`，在启动选择界面，先选中要启动的项，然后按键盘的 `Ctrl` + `Enter` 进入系统即可
- 也有看到说在 `设置`-`启动磁盘` 可选择默认启动项,修改后重启
### 更新oc
- 下载最新版本`OCAT`(https://github.com/ic005k/OCAuxiliaryTools/releases)
- 挂载你的`efi`分区（也叫`esp`分区）
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/%E6%9B%B4%E6%96%B0oc-1.jpg)
- 挂载后先不要着急打开，先把`OCAT`（即`OCAuxiliaryTools`）同步一下再打开
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/%E6%9B%B4%E6%96%B0oc-2.jpg)
- 然后再打开`Config.plist`。首先点击全选，然后`检查kext`更新，更新`kext`，后点击选择`opencore版本`，选择`最新版`，`获取opencore`，后点击`同步` `保存`即可
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/%E6%9B%B4%E6%96%B0oc-3.jpg)
- 保存重启即可
  ![Image text](https://github.com/Win10Q/hackintosh-with-B560-msi-asus/blob/main/img-storage/%E6%9B%B4%E6%96%B0oc-4.jpg)

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
