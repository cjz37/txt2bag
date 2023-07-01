# INS数据：txt转bag

## 一、自定义参数

### 1、launch/startup.launch

- 自定义frame_id
- 自定义数据文件路径(输入输出同文件夹)
- 自定义输入输出文件名

```xml
5:| <param name="frame_id" value="odom">
6:| 
7:| <arg name="file_path" default="[workspace path]/src/txt2bag/data/"/>
8:| <arg name="input_file" default="ins.txt"/>
9:| <arg name="output_file" default="ins.bag"/>
```

### 2、launch/showrviz.launch

- 自定义数据文件路径(输入输出同文件夹)
- 自定义输入输出文件名

```xml
5:| <arg name="file_path" default="[workspace path]/src/txt2bag/data/"/>
6:| <arg name="output_file" default="ins.bag"/>
```



## 二、使用

### 1、转换

```shell
$ roslaunch txt2bag startup.launch
```

### 2、查看bag以及rviz显示

```shell
$ roslaunch txt2bag showrviz.launch
```
