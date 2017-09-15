---
title: "События в среде CLR (трассировка событий Windows)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
caps.latest.revision: 7
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6a6b97bf8ce9075ee5fc8877fed65bd4a23f1ce5
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="etw-events-in-the-common-language-runtime"></a>События в среде CLR (трассировка событий Windows)
В общеязыковой среде выполнения (CLR) реализован полезный механизм трассировки событий (ETW), который позволяет получать диагностические сведения для широкого спектра событий отладки и профилирования. События трассировки событий Windows в среде CLR используют систему трассировки Windows ETW, дополняя существующие средства профилирования и отладки, реализованные в общеязыковой среде выполнения.  
  
 Дополнительные сведения о трассировке событий Windows см. в статье [Улучшение отладки и настройки производительности с помощью ETW](http://go.microsoft.com/fwlink/?LinkID=161142) библиотеки MSDN. Сведения о программе Xperf можно найти в записи [Windows Performance Toolkit — Xperf](http://go.microsoft.com/fwlink/?LinkID=161144) блога NTDebugging.  
  
 Дополнительные инструменты трассировки событий Windows в среде CLR будут представлены на [веб-сайте CodePlex](http://go.microsoft.com/fwlink/?LinkID=111138), как только станут доступны.  
  
 Для всех событий, описанных в разделах, посвященных событиям, требуется [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] или более поздней версии. Минимальный поддерживаемый клиент — операционная система Windows Vista; минимальный поддерживаемый сервер — Windows Server 2008.  
  
## <a name="in-this-section"></a>Содержание  
 [Контроль ведения журнала .NET Framework](../../../docs/framework/performance/controlling-logging.md)  
 Описывает средства и команды для захвата и просмотра событий трассировки событий Windows.  
  
 [Поставщики трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-providers.md)  
 Содержит сведения о поставщиках среды выполнения и очистки, а также о том, как использовать их для сбора данных трассировки событий Windows.  
  
 [Ключевые слова и уровни среды CLR (трассировка событий Windows)](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)  
 Описывает ключевые слова для поставщиков среды выполнения и очистки, которые обеспечивают фильтрацию событий по категориям.  
  
 [События трассировки событий Windows в среде CLR](../../../docs/framework/performance/clr-etw-events.md)  
 Содержит подробные сведения о событиях трассировки событий Windows в среде CLR, а также соответствующих ключевых словах, уровнях и данных событий.  
  
## <a name="see-also"></a>См. также  
 [События трассировки событий Windows в .NET Framework](../../../docs/framework/performance/etw-events.md)

