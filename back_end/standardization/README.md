## 一、项目结构规约


```
[weiyiacen@bigdata-1 autopai-cloud-parent (master)]$ tree -L 1
.
├── autopai-cloud-demo
├── autopai-cloud-device
├── autopai-cloud-echo
├── autopai-cloud-echo-api
├── pom.xml
└── README.md
```

结构模块说明：

autopai-cloud-demo：示例项目，RPC调用echo服务

autopai-cloud-echo：示例项目，实现echo服务

autopai-cloud-echo-api：echo项目对外RPC接口，提供给对外项目调用时引入。此包仅提供接口，不能引入无用的第三方依赖。


## 二、包命名规约

域名.公司名.项目名.层级名

eg:  com.autopai.pay.web 

com.autopai.pay.service

com.autopai.pay.dao


### 二、maven 规约

1.父pom规范：

```
<groupId>com.${公司标识}.${项目标识}</groupId>
<artifactId>${项目标识}-${业务项目标识}</artifactId>
<version>1.0.0</version>
<packaging>pom</packaging>
```

demo:

```
<groupId>com.wtcar.ota</groupId>
<artifactId>ota-pom</artifactId>
<version>1.0.0</version>
<packaging>pom</packaging>
```

2.子pom规范

```
<groupId>com.${公司标识}.${业务项目标识}</groupId>
<artifactId>${业务项目标示}-${模块标识}</artifactId>
<version>1.0.0</version>
```

demo:

```
<groupId>com.wtcar.ota</groupId>
<artifactId>ota-web</artifactId>
<version>1.0.0</version>
```

3.模块名规范

```
<name>autopai-${业务项目标识}-${模块标识}</name>
```