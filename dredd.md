# dredd 使用简述
## 是什么
dredd是HTTP API测试框架，口号：No more outdated API Documentation。
## 原理
它根据后端API的实现来验证API文档描述的有效性。具体的是逐步读取API文档，发送请求到后端，验证后端的响应是否和文档描述一致
## 支持的API描述文档格式
1. API BluePrint
2. OpenAPI 2(Swagger)
3. OpenAPI 3(实验中)
## 使用
### 预安装环境
Node.js
### 1. 安装dredd
```shell
npm install -g dredd
```
### 2. 书写您的API文档
以API Blueprint或者OpenAPI 2的格式书写API文档，当然如果您后端基于Spring Boot,引入springfox包，加上少量的注解，
便可以直接获得对应的swagger文档。
### 3. 准备API接口
比如后端基于SpringBoot,直接bootRun应用
### 4. 测试API接口
假定我们已准备好API文档api.json,我们的后端应用运行在localhost上，那么进入api.json所在的目录，运行如下命令
```shell
dredd api.json http://localhost 
```
就这么简单，dredd会在命令行会输出测试报告。
