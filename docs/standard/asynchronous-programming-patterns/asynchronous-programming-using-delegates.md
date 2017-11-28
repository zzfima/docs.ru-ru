---
title: "Асинхронное программирование с использованием делегатов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BeginInvoke method
- asynchronous programming, delegates
- asynchronous delegates
- calling synchronous methods in asynchronous manner
- EndInvoke method
- calling asynchronous methods
- delegates [.NET Framework], asynchronous
- synchronous calling in asynchronous manner
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 596d2be26318b782423653b4eb3f43c1f9fc4b92
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="asynchronous-programming-using-delegates"></a>Асинхронное программирование с использованием делегатов
Делегаты позволяют вызывать синхронные методы асинхронно. При синхронном вызове делегата метод `Invoke` вызывает целевой метод непосредственно в текущем потоке. При вызове метода `BeginInvoke` среда CLR помещает запрос в очередь и сразу же передает управление вызывающему объекту. Целевой метод вызывается асинхронно в потоке из пула потоков. Исходный поток, отправивший этот запрос, продолжает выполняться параллельно с целевым методом. Если при вызове метода `BeginInvoke` был указан метод обратного вызова, то метод обратного вызова вызывается после завершения целевого метода. В методе обратного вызова метод `EndInvoke` получает возвращаемое значение и любые параметры ввода/вывода или только выходные параметры. Если при вызове `BeginInvoke` не указан метод обратного вызова, `EndInvoke` можно вызвать из потока, который вызвал `BeginInvoke`.  
  
> [!IMPORTANT]
>  Компиляторы должны формировать классы делегатов с методами `Invoke`, `BeginInvoke`, и `EndInvoke` с использованием сигнатуры делегата, задаваемой пользователем. Методы `BeginInvoke` и `EndInvoke` должны быть объявлены как собственные. Поскольку эти методы помечены как собственные, среда CLR автоматически обеспечивает реализацию во время загрузки класса. Загрузчик проверяет, что эти методы не переопределены.  
  
## <a name="in-this-section"></a>Содержание  
 [Асинхронный вызов синхронных методов](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Обсуждается использование делегатов для асинхронного вызова обычных методов, и приводятся примеры кода, демонстрирующие четыре способа ожидания возврата асинхронного вызова.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Асинхронная модель на основе событий (EAP)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Описывается асинхронное программирование в .NET Framework.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Delegate>
