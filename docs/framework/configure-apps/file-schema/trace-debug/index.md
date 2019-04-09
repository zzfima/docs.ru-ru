---
title: Схема параметров трассировки и отладки
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: 79054ba450dcab1a18562aaadd71b9171896c1e9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177441"
---
# <a name="trace-and-debug-settings-schema"></a>Схема параметров трассировки и отладки
Параметры трассировки и отладки определяют прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.  
  
 В приведенной ниже таблице описывается назначение каждого элемента параметров трассировки и отладки.  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|Добавляет прослушиватель в коллекцию `Listeners`.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-sharedlisteners.md)|Добавляет прослушиватель в коллекцию `sharedListeners`.|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|Задает уровень, на котором установлен ключ трассировки.|  
|[\<assert>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/assert-element.md)|Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.|  
|[\<Очистить >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|Очищает коллекцию `Listeners` для источника трассировки.|  
|[\<Очистить >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|Очищает коллекцию `Listeners` для трассировки.|  
|[\<Фильтр >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.|  
|[\<Фильтр >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-trace.md)|Добавляет фильтр к прослушивателю в коллекции `Listeners` для трассировки.|  
|[\<Фильтр >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-sharedlisteners.md)|Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.|  
|[\<прослушиватели >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|Определяет прослушиватели в коллекции `Listeners` для источника трассировки.|  
|[\<прослушиватели >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|Определяет прослушиватели в коллекции `Listeners` для трассировки.|  
|[\<performanceCounters >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/performancecounters-element.md)|Задает размер глобальной памяти, совместно используемой счетчиками производительности.|  
|[\<Удалить >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|Удаляет прослушиватель из коллекции `Listeners` для трассировки.|  
|[\<Удалить >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.|  
|[\<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md)|Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.|  
|[\<источники >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sources-element.md)|Содержит источники трассировки, которые инициируют сообщения трассировки.|  
|[\<Источник >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|Содержит источник трассировки, который инициирует сообщения трассировки.|  
|[\<Параметры >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/switches-element.md)|Содержит ключи трассировки и уровень, на котором они установлены.|  
|[\<system.diagnostics>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/system-diagnostics-element.md)|Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.|  
|[\<трассировки >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/trace-element.md)|Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.|  
  
## <a name="see-also"></a>См. также

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [Схема файла конфигурации](../../../../../docs/framework/configure-apps/file-schema/index.md)
