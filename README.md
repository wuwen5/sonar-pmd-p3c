# SonarQube PMD Plugin [![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.sonarsource.pmd/sonar-pmd-plugin/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.sonarsource.pmd/sonar-pmd-plugin) [![Build Status](https://api.travis-ci.org/jensgerdes/sonar-pmd.svg?branch=master)](https://travis-ci.org/jensgerdes/sonar-pmd) [![SonarStatus](https://sonarcloud.io/api/project_badges/measure?project=org.sonarsource.pmd%3Asonar-pmd-plugin&metric=alert_status)](https://sonarcloud.io/dashboard?id=org.sonarsource.pmd%3Asonar-pmd-plugin) [![SonarStatus](https://sonarcloud.io/api/project_badges/measure?project=org.sonarsource.pmd%3Asonar-pmd-plugin&metric=coverage)](https://sonarcloud.io/dashboard?id=org.sonarsource.pmd%3Asonar-pmd-plugin)
Sonar-PMD is a plugin that provides coding rules from [PMD](https://pmd.github.io/).

## Description / Features
PMD Plugin|2.0|2.1|2.2|2.3|2.4.1|2.5|2.6|3.0.0|3.1.x|3.2.x
-------|---|---|---|---|---|---|---|---|---|---
PMD|4.3|4.3|5.1.1|5.2.1|5.3.1|5.4.0|5.4.2|5.4.2|6.9.0|6.10.0
Max. supported Java Version | |  |  |  |  | 1.7 | 1.8 | 1.8 | 11 |
Min. SonarQube Version |  |  |  |  |  | 4.5.4 | 4.5.4 | 6.6 | 6.6 |

A majority of the PMD rules have been rewritten in the Java plugin. Rewritten rules are marked "Deprecated" in the PMD plugin, but a [concise summary of replaced rules](http://dist.sonarsource.com/reports/coverage/pmd.html) is available.

## Usage
In the quality profile, activate some rules from PMD and run an analysis on your project.
Set the sonar.java.source property to tell PMD which version of Java your source code complies to. The default value is 1.6. 

Possible values: 
- 1.4
- 1.5 or 5 
- 1.6 or 6 
- 1.7 or 7 
- 1.8 or 8
- 9
- 10
- 11

## Rules on test
PMD tool provides some rules that can check the code of JUnit tests. Please note that these rules (and only these rules) will be applied only on the test files of your project.

## License
Licensed under the [GNU Lesser General Public License, Version 3.0](https://github.com/jensgerdes/sonar-pmd/blob/master/LICENSE.md)

## 备注 
在官方仓库tag中的3.2.1版本和alibaba/p3c的2.0.0版本上开发。
使用参考：
1.  使用mvn clean package -DskipTests打包后将jar包上传到SonarQube extensions/plugins目录下后再重启SonarQube服务即可完成Sonar插件的部署
2.  有管理员权限的账号登陆SonarQube后点击顶部菜单的“代码规则”，在页面中点击“资源库”，下方出现“PMD P3C Java 55”即代表插件没有问题。其中“Java”代表适用于Java语言，“55”代表有55条规则。
3.  点击顶部菜单的“质量配置”页面“Java配置”，默认的“Sonar way”不支持修改，点击后面箭头的“复制”，然后在复制出的配置中将刚才的“PMD P3C”的55条规则添加到此配置中，然后将此配置激活设置成默认即可。
4.  新分析的即可在SonarQube中查看到P3C的规则已经生效。