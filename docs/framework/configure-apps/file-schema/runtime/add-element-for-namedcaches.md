---
title: "Элемент &lt;add&gt; для &lt;namedCaches&gt; | Microsoft Docs"
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
  - "<add> - элемент для <namedCaches>"
  - "add - элемент для <namedCaches>"
ms.assetid: ce2a63a8-c829-4742-a6ea-72ee5d89f169
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Элемент &lt;add&gt; для &lt;namedCaches&gt;
Добавляет запись `namedCache` в коллекцию `namedCaches` для кэша памяти.  
  
## Синтаксис  
  
```  
<namedCaches>  
    <add name="default" />  
      <!-- child elements -->  
 </namedCaches>  
```  
  
## Тип  
 `None`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|||  
|-|-|  
|Атрибут|Описание|  
|`CacheMemoryLimitMegabytes`|Целое значение, которое задает максимально допустимый размер \(в мегабайтах\), до которого может увеличиться объект <xref:System.Runtime.Caching.MemoryCache>.  Значение по умолчанию равно 0, что свидетельствует о том, что эвристические механизмы автоматического изменения размера класса <xref:System.Runtime.Caching.MemoryCache> используются по умолчанию.|  
|`Name`|Имя кэша.|  
|`PhysicalMemoryLimitPercentage`|Целое число от 0 до 100, задающее максимальный процент физической памяти, который может использоваться кэшем.  Значение по умолчанию равно 0, что свидетельствует о том, что эвристические механизмы автоматического изменения размера класса <xref:System.Runtime.Caching.MemoryCache> используются по умолчанию.|  
|`PollingInterval`|Значение, обозначающее интервал времени, по истечении которого реализация кэша сравнивает текущую загрузку памяти с абсолютными и относительными ограничениями памяти, заданными для экземпляра кэша.  Это значение вводится в формате "ЧЧ: ММ: СС".|  
  
### Дочерние элементы  
 `None`  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованных экземпляров <xref:System.Runtime.Caching.MemoryCache>.|  
  
## Заметки  
 Элемент `add` добавляет запись в коллекцию `namedCaches` для кэша памяти.  Элемент [clear](../../../../../docs/framework/configure-apps/file-schema/runtime/clear-element-for-namedcaches.md) можно использовать перед элементом `add`, чтобы убедиться в том, что в коллекции отсутствуют другие именованные кэши.  Этот элемент может быть использован в файле Machine.config и в файле Web.config.  
  
## Пример  
 В следующем примере показано, как определить параметры для записи `namedCache` по умолчанию в коллекции `namedCaches`  кэша памяти.  
  
```  
<configuration>  
  
  <system.runtime.caching>  
    <memoryCache>  
      <namedCaches>  
          <add name="default"   
               cacheMemoryLimitMegabytes="0"   
               physicalMemoryPercentage="0"  
               pollingInterval="00:02:00" />  
      </namedCaches>  
    </memoryCache>  
  </system.runtime.caching>  
  
</configuration>  
```  
  
## См. также  
 [Элемент \<namedCaches\> \(параметры кэша\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)