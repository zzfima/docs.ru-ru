---
title: "Разрешение безопасности перенаправления привязки сборок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "сборки [платформа .NET Framework], перенаправление привязки"
  - "параллельное выполнение, перенаправление привязки сборок"
ms.assetid: 24a5cdff-7ed9-4195-93f3-edf6899019fc
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Разрешение безопасности перенаправления привязки сборок
Для явного перенаправления привязки сборки в файле конфигурации приложения необходимо разрешение безопасности.  Это относится к перенаправлению как сборок платформы .NET Framework, так и сторонних сборок.  Разрешение можно получить путем установки флага [BindingRedirects](frlrfSystemSecurityPermissionsSecurityPermissionFlagClassTopic) в классе [SecurityPermission](frlrfSystemSecurityPermissionsSecurityPermissionClassTopic).  Управляемые сборки не имеют разрешений по умолчанию.  
  
 Разрешение безопасности предоставляется приложениям, запущенным в зоне доверенных узлов \(локальный компьютер\) и зоне интрасети.  Приложениям, запущенным в зоне Интернета, строго запрещено осуществлять перенаправление привязки сборок.  
  
 Разрешение не требуется, если перенаправление сборки выполняется в файле политики издателя, которым управляет издатель компонента, или в файле конфигурации компьютера, который контролирует администратор.  Приложению, однако, требуется разрешение, чтобы явно игнорировать политику издателя с помощью элемента [\<publisherPolicy apply\="no"\/\>](../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md) в файле конфигурации приложения.  
  
 В следующей таблице приведены параметры безопасности, установленные по умолчанию для флага **BindingRedirects**.  
  
|Зона|Параметр флага BindingRedirects|  
|----------|-------------------------------------|  
|Зона доверенных узлов \(локальный компьютер\)|**ON**|  
|Зона интрасети|**ON**|  
|Зона Интернета|**OFF**|  
|Зоны без доверия|**OFF**|  
  
 Администратор может изменить эти параметры безопасности, чтобы разрешить или запретить определенные сценарии на определенном компьютере.  Средств для изменения параметров флага **BindingRedirects** не существует; администратору потребуется вручную изменить файл Security.config на компьютере пользователя.  
  
## См. также  
 [Publisher Policy Files and Side\-by\-Side Execution](http://msdn.microsoft.com/ru-ru/97a042be-4d72-40c3-91c0-76fd36bdf133)   
 [Практическое руководство. Включение и отключение автоматического перенаправления привязки](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)   
 [Параллельное выполнение](../../../docs/framework/deployment/side-by-side-execution.md)