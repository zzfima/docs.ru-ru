---
title: '&lt;performanceCounters&gt; элемент'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <perfomanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 69d6deafb6aad88f5d379c7e8d4ac707e4c51815
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47209825"
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
|FileMappingSize|Обязательный атрибут.<br /><br /> Указывает размер в байтах, глобальной памяти, совместно используемой счетчиками производительности. Значение по умолчанию — 524288.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|`Configuration`|Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.|  
|`system.diagnostics`|Задает корневой элемент для раздела конфигурации ASP.NET.|  
  
## <a name="remarks"></a>Примечания  
 Счетчики производительности используйте отображенного в памяти файла или общей памяти, публикацию данных производительности.  Размер общей памяти определяет, сколько экземпляров можно использовать одновременно.  Существует два типа общей памяти: глобальную общую память и объем отдельной общей памяти.  Глобальной общей памяти используется всех категорий счетчиков производительности, устанавливается вместе с .NET Framework версии 1.0 или 1.1.  Категории счетчиков производительности, вместе с .NET Framework версии 2.0 используйте отдельной общей памяти, у каждого счетчика производительности есть свою собственную память.  
  
 Размер глобальную общую память можно задать только с помощью файла конфигурации.  Значение по умолчанию-524 288 байтов, максимальный размер составляет 33 554 432 байтов и минимальный размер — 32 768 байт.  Поскольку глобальной общей памяти совместно используется всеми процессами и категориями, создатель первый размер.  Если размер определяется в файле конфигурации приложения, что размер используется только если приложение является первому приложению, которое вызывает счетчики производительности для выполнения.  Поэтому правильное расположение, чтобы указать `filemappingsize` значением является файл Machine.config.  Отдельные счетчики производительности, поэтому в конечном итоге глобальную общую память исчерпана, если большое количество экземпляров счетчиков производительности с разными именами, создаются не освобождать память в глобальную общую память.  
  
 Размер отдельной общей памяти, значение DWORD FileMappingSize в реестре раздела HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<имя категории >* \Performance указывается ссылка на Во-первых следует значение, указанное для глобальной общей памяти в файле конфигурации. Если значение FileMappingSize не существует, то размер отдельной общей памяти задается равным одной четвертой (1/4) глобальные настройки в файле конфигурации.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Diagnostics.PerformanceCounter>  
 <xref:System.Diagnostics.PerformanceCounterCategory>  
 <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>  
 <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
