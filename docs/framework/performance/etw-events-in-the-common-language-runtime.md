---
title: События в среде CLR (трассировка событий Windows)
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: 49d1141540fb00ab7ef462da5af84f02e6d9fc4d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937861"
---
# <a name="etw-events-in-the-common-language-runtime"></a>События в среде CLR (трассировка событий Windows)
В общеязыковой среде выполнения (CLR) реализован полезный механизм трассировки событий (ETW), который позволяет получать диагностические сведения для широкого спектра событий отладки и профилирования. События трассировки событий Windows в среде CLR используют систему трассировки Windows ETW, дополняя существующие средства профилирования и отладки, реализованные в общеязыковой среде выполнения.  
  
 Дополнительные сведения о трассировке событий Windows доступны в статье [улучшение отладки и настройки производительности с помощью ETW](https://docs.microsoft.com/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) . Сведения о программе Xperf можно найти в записи [Windows Performance Toolkit — Xperf](https://docs.microsoft.com/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) блога NTDebugging.  
  
 Для всех событий, описанных в разделах о событиях, требуется .NET Framework 4 или более поздней версии. Минимальный поддерживаемый клиент — операционная система Windows Vista; минимальный поддерживаемый сервер — Windows Server 2008.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Контроль ведения журнала .NET Framework](controlling-logging.md)  
 Описывает средства и команды для захвата и просмотра событий трассировки событий Windows.  
  
 [Поставщики трассировки событий Windows в среде CLR](clr-etw-providers.md)  
 Содержит сведения о поставщиках среды выполнения и очистки, а также о том, как использовать их для сбора данных трассировки событий Windows.  
  
 [Ключевые слова и уровни среды CLR (трассировка событий Windows)](clr-etw-keywords-and-levels.md)  
 Описывает ключевые слова для поставщиков среды выполнения и очистки, которые обеспечивают фильтрацию событий по категориям.  
  
 [События трассировки событий Windows в среде CLR](clr-etw-events.md)  
 Содержит подробные сведения о событиях трассировки событий Windows в среде CLR, а также соответствующих ключевых словах, уровнях и данных событий.  
  
## <a name="see-also"></a>См. также:

- [События трассировки событий Windows в .NET Framework](etw-events.md)
