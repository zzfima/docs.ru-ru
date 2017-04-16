---
title: "HttpListener | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "HTTP"
ms.assetid: 5b89d3fb-3c9a-49e2-af1f-c34c020c68ac
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# HttpListener
Класс <xref:System.Net.HttpListener> предоставляет программно управляемый прослушиватель протокола HTTP.  Прослушиватель активен в течение времени существования <xref:System.Net.HttpListener> объекта и выполняется в приложении.  
  
## HTTP.SYS  
 Класс <xref:System.Net.HttpListener> построен на базе HTTP.sys, который является прослушивателем режима ядра, обрабатывающим весь трафик HTTP для Windows.  HTTP.sys обеспечивает управление соединениями, регулирование полосы пропускания и ведение журналов веб\-сервера.  Используйте средство `HttpCfg.exe` для добавления SSL\-сертификатов.  Дополнительные сведения см. в описании средства [HttpCfg.exe](http://go.microsoft.com/fwlink/?LinkID=178284) в документации по [серверу](http://go.microsoft.com/fwlink/?LinkID=178285).  
  
## См. также  
 <xref:System.Net.HttpListener>   
 <xref:System.Net.HttpWebRequest>   
 <xref:System.Net.HttpWebResponse>   
 [HTTP\-сервер](http://go.microsoft.com/fwlink/?LinkID=178285)   
 [Усовершенствования системы безопасности Internet Information](http://go.microsoft.com/fwlink/?LinkID=178286)   
 [Пример хост\-приложения ASPX HttpListener](http://go.microsoft.com/fwlink/?LinkID=179560)   
 [Пример технологии HttpListener](http://go.microsoft.com/fwlink/?LinkID=179558)   
 [Примеры сетевого программирования](../../../docs/framework/network-programming/network-programming-samples.md)