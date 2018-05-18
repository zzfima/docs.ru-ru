---
title: Асинхронная модель на основе событий (EAP)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- asynchronous calls
- asynchronous programming, design patterns
- asynchronous programming
ms.assetid: c6baed9f-2a25-4728-9a9a-53b7b14840cf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7811113244d8c5f7d79a55ebb01f04e99e9bd2a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="event-based-asynchronous-pattern-eap"></a>Асинхронная модель на основе событий (EAP)
Существует несколько способов предоставить асинхронные возможности клиентскому коду. Асинхронная модель на основе событий задает для классов рекомендуемый способ работы в асинхронном режиме.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], библиотека параллельных задач предоставляет новую модель для асинхронного и параллельного программирования. Дополнительные сведения см. в разделе [Параллельное программирование](../../../docs/standard/parallel-programming/index.md).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Обзор асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)  
 Описывает, как асинхронная модель на основе событий позволяет использовать преимущества многопоточных приложений и устраняет многие сложности, присущие многопоточности.  
  
 [Реализация асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)  
 Описывает стандартизированный способ упаковки класса, имеющего асинхронные возможности.  
  
 [Рекомендации по реализации асинхронной модели, основанной на событиях](../../../docs/standard/asynchronous-programming-patterns/best-practices-for-implementing-the-event-based-asynchronous-pattern.md)  
 Описывает требования для предоставления асинхронных возможностей в соответствии с асинхронной моделью на основе событий.  
  
 [Определение, когда следует реализовать асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/deciding-when-to-implement-the-event-based-asynchronous-pattern.md)  
 Описывает, в каких случаях следует реализовать асинхронную модель на основе событий вместо шаблона <xref:System.IAsyncResult>.  
  
 [Пошаговое руководство. Реализация компонента, поддерживающего асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md)  
 Демонстрирует, как создать компонент, реализующий асинхронную модель на основе событий. Она реализуется с использованием вспомогательных классов из пространства имен <xref:System.ComponentModel?displayProperty=nameWithType>, что обеспечивает правильную работу компонента при любой модели приложения.  
  
 [Практическое руководство. Использование компонентов, поддерживающих асинхронную модель, основанную на событиях](../../../docs/standard/asynchronous-programming-patterns/how-to-use-components-that-support-the-event-based-asynchronous-pattern.md)  
 Описывает использование компонента, поддерживающего асинхронную модель на основе событий.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ComponentModel.AsyncOperation>  
 Описывает класс <xref:System.ComponentModel.AsyncOperation> и содержит ссылки на все его члены.  
  
 <xref:System.ComponentModel.AsyncOperationManager>  
 Описывает класс <xref:System.ComponentModel.AsyncOperationManager> и содержит ссылки на все его члены.  
  
 <xref:System.ComponentModel.BackgroundWorker>  
 Описывает компонент <xref:System.ComponentModel.BackgroundWorker> и содержит ссылки на все его члены.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Библиотека параллельных задач (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 Описание модели программирования для асинхронных и параллельных операций.  
  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 Описание многопоточных функциональных возможностей платформы .NET Framework.  
  
 [Работа с потоками](https://msdn.microsoft.com/library/552f6c68-dbdb-4327-ae36-32cf9063d88c)  
 Описание возможностей многопоточности языков C# и Visual Basic.  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по работе с потоками](../../../docs/standard/threading/managed-threading-best-practices.md)  
 [События](../../../docs/standard/events/index.md)  
 [Многопоточность в компонентах](https://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [Шаблоны асинхронного программирования](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)
