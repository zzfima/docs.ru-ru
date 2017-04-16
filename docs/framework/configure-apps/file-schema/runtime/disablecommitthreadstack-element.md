---
title: "Элемент &lt;disableCommitThreadStack&gt; | Microsoft Docs"
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
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "элемент <disableCommitThreadStack>"
  - "disableCommitThreadStack - элемент"
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Элемент &lt;disableCommitThreadStack&gt;
Указывает, фиксируется ли весь стек потоков при запуске потока.  
  
 \<configuration\>  
\<runtime\>  
\<disableCommitThreadStack\>  
  
## Синтаксис  
  
```  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|enabled|Обязательный атрибут.<br /><br /> Указывает, отключена ли фиксация всего стека потоков при запуске потока \(режим по умолчанию\).|  
  
## Атрибут enabled  
  
|Значение|Описание|  
|--------------|--------------|  
|0|Не отключать для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.|  
|1|Отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|`configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)].|  
|`runtime`|Содержит сведения о привязке сборок и сборке мусора.|  
  
## Заметки  
 Режим по умолчанию для среды CLR заключается в фиксации всего стека потоков при запуске потока. Если на сервере с ограниченным объемом памяти необходимо создать большое число потоков и большинство из этих потоков будут использовать очень небольшое пространство стека, сервер может работать лучше, если среда не фиксирует весь стек потоков сразу после запуска потока.  
  
> [!NOTE]
>  Неуправляемые узлы могут использовать флаг запуска `STARTUP_DISABLE_COMMITTHREADSTACK` в перечислении [STARTUP\_FLAGS](../../../../../ocs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) для достижения такого же результата.  
  
## Пример  
 В следующем примере показано, как отключить для среды CLR режим по умолчанию, который заключается в фиксации всего стека потоков при запуске потока.  
  
```  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## См. также  
 [Схема параметров среды выполнения](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)