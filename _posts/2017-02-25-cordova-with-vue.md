---
layout: post
title: "使用cordova打包vue程序"
tagline: "cordova with vue"
description: ""
tags: ["总结", "vue", "cordova"]
---

#使用Cordova打包Vue WebAPP

<br>
##一、构建Vue webapp
	1、npm install -g vue-cli    //全局安装vue-cli
    
	2、vue init webpack projectName   //生成项目名为projectName的模板，这里的项目名projectName随你自己写
    
	3、cd projectName 
    
	4、npm install   //初始化安装依赖
    
	5、然后执行 npm run dev 在浏览器打开http://localhost:8080，则可以看到欢迎页了。
	
##二、构建Cordova应用
	1、在某个目录下创建cordova项目，打开命令行，输入：cordova  create  test  com.cordova.test   test  （创建cordova工程  <文件夹名> <包名> <app名>）

		hooks：存放自定义cordova命令的脚本文件。每个project命令都可以定义before和after的Hook，比如：before_build、after_build。没用过，不展开了。

		platforms：平台目录，各自的平台代码就放在这里，可以放一下平台专属的代码，现在这个目录应该是空的，后面会介绍如何创建平台。

		plugins：插件目录，安装的插件会放在这里。后面会有专门的文章介绍开发插件。

		www：最重要的目录，存放项目主题的HTML5和JS代码的目录。app一开始打开的就是这个目录中index.html文件。

		config.xml：主要是cordova的一些配置，比如：项目使用了哪些插件、应用图标icon和启动页面SplashScreen，修改app的版本，名字等信息，还有平台的配置。
	
	2、添加平台：用命令行打开对应的文件夹，输入：cordova platforms add android
		现在就可以在www文件夹内写自己的js和html代码了。（cordova platforms ls  查看支持的平台）
		移除平台：输入：cordova platforms rm android  （移除android平台支持）
		
	3、cordova build android //打包cordova项目到android平台。
	
	4、cordova run android //安装程序运行（该语句已经包括了build命令）

##三、将Vue webapp编译到Cordova
	1、打开Vue项目config/index.js
    
	2、修改下列参数：
			index:path.resolve(__dirname, '../cordova-app/www/index.html'),
			assetsRoot:path.resolve(__dirname, '../cordova-app/www'),
			assetsSubDirectory:'',
			assetsPublicPath:''
            
	3、npm run build 编译 vue-app 到 cordova-app 中
    
	4、cordova run android 运行 打包vue-app到cordova-app的webapp
	
[完毕]