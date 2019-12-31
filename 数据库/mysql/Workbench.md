# Workbench文档

[mysql workbench如何把已有的数据库导出ER模型](https://www.cnblogs.com/xiaoqian1993/p/6225037.html)

## 导出数据到Excel

导出CSV文件

- 选中想导出的表，右键，选中TableDataExportWizard
- 选择需要导出的列，点击next
- 选择文件保存位置，格式为csv
- 点击next,点击Finish

Excel打开中文乱码：用记事本打开，选择另存为，编码选为ANSI。

CSV文件转Excel文件

- 选中第一列
- 选中菜单栏：数据，点击分列，下一步
- 选择分隔符号为tab键和分号，
- 是否覆盖原数据：是

## 将数据从Excel导入到MySql

将Excel另存为csv，再将csv的格式在记事本里改为utf-8，然后在Mysql Workbench里操作就可以了

注意：Excel的表结构要和MySql里的表结构一致，可以新建一个表保存对应的数据。
