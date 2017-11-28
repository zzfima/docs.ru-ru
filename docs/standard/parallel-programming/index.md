---
title: "Параллельное программирование в .NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: parallel programming
ms.assetid: 4d83c690-ad2d-489e-a2e0-b85b898a672d
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e061508b6b74e81b79ab7d53b0277afd38072635
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="parallel-programming-in-net"></a>Параллельное программирование в .NET
Многие персональные компьютеры и рабочие станции имеют ЦП, содержащие два или четыре ядра, которые позволяют одновременно выполнять несколько потоков. В ближайшем будущем ожидается, что компьютеры будут иметь значительно больше ядер. Чтобы воспользоваться преимуществами существующего и будущего оборудования, можно распараллеливать код для распределения работы между несколькими процессорами. В прошлом распараллеливание требовало управления потоками и взаимоблокировками на низком уровне. [!INCLUDE[vs_dev10_long](../../../includes/vs-dev10-long-md.md)] и [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] улучают поддержку параллельного программирования, предоставляя новую среду выполнения, новые типы библиотек классов и новые средства диагностики. Эти функциональные возможности упрощают параллельную разработку, что позволяет разработчикам писать эффективный, детализированный и масштабируемый параллельный код с помощью естественных выразительных средств без необходимости непосредственной работы с потоками или пулом потоков. На рисунке ниже представлен общий обзор архитектуры параллельного программирования в [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)].  
  
 ![Архитектура параллельного программирования в .NET](../../../docs/standard/parallel-programming/media/tpl-architecture.png "TPL_Architecture")  
  
## <a name="related-topics"></a>Связанные разделы  
  
|Технология|Описание|  
|----------------|-----------------|  
|[Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)|Предоставляет документацию для класса <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType>, который содержит параллельные версии цикла `For`, цикла `ForEach`; а также для класса <xref:System.Threading.Tasks.Task?displayProperty=nameWithType>, который предоставляет предпочитаемый способ для выражения асинхронных операций.|  
|[Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)|Параллельная реализация LINQ to Objects, которая значительно улучшает производительность во множестве сценариев.|  
|[Структуры данных для параллельного программирования](../../../docs/standard/parallel-programming/data-structures-for-parallel-programming.md)|Предоставляет ссылки на документацию для потокобезопасные классы коллекций, упрощенные типы синхронизации, типы для "ленивой" инициализации.|  
|[Средства диагностики параллельного выполнения](../../../docs/standard/parallel-programming/parallel-diagnostic-tools.md)|Ссылки на документацию в окнах отладчика среды Visual Studio для задач, параллельных стеков и [визуализатор параллелизма[!INCLUDE[vsprvsts](../../../includes/vsprvsts-md.md)], который состоит из набора представлений в профилировщике ](/visualstudio/profiling/concurrency-visualizer), используемого для отладки параллельного кода и настройки его производительности.|  
|[Пользовательские разделители для PLINQ и TPL](../../../docs/standard/parallel-programming/custom-partitioners-for-plinq-and-tpl.md)|Описывает работу модулей разделения, порядок настройки модулей разделения по умолчанию, порядок создания нового модуля разделения.|  
|[Планировщики задач](http://msdn.microsoft.com/library/638f8ea5-21db-47a2-a934-86e1e961bf65)|Описывает порядок работы модуля планирования и порядок их настройки.|  
|[Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)|Предоставляет краткие общие сведения по лямбда выражениям в C# и Visual Basic, показывает, как они используются в PLINQ и в библиотеке параллельных задач.|  
|[Дополнительные сведения](../../../docs/standard/parallel-programming/for-further-reading-parallel-programming.md)|Предоставляет ссылки на дополнительные ресурсы примеров и документации для параллельного программирования на платформе .NET Framework.|  
  
## <a name="see-also"></a>См. также  
 [Шаблоны для параллельного программирования: описание и применение в .NET Framework 4](http://go.microsoft.com/fwlink/?LinkID=185142)  
 [Примеры параллельного программирования в .NET Framework](http://code.msdn.microsoft.com/Samples-for-Parallel-b4b76364)
