---
title: "Элемент &lt;startup&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/startup"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#startup"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<startup> - элемент"
  - "теги контейнеров, <startup> - элемент"
  - "startup - элемент"
ms.assetid: 536acfd8-f827-452f-838a-e14fa3b87621
caps.latest.revision: 19
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 19
---
# Элемент &lt;startup&gt;
Указывает общие сведения о среде CLR.  
  
## Синтаксис  
  
```  
<startup useLegacyV2RuntimeActivationPolicy="true|false" >   
</startup>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`useLegacyV2RuntimeActivationPolicy`|Необязательный атрибут.<br /><br /> Указывает, следует включить политику активации среды выполнения [!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)] или следует использовать политику активации [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].|  
  
## Атрибут useLegacyV2RuntimeActivationPolicy  
  
|Значение|Описание|  
|--------------|--------------|  
|`true`|Включите политику активации для выбранной среды выполнения[!INCLUDE[dnprdnext](../../../../../includes/dnprdnext-md.md)], которая должна связать методы выполнения выполнения активации прежних версий \(например, [CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)\) со средой выполнения, выбранной в конфигурационном файле, вместо их ограничения в среде CLR версии 2.0.  Таким образом, если CLR версии 4 или более поздней выбирается из файла конфигурации, смешанный режим сборки, созданные с более ранних версий .NET Framework, загружаются с выбранной версией среды CLR.  Установка этого значения предотвращает для CLR 1.1 или 2.0 загрузку в этот же процесс, эффективно отключая функции внутрипроцессного параллельного выполнения.|  
|`false`|Используйте активации политики по умолчанию для [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] и более поздней версии, который позволят методам выполнения активации прежних версий загрузить среду CLR версии 1.1 или 2.0 в этот процесс.  Установка этого значения предотвращает загрузку в смешанном режиме сборки в .NET Framework 4 или более поздней версии, если они не были построены с помощью .NET Framework 4 или более поздней версии. Это значение является значением по умолчанию.  Это значение по умолчанию.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<requiredRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)|Указывает, что приложение поддерживает только версию 1.0 среды CLR.  Приложения, построенные с помощью среды выполнения версии 1.1 или более поздней, должны использовать элемент **\<supportedRuntime\>**.|  
|[\<supportedRuntime\>](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)|Указывает, какие версии среды CLR поддерживает приложение.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
  
## Заметки  
 Элемент **\<supportedRuntime\>** должен использоваться всеми приложениями, собранными с помощью среды выполнения версии 1.1 или более поздней.  Приложения, собранные для поддержки только версии 1.0 среды выполнения, должны использовать элемент **\<requiredRuntime\>**.  
  
 Код запуска для приложения, выполняемого в Microsoft Internet Explorer, не обрабатывает элемент **\<startup\>** и его дочерние элементы.  
  
## Атрибут useLegacyV2RuntimeActivationPolicy  
 Этот атрибут полезен, если ваше приложение использует пути активации прошлых версий, такие как функция [CorBindToRuntimeEx](../../../../../ocs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), и хотите использовать пути активации CLR версии 4 вместо более ранней версии, или если построение приложения выполняется [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], но имеет зависимость от смешанного режима построения сборки с более ранней версией .NET Framework.  В таких сценариях задайте атрибуту значение `true`.  
  
> [!NOTE]
>  Установка атрибута в `true` предотвращает для CLR 1.1 или 2.0 загрузку в этот же процесс, эффективно отключая функции внутрипроцессного параллельного выполнения \(см. [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/ru-ru/4302318c-3586-49bf-8620-b9a39cdf4a32)\).  
  
## Пример  
 В следующем примере показан способ указания в файле конфигурации версии среды выполнения.  
  
```  
<!-- When used with version 1.0 of the .NET Framework runtime -->  
<configuration>  
   <startup>  
      <requiredRuntime version="v1.0.3705" safemode="true"/>  
   </startup>  
</configuration>  
<!-- When used with version 1.1 (or later) of the runtime -->  
<configuration>  
   <startup>  
      <supportedRuntime version="v1.1.4322"/>  
      <supportedRuntime version="v1.0.3705"/>  
   </startup>  
</configuration>  
```  
  
## См. также  
 [Схема параметров запуска](../../../../../docs/framework/configure-apps/file-schema/startup/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<PaveOver\> Specifying Which Runtime Version to Use](http://msdn.microsoft.com/ru-ru/c376208d-980d-42b4-865b-fbe0d9cc97c2)   
 [Side\-by\-Side Execution for COM Interop](http://msdn.microsoft.com/ru-ru/4302318c-3586-49bf-8620-b9a39cdf4a32)   
 [Внутрипроцессное параллельное выполнение](../../../../../docs/framework/deployment/in-process-side-by-side-execution.md)