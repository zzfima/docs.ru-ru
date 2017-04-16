---
title: "Элемент &lt;appDomainResourceMonitoring&gt; | Microsoft Docs"
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
  - "<appDomainResourceMonitoring> - элемент"
  - "appDomainResourceMonitoring - элемент"
ms.assetid: 02119ab6-1e91-448e-97ad-e7b2e5c4bbbd
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Элемент &lt;appDomainResourceMonitoring&gt;
Указывает среде выполнения собирать статистические данные по всем доменам приложений в процессе за весь период существования процесса.  
  
## Синтаксис  
  
```  
<appDomainResourceMonitoring    
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, собирает ли среда выполнения статистические данные для отслеживания ресурсов домена приложения.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`true`|Статистические данные для отслеживания ресурсов домена приложения собираются.|  
|`false`|Статистические данные для отслеживания ресурсов домена приложения не собираются.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Отслеживание ресурсов домена приложения доступно через класс управляемого домена приложения, интерфейс размещения [ICLRAppDomainResourceMonitor](../../../../../ocs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md) и трассировку событий Windows \(ETW\).  Если отслеживание включено, статистические данные собираются для всех доменов приложений в процессе за весь период существования процесса.  
  
 Чтобы включить отслеживание из управляемого кода, используйте свойство <xref:System.AppDomain.MonitoringIsEnabled%2A>.  
  
 Этот элемент конфигурации доступен только в [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] или более поздних версиях.  
  
## Пример  
 Следующий пример показывает, как включить отслеживание ресурсов домена приложения.  
  
```  
<configuration>  
   <runtime>  
      <appDomainResourceMonitoring enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=fullName>   
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)