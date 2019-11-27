---
title: События трассировки событий Windows в среде CLR
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 951941af2568e72fe093860801bd2595b3037e41
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428163"
---
# <a name="clr-etw-events"></a>События трассировки событий Windows в среде CLR
В этом разделе описываются события трассировки событий Windows (ETW). С каждым событием связаны ключевое слово и уровень, которые описываются в разделе [Ключевые слова и уровни среды CLR (трассировка событий Windows)](clr-etw-keywords-and-levels.md). В среде CLR предусмотрены два поставщика событий:  
  
- Поставщик среды выполнения вызывает события в зависимости от того, какие ключевые слова (категории событий) активированы. Поставщик среды выполнения CLR имеет GUID e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.  
  
- Поставщик очистки используется в особых случаях. Поставщик очистки среды CLR имеет GUID a669021c-c450-4609-a035-5af59af4df18.  
  
 Дополнительные сведения см. в разделе [Поставщики трассировки событий Windows в среде CLR](clr-etw-providers.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [События сведений времени выполнения](runtime-information-etw-events.md)  
 Захватывают информацию о среде выполнения, включая SKU, номер версии, способ активизации среды выполнения, параметры командной строки при ее запуске, GUID (если применимо) и другие релевантные данные.  
  
 [Событие ExceptionThrown_V1](exception-thrown-v1-etw-event.md)  
 Захватывает информацию о сгенерированных исключениях.  
  
 [События конфликтов](contention-etw-events.md)  
 Захватывают информацию о конкуренции за блокировки мониторинга или неуправляемые блокировки, используемые исполняющей средой.  
  
 [События пула потоков](thread-pool-etw-events.md)  
 Захватывают информацию о пулах рабочих потоков и пулах потоков ввода-вывода.  
  
 [События загрузчика](loader-etw-events.md)  
 Захватывают информацию о загрузке и выгрузке доменов приложения, сборок и модулей.  
  
 [События методов](method-etw-events.md)  
 Захватывают информацию о методах среды CLR для разрешения символов.  
  
 [События сборки мусора](garbage-collection-etw-events.md)  
 Захватывают сведения, относящиеся к сборке мусора, в целях диагностики и отладки.  
  
 [События трассировки JIT-компилятора](jit-tracing-etw-events.md)  
 Захватывают информацию о JIT-подстановке (inlining) и концевых вызовах (tail calls).  
  
 [События взаимодействия](interop-etw-events.md)  
 Захватывают информацию о генерации и кэшировании заглушек MSIL.  
  
 [События ARM](application-domain-resource-monitoring-arm-etw-events.md)  
 Захватывают детализированную диагностическую информацию о состоянии домена приложения.  
  
 [События безопасности](security-etw-events.md)  
 Захватывают информацию о строгом имени и проверке Authenticode.  
  
 [События стека](stack-etw-event.md)  
 Захватывают информацию, которая используется совместно с другими событиями для генерации трассировок стека после возникновения какого-либо события.  
  
## <a name="see-also"></a>См. также:

- [Улучшение отладки и настройки производительности с помощью ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw)
- [Блог о производительности Windows](https://blogs.msdn.microsoft.com/pigscanfly/tag/xperf/)
- [Контроль ведения журнала .NET Framework](controlling-logging.md)
- [Поставщики трассировки событий Windows в среде CLR](clr-etw-providers.md)
- [Ключевые слова и уровни среды CLR (трассировка событий Windows)](clr-etw-keywords-and-levels.md)
- [События в среде CLR (трассировка событий Windows)](etw-events-in-the-common-language-runtime.md)
