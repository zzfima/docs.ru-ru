---
title: "Элемент &lt;WebProxyScript&gt; (сетевые параметры) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#webProxyScript"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/webProxyScript"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "элемент <webProxyScript>"
  - "webProxyScript - элемент"
ms.assetid: a13c26db-6218-4af3-9696-38f24b23bfac
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;WebProxyScript&gt; (сетевые параметры)
Настройка характеристик скрипта, используемого для обнаружения веб\-прокси.  
  
## Синтаксис  
  
```  
  
      <webProxyScript  
  downloadTimeout="hh:mm:ss"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`downloadTimeout`|Максимальное время на загрузку скрипта в часах, минутах и секундах.  Значение по умолчанию — одна минута.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net>.|  
  
## Заметки  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## См. также  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)