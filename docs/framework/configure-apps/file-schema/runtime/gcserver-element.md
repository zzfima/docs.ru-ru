---
title: "Элемент &lt;gcServer&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<gcServer> - элемент"
  - "gcServer - элемент"
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# Элемент &lt;gcServer&gt;
Указывает, выполняет ли среда CLR сборку мусора сервера.  
  
## Синтаксис  
  
```  
<gcServer    
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Указывает, выполняет ли среда выполнения сборку мусора сервера.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Не выполняет сборку мусора сервера.  Это значение по умолчанию.|  
|`true`|Выполняет сборку мусора сервера.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Среда CLR поддерживает два типа сборки мусора: сборку мусора рабочей станции, которая доступна во всех системах, и сборку мусора сервера, которая доступна в многопроцессорных системах.  Для управления типом сборки мусора среды CLR можно использовать элемент `<gcServer>`.  Используйте свойство <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=fullName>, чтобы определить, включена ли сборка мусора сервера.  
  
 Для однопроцессорных компьютеров сборка мусора рабочей станции по умолчанию должна быть самым быстрым вариантом.  Для двухпроцессорных компьютеров можно использовать сборку мусора как рабочей станции, так и сервера.  Сборка мусора сервера должно быть самым быстрым вариантом при наличии более двух процессоров.  
  
 Этот элемент может использоваться только в файле конфигурации приложения; в файле конфигурации компьютера он игнорируется.  
  
> [!NOTE]
>  В платформе .NET Framework версии 4 и более ранних версиях параллельная сборка мусора недоступна, если включена серверная сборка мусора.  Начиная с версии [!INCLUDE[net_v45](../../../../../includes/net-v45-md.md)] сборка мусора сервера является параллельной.  Для использования непараллельной серверной сборки мусора присвойте элементу `<gcServer>` значение `true`, а [элементу \<gcConcurrent\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) — значение `false`.  
  
## Пример  
 В следующем примере включается параллельная сборка мусора сервера.  
  
```  
  
<configuration>  
   <runtime>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
  
```  
  
## См. также  
 <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=fullName>   
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/ru-ru/ba2c6c67-5778-497c-9fac-5f793b5500c7)