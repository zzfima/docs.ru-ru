---
title: "&lt;performanceCounters&gt; элемент"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 64afd62c6eeca7bce14e331fdc65fccfa3d02bce
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltperformancecountersgt-element"></a>&lt;performanceCounters&gt; элемент
Задает размер глобальной памяти, совместно используемой счетчиками производительности.  
  
 \<configuration>  
\<System.Diagnostics >  
\<performanceCounters >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<performanceCounters filemappingsize="524288" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|FileMappingSize|Обязательный атрибут.<br /><br /> Размер в байтах глобальной памяти, совместно используемой счетчиками производительности. Значение по умолчанию — 524288.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Примечания  
 Счетчики производительности для публикации данных о производительности используйте отображенных в памяти файла или общей памяти.  Объем общей памяти определяет, сколько экземпляров могут быть использованы одновременно.  Существует два типа общей памяти: глобальную общую память и отдельную общую память.  Глобальную общую память используется всеми категориями счетчиков производительности, устанавливается вместе с .NET Framework версии 1.0 или 1.1.  Категории счетчиков производительности, вместе с .NET Framework версии 2.0 используют отдельную общую память, у каждого счетчика производительности есть свою собственную память.  
  
 Размер глобальную общую память можно задать только с помощью файла конфигурации.  Значение по умолчанию-524 288 байтов, максимальный размер — 33 554 432 байта, а минимальный размер — 32 768 байт.  Поскольку глобальную общую память совместно используется всеми процессами и категориями, создатель первый размер.  При указании размера в файле конфигурации приложения, чтобы размер используется только если приложение является первым приложением, выполнившим запуск счетчиков производительности.  Поэтому правильное расположение, чтобы указать `filemappingsize` значение — в файле Machine.config.  Не удается освободить память в глобальную общую память отдельные счетчики производительности, поэтому в конечном итоге глобальную общую память будет исчерпан, если создается большое число экземпляров счетчика производительности с разными именами.  
  
 Для размера отдельной общей памяти, значение DWORD FileMappingSize в реестре раздела HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<имя категории >*\Performance имеется ссылка Во-первых следуют значение, указанное для глобальную общую память в файле конфигурации. Если значение FileMappingSize не существует, то размер отдельной общей памяти устанавливается равным одной четвертой (1/4) глобальный параметр в файле конфигурации.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
