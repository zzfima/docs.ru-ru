---
title: "Элемент &lt;system.web&gt; (Веб-параметры) | Microsoft Docs"
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
  - "<system.Web> - элемент"
  - "система конфигурации ASP.NET"
  - "файлы конфигурации [ASP.NET]"
  - "system.Web - элемент"
  - "Web.config - файл конфигурации [ASP.NET]"
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Элемент &lt;system.web&gt; (Веб-параметры)
Содержит сведения о том, как уровень размещения ASP.NET управляет поведением на уровне всего процесса.  
  
## Синтаксис  
  
```  
<system.web>  
</system.web>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<applicationPool\>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Указывает параметры конфигурации для пулов приложений IIS в файле aspnet.config.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<configuration\>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Указывает корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
  
## Заметки  
 Элемент `system.web` и его дочерний элемент `applicationPool` были добавлены в [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] начиная с версии [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].  При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в интегрированном режиме это сочетание элементов позволяет настроить, как ASP.NET управляет потоками и как помещает запросы в очередь, когда ASP.NET размещен в пуле приложений IIS.  При запуске [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] или более поздних версий в классическом режиме или режиме ISAPI эти параметры игнорируются.  
  
## Пример  
 В следующем примере показано, как настроить в файле aspnet.config поведение ASP.NET на уровне всего процесса, когда ASP.NET размещен в пуле приложений IIS.  В примере предполагается, что службы IIS выполняются в интегрированном режиме, а приложение использует [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] или более позднюю версию.  Указанное поведение не имеет места в версиях [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] до [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)].  Значения, указанные в примере, являются значениями по умолчанию.  
  
```  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## Сведения об элементе  
  
|||  
|-|-|  
|Пространство имен||  
|Имя схемы||  
|Файл проверки||  
|Может быть пустым||  
  
## См. также  
 [Элемент \<applicationPool\> \(Веб\-параметры\)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)