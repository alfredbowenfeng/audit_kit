# Audit Kit

由于通过VBA爬客编表的效率较低，导致公司电脑在爬表过程中死机而影响工作，此 audit_kit Python 版本根据`ABASToolkit.xlam`爬表思路编写。慢慢更新，如有 Python 脚本的需求 :+1: 以及改进意见 :-1:，请联系作者 [@alfredbowenfeng](https://github.com/alfredbowenfeng)，邮箱是 alfred.bowenfeng@gmail.com。

使用 Python 初始配置可能看起来比较麻烦，实际上只要一次性花5分钟左右的时间安装、配置、安装包，以后爬表的同时，可以用电脑运行其他应用软件，避免死机而无法继续工作的问题。

## Table of Contents
- [Python 的配置](#installation)
- [Breakdown by Value](#breakdown_value)
- [Breakdown by Link](#breakdown_link)

<a name="installation"></a>
## Python 的配置

#### Python 的下载
* 请在[官网](https://www.python.org/downloads/)下载，黄色图标 Download Python 3.6.5。

#### Windows 10 安装与环境搭建
* 请在C盘新建名为"Python"的文件夹，以管理员身份打开 Python 安装软件，通过自定义安装，将 Python 安装于"C:\Python"目录下。（如遇到安装原因，选择"Client Engagement"或其他任意原因即可）
* 右键点击"计算机"，点击"属性"，点击"高级系统设置"。
* 此时看到"用户变量"与"系统变量"，选择"系统变量"下的"Path"，点击编辑。
* 点击"新增"，输入"C:\Python"，确定。
* 点击"新增"，输入"C:\Python\Scripts"，确定。

#### 使用 cmd 与 pip 命令安装包
* Python 处理 Excel 文件需要一些功能包，所以用系统自带的 cmd 安装。
* 按"START + R"搜索 cmd 并打开。
* 输入"pip install" + "安装包名称" 并回车，等待安装完成。
* 例如输入"pip install xlrd"并回车，等待 xlrd 包安装完成。

#### 脚本的使用
* Python 的脚本是后缀为".py"的文件，待 Python 安装完成后，用 IDLE 打开文件。
* 按"F5"运行文件，根据提示操作即可。

<a name="breakdown_value"></a>
## Breakdown by Value

#### 输入端路径
* 第1步：输入文件（们）所在目录，可直接从窗口中复制粘贴，务必添加"\\"并以"\\"结尾，例如"C:\Audit\Engagement\\"。
* 注：若经常使用同一路径，则可以编辑.py文件，例如修改第11行：

~~ImportFileDirectory = str(input(r'''Please enter Import File Directory: (eg. "C:\Users\Alfred.Feng\Desktop\\") '''))~~

ImportFileDirectory = r'C:\Audit\Engagement\\' （举例）

#### 定位
* 第2步：输入 worksheet 的名字，例如"Sheet1"，请精准输入。
* 第3步：输入"开始列"，务必为大写的英文字母（例如"A"）。
* 第4步：输入"开始行"，务必为数字（例如"1"）。
* 第5步：输入"结束列"，务必为大写的英文字母（例如"AH"）。
* 第6步：输入"结束行"，务必为数字（例如"1001"）。

#### 结果输出
* 第7步：输入"输出路径"，务必以".xlsx"结尾，例如"C:\Audit\Engagement\breakdown.xlsx"。
* 注1：Python 不像 VBA 可直接输入"A1"或"AH1001"来开始与结尾，所以需将字母与数字分开。
* 注2：此脚本已默认utf-8编码，应该来说运行后中文处理不会存在乱码，若存在乱码请联系作者。
* 注3：此脚本仅爬取 value ，如需建立 link 请使用 [Breakdown by Link](#breakdown_link)。

<a name="breakdown_link"></a>
## Breakdown by Link

#### 输入端路径
* 第1步：输入文件（们）所在目录，可直接从窗口中复制粘贴，务必添加"\\"并以"\\"结尾，例如"C:\Audit\Engagement\\"。
* 注：若经常使用同一路径，则可以编辑.py文件，例如修改第10行：

~~ImportFileDirectory = str(input(r'''Please enter Import File Directory: (eg. "C:\Users\Alfred.Feng\Desktop\\") '''))~~

ImportFileDirectory = r'C:\Audit\Engagement\\' （举例）

#### 定位
* 第2步：输入 worksheet 的名字，例如"Sheet1"，请精准输入。
* 第3步：输入"开始列"，务必为大写的英文字母（例如"A"）。
* 第4步：输入"开始行"，务必为数字（例如"1"）。
* 第5步：输入"结束列"，务必为大写的英文字母（例如"AH"）。
* 第6步：输入"结束行"，务必为数字（例如"1001"）。

#### 结果输出
* 第7步：输入"输出路径"，务必以".xlsx"结尾，例如"C:\Audit\Engagement\breakdown.xlsx"。
* 注1：Python 不像 VBA 可直接输入"A1"或"AH1001"来开始与结尾，所以需将字母与数字分开。
* 注2：此脚本已默认utf-8编码，应该来说运行后中文处理不会存在乱码，若存在乱码请联系作者。
* 注3：此脚本仅建立 link ，如需爬取 link 请使用 [Breakdown by Value](#breakdown_value) 。
* 注4：通过 Python 处理的 "Paste Link" 回到 Excel 时可能需要更新数值，请选择"Ignore Links"、全选数据、复制、并在新的单元格粘贴（或者 Transpose 适用于不同情景）。