---
layout: post
title: "ʹ��cordova���vue����"
tagline: "cordova with vue"
description: ""
tags: ["�ܽ�", "vue", "cordova"]
---

#ʹ��Cordova���Vue WebAPP

<br>
##һ������Vue webapp
	1��npm install -g vue-cli    //ȫ�ְ�װvue-cli
    
	2��vue init webpack projectName   //������Ŀ��ΪprojectName��ģ�壬�������Ŀ��projectName�����Լ�д
    
	3��cd projectName 
    
	4��npm install   //��ʼ����װ����
    
	5��Ȼ��ִ�� npm run dev ���������http://localhost:8080������Կ�����ӭҳ�ˡ�
	
##��������CordovaӦ��
	1����ĳ��Ŀ¼�´���cordova��Ŀ���������У����룺cordova  create  test  com.cordova.test   test  ������cordova����  <�ļ�����> <����> <app��>��

		hooks������Զ���cordova����Ľű��ļ���ÿ��project������Զ���before��after��Hook�����磺before_build��after_build��û�ù�����չ���ˡ�

		platforms��ƽ̨Ŀ¼�����Ե�ƽ̨����ͷ���������Է�һ��ƽ̨ר���Ĵ��룬�������Ŀ¼Ӧ���ǿյģ�����������δ���ƽ̨��

		plugins�����Ŀ¼����װ�Ĳ�����������������ר�ŵ����½��ܿ��������

		www������Ҫ��Ŀ¼�������Ŀ�����HTML5��JS�����Ŀ¼��appһ��ʼ�򿪵ľ������Ŀ¼��index.html�ļ���

		config.xml����Ҫ��cordova��һЩ���ã����磺��Ŀʹ������Щ�����Ӧ��ͼ��icon������ҳ��SplashScreen���޸�app�İ汾�����ֵ���Ϣ������ƽ̨�����á�
	
	2�����ƽ̨���������д򿪶�Ӧ���ļ��У����룺cordova platforms add android
		���ھͿ�����www�ļ�����д�Լ���js��html�����ˡ���cordova platforms ls  �鿴֧�ֵ�ƽ̨��
		�Ƴ�ƽ̨�����룺cordova platforms rm android  ���Ƴ�androidƽ̨֧�֣�
		
	3��cordova build android //���cordova��Ŀ��androidƽ̨��
	
	4��cordova run android //��װ�������У�������Ѿ�������build���

##������Vue webapp���뵽Cordova
	1����Vue��Ŀconfig/index.js
    
	2���޸����в�����
			index:path.resolve(__dirname, '../cordova-app/www/index.html'),
			assetsRoot:path.resolve(__dirname, '../cordova-app/www'),
			assetsSubDirectory:'',
			assetsPublicPath:''
            
	3��npm run build ���� vue-app �� cordova-app ��
    
	4��cordova run android ���� ���vue-app��cordova-app��webapp
	
[���]