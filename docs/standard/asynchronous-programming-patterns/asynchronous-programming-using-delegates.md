---
title: "Asynchronous Programming Using Delegates | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "BeginInvoke method"
  - "asynchronous programming, delegates"
  - "asynchronous delegates"
  - "calling synchronous methods in asynchronous manner"
  - "EndInvoke method"
  - "calling asynchronous methods"
  - "delegates [.NET Framework], asynchronous"
  - "synchronous calling in asynchronous manner"
ms.assetid: 38a345ca-6963-4436-9608-5c9defef9c64
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Asynchronous Programming Using Delegates
Делегаты позволяют вызывать синхронные методы асинхронно.  При синхронном вызове делегата метод `Invoke` вызывает метод назначения непосредственно в текущий поток.  При вызове метода `BeginInvoke` среда CLR помещает запрос в очередь и сразу же возвращает управление вызывающему объекту.  Метод назначения асинхронно вызывается в поток из пула потоков.  Исходный поток, отправивший этот запрос, теперь может беспрепятственно продолжать работу параллельно с методом назначения.  Если при вызове метода `BeginInvoke` был задан метод обратного вызова, он будет вызван при завершении выполнения метода назначения.  В методе обратного вызова метод `EndInvoke` получает возвращаемое значение и любые входные и выходные параметры или только выходные параметры.  Если метод обратного вызова не указан при вызове `BeginInvoke`, `EndInvoke` может быть вызван из потока, который вызвал `BeginInvoke`.  
  
> [!IMPORTANT]
>  Компиляторы должны выпускать классы делегатов с помощью методов `Invoke`, `BeginInvoke` и `EndInvoke` с использованием сигнатуры делегата, задаваемой пользователем.  Методы `BeginInvoke` и `EndInvoke` должны иметь вид собственных методов.  Поскольку эти методы помечены как собственные, среда CLR автоматически обеспечивает реализацию во время загрузки класса.  Загрузчик обеспечивает невозможность их переопределения.  
  
## В этом подразделе  
 [Calling Synchronous Methods Asynchronously](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 Использование делегатов для асинхронного вызова обычных методов, а также примеры кода, в которых демонстрируются четыре способа ожидания возврата асинхронного вызова.  
  
 [Пример асинхронного программирования делегатов](../Topic/Asynchronous%20Delegates%20Programming%20Sample.md)  
 На более сложном примере кода демонстрируется использование делегатов для осуществления асинхронных вызовов при выполнении факторизации чисел.  
  
## Связанные подразделы  
 [Event\-based Asynchronous Pattern \(EAP\)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 Описано асинхронное программирование в .NET Framework.  
  
## См. также  
 <xref:System.Delegate>