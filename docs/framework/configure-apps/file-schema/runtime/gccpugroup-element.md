---
title: "Элемент &lt;GCCpuGroup&gt; | Microsoft Docs"
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
  - "Элемент <GCCpuGroup>"
  - "Элемент GCCpuGroup"
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Элемент &lt;GCCpuGroup&gt;
Определяет, поддерживает ли сборка мусора несколько групп ЦП.  
  
## Синтаксис  
  
```  
<GCCpuGroup    
   enabled="true|false"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`enabled`|Обязательный атрибут.<br /><br /> Определяет, поддерживает ли сборка мусора несколько групп ЦП.|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|`false`|Сборка мусора не поддерживает несколько групп ЦП.  Это значение по умолчанию.|  
|`true`|Сборка мусора поддерживает несколько групп ЦП, если включена серверная сборка мусора.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями платформы .NET Framework.|  
|`runtime`|Элемент, содержащий сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Если компьютер имеет несколько групп ЦП и включена серверная сборка мусора сервера \(см. элемент [\<gcServer\>](../../../../../docs/framework/configure-apps/file-schema/runtime/gcserver-element.md)\), активация этого элемента расширяет сборку мусора на всех группы ЦП и использует все ядра создания и балансировки куч.  
  
> [!NOTE]
>  Этот элемент применяется только к потокам сборки мусора.  Чтобы разрешить среде выполнения распределять потоки пользователя во всех группах ЦП, необходимо также активировать элемент [\<Thread\_UseAllCpuGroups\>](../../../../../docs/framework/configure-apps/file-schema/runtime/thread-useallcpugroups-element.md).  
  
## Пример  
 В следующем примере кода демонстрируется способ включения сборки мусора для нескольких групп ЦП.  
  
```  
<configuration>  
   <runtime>  
      <GCCpuGroup enabled="true"/>  
      <gcServer enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)   
 [How to: Disable Concurrent Garbage Collection](http://msdn.microsoft.com/ru-ru/ba2c6c67-5778-497c-9fac-5f793b5500c7)   
 [Сборка мусора рабочей станции и сборка мусора сервера](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)