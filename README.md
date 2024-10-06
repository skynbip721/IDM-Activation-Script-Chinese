# IDM 激活脚本

一个开源工具，用于激活和重置 [Internet Download Manager](https://www.internetdownloadmanager.com/) 的试用版

原作者英语版本仓库地址 [GitHub](https://github.com/lstprjct/IDM-Activation-Script)

警告：以下翻译内容可能含有机器翻译，请自行辨别。

# 免责声明

以下为原仓库内容

I want to clarify that I am not the original author of this script. When I initially published this script on GitHub, the primary author had not yet created an official GitHub repository. As a result, the only available option for users was to visit the [official forum](https://www.nsaneforums.com/topic/371047--/?do=findComment%5E&comment=1578647) to download and utilize the script, later they created the [Github](https://github.com/WindowsAddict/IDM-Activation-Script) repository. My main aim in creating this repository was to streamline the process for users. Furthermore, I ensured to credit the original creators of the script as a sign of respect for their work.

# 功能

* 使用注册表项锁定方法进行IDM冻结试验和激活
* 即使在安装IDM更新后，激活和试用仍然有效
* IDM试验重置
* 完全开源
* 基于透明批处理脚本

# IAS 最新版本（中文版）

最新版本-v1.2（2024年10月6日）(中文版）

[GitHub](https://github.com/cjhdevact/IDM-Activation-Script/Chinese)

原版

[GitHub](https://github.com/lstprjct/IDM-Activation-Script)

# 下载 / 如何使用？

首次全新安装[Internet Download Manager](https://www.internetdownloadmanager.com/)。 确保之前的破解/补丁已被移除/卸载（如果有的话）。

之后，按照以下步骤激活它。

# 注意事项

* 📌 激活选项当前在脚本中不起作用，请使用冻结试用选项在生命周期内锁定30天的试用期。

# 方法1（建议）

* 从[GitHub]下载文件(https://github.com/cjhdevact/IDM-Activation-Script-Chinese/archive/refs/heads/main.zip)
* 右键单击下载的zip文件并解压缩
* 在提取的文件夹中，运行名为`IAS.cmd`的文件
* 您将看到激活选项，并按照屏幕上的说明进行操作。
* 即可使用

# 方法2-PowerShell（原作者英语版本）
* 右键单击Windows开始菜单，然后选择PowerShell或终端（非CMD）。
* 复制粘贴以下代码，然后按enter键
* `iex(irm is.gd/idm_reset)`
* 您将看到激活选项，请按照屏幕上的说明进行操作。
* 即可使用

# 信息

## 冷冻试用
* IDM提供30天的试用期，您可以在脚本中使用此选项将此试用期锁定为终身，这样您就不必再次重置试用期，试用期也不会过期。
* 此方法在应用此选项时需要互联网。
* IDM更新可以直接安装，无需再次冻结。

## 激活
（**当前不工作**）

* 此脚本应用注册表锁定方法来激活Internet下载管理器（IDM）。
* 此方法在激活时需要互联网。
* IDM更新可以直接安装，无需再次激活。
* 激活后，如果在某些情况下，IDM开始显示激活提示屏幕，则只需再次运行激活选项，而不使用重置选项。

## 重置IDM激活/试用
*Internet下载管理器提供30天的试用期，您可以随时使用此脚本重置此激活/试用期。
*如果IDM报告假序列密钥和其他类似错误，此选项也可用于恢复状态。

## 操作系统要求
* 该项目支持 Windows 7/8/8.1/10/11 及其服务器等效版本。
* Windows 8及更高版本支持运行IAS的PowerShell方法。

## 高级信息
* 要在无人值守模式下激活，请使用/act参数运行脚本。
* 要在无人值守模式下冻结试用，请使用/frz参数运行脚本。
* 要在无人值守模式下重置，请使用/res参数运行脚本。

# 它是如何工作的？
* IDM跨各种注册表项存储与试用和激活相关的数据。其中一些密钥被锁定以防止篡改，数据以一种模式存储，以跟踪假序列问题和剩余的试用期。要激活它，这里的脚本只需通过触发IDM中的一些下载来生成这些注册表项，识别这些注册表项并锁定它们，这样IDM就无法编辑和查看它们。这样IDM就不会显示使用假串行密钥激活的警告。

# 故障排除
* 浏览器集成修复程序：[Chrome](https://www.internetdownloadmanager.com/register/new_faq/bi9.html) - [火狐浏览器](https://www.internetdownloadmanager.com/register/new_faq/bi4.html)

# 更新日志
## v1.2
* Added back activation option with a randomized name, email, and key in registration details along with a warning that it’s not working for some users, the recommended option is to use Freeze trial.
## v1.1
* IDM update 6.42b3 has started showing fake serial popups with IAS activation, due to this we have removed the activation option and replaced it with the Freeze trial option to lock the 30-day trial period for the lifetime.
* Now the script will disable quick-edit in CMD windows using Powershell instead of editing the registry, thanks to @abbodi1406 for the code and @awuctl for the idea.
* Code to relaunch script with conhost.exe to avoid terminal app is now merged in quick-edit disable code, thanks to @abbodi1406.
Updated full code from [WindowsAddict ](https://massgrave.dev/idm-activation-script)
## v1.0
* Added the code to relaunch the script with conhost.exe if the script is running from the terminal app.
* Fixed an issue in getting the current user account SID.
## v0.9
* Fixed an issue where the script can not activate and reset IDM in non-admin user accounts.
* Fixed an issue where the script incorrectly shows that IDM is activated.
* Fixed an issue where a fake serial pop-up may appear. The script will also show the info to run the activation option again without using the reset option.
* IDM registry scanning and locking code is now written in Powershell.
* The script update checker code is added to the script.
* The script will now disable quick edit mode temporarily because users often click inside the script window and it pauses the script.
* The script will back up the CLSISD registry keys before performing operations on them.
* Many error checks are added to better identify the issues.
## v0.8
* Move the project to [Github](https://github.com/lstprjct/IDM-Activation-Script)
* Minor bug fixes
* Add info to inform users that empty registry keys are being deleted when the script deletes a lot of them

# 截图
![IAS](https://github.com/lstprjct/IDM-Activation-Script/assets/88411318/fafdb481-c497-464f-b1e6-9a4254eaf880)

![IAS_Freeze_Trial](https://github.com/lstprjct/IDM-Activation-Script/assets/88411318/76b36582-8cf4-4d1e-870f-6e8e57c80a87)

# 贡献者

|                                             |                                                                                                                                                                                                                                        |
|-------------------|-----------------------------------------------------|
| Dukun Cabul                                 | Original researcher of this IDM trial reset and activation logic, made an Autoit tool for these methods, [IDM-AIO_2020_Final](https://nsaneforums.com/topic/371047-discussion-internet-download-manager-fixes/page/8/#comment-1632062) |
| AveYo aka BAU                               | [reg_own lean and mean snippet](https://pastebin.com/XTPt0JSC)                                                                                                                                                                         |
| [abbodi1406](https://github.com/abbodi1406) | Help in coding                                                                                                                                                                                                                         |
| WindowsAddict                               | Original [IAS](https://github.com/WindowsAddict/IDM-Activation-Script) Author                                                                                                                                                                                                                             |

And thanks to the IAS users for their interest, feedback, and assistance.

------------------------------------------------------------------------

Made with Love ❤️
