---
title: "Схема параметров сети | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
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
  - "параметры конфигурации [платформа .NET Framework], сети"
  - "подключения [платформа .NET Framework], элементы конфигурации сети"
  - "элементы [платформа .NET Framework], элементы конфигурации сети"
  - "Интернет, элементы конфигурации сети"
  - "элементы конфигурации сети"
  - "сетевые ресурсы, элементы конфигурации сети"
  - "сетевые параметры"
  - "получение данных, элементы конфигурации сети"
  - "отправка данных, элементы конфигурации сети"
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Схема параметров сети
Сетевые параметры определяют способ подключения платформы .NET Framework к Интернету.  В следующей таблице описываются функции каждого дочернего элемента конфигурации в [Элемент \<system.Net\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md).  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<authenticationModules\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Задает модули, используемые для проверки подлинности интернет\-запросов.|  
|[Элемент \<connectionManagement\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Задает максимальное число подключений к интернет\-узлам.|  
|[Элемент \<defaultProxy\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Задает прокси\-сервер, используемый для HTTP\-запросов в Интернете.|  
|[Элемент \<mailSettings\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Содержит значения для параметров отправки почты.|  
|[Элемент \<requestCaching\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Задает модули, используемые для запроса данных от интернет\-узлов.|  
|[Элемент \<requestCaching\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net?displayProperty=fullName>.|  
|[Элемент \<webRequestModules\> \(параметры сети\)](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от интернет\-узлов.|  
  
 Параметры универсальных кодов ресурсов \(URI\) определяют, как платформа .NET Framework обрабатывает веб\-адреса, выраженные с использованием URI.  В следующей таблице описываются функции каждого дочернего элемента конфигурации в [Элемент \<Uri\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/uri-element-uri-settings.md).  
  
|Элемент|Описание|  
|-------------|--------------|  
|[Элемент \<idn\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/idn-element-uri-settings.md)|Указывает, применяется ли синтаксический анализ IDN к именам доменов.|  
|[Элемент \<iriParsing\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/iriparsing-element-uri-settings.md)|Указывает, применяется ли синтаксический анализ международного имени ресурса \(IRI\) к <xref:System.Uri>, а также следует ли применять правила синтаксического анализа IRI.|  
|[Элемент \<schemeSettings\> \(параметры URI\)](../../../../../docs/framework/configure-apps/file-schema/network/schemesettings-element-uri-settings.md)|Указывает, как <xref:System.Uri> будет анализироваться по конкретным схемам.|  
  
## См. также  
 [Настройка веб\-приложений](../../../../../docs/framework/network-programming/configuring-internet-applications.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)