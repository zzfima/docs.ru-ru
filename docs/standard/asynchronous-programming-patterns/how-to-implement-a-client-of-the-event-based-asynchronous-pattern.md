---
title: "How to: Implement a Client of the Event-based Asynchronous Pattern | Microsoft Docs"
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
  - "Event-based Asynchronous Pattern"
  - "ProgressChangedEventArgs class"
  - "BackgroundWorker component"
  - "events [.NET Framework], asynchronous"
  - "Asynchronous Pattern"
  - "AsyncOperationManager class"
  - "threading [.NET Framework], asynchronous features"
  - "components [.NET Framework], asynchronous"
  - "AsyncOperation class"
  - "threading [Windows Forms], asynchronous features"
  - "AsyncCompletedEventArgs class"
ms.assetid: 21a858c1-3c99-4904-86ee-0d17b49804fa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Implement a Client of the Event-based Asynchronous Pattern
В следующем примере кода показано, как использовать компонент, который соответствует [Event\-based Asynchronous Pattern Overview](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).  В форме этого примера используется компонент  `PrimeNumberCalculator` , описанный в разделе [How to: Implement a Component That Supports the Event\-based Asynchronous Pattern](../../../docs/standard/asynchronous-programming-patterns/component-that-supports-the-event-based-asynchronous-pattern.md).  
  
 При выполнении проекта, в котором используется этот пример, будет отображаться форма калькулятора простых чисел с сеткой и двумя кнопками **Start New Task** и **Cancel**.  Можно нажать кнопку **Start New Task** несколько раз последовательно. При каждом нажатии асинхронная операция начнет вычисление для определения, является ли созданное случайным образом число простым.  В форме будет периодически отображаться ход выполнения и добавочные результаты.  Каждой операции присвоен уникальный идентификатор задачи.  Результат вычисления отображается в столбце **Result**; если проверяемое число не является простым, оно помечается как **Composite** и отображается первый делитель.  
  
 Любая операция ожидания может быть отменена с помощью кнопки **Cancel**.  Можно выбрать несколько объектов.  
  
> [!NOTE]
>  Большинство чисел не будут простыми.  Если после нескольких завершенных операций простые числа не будут найдены, просто запустите дополнительные задачи и, в конце концов, простые числа будут обнаружены.  
  
## Пример  
 [!code-csharp[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/CS/primenumbercalculatormain.cs#10)]
 [!code-vb[System.ComponentModel.AsyncOperationManager#10](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AsyncOperationManager/VB/primenumbercalculatormain.vb#10)]  
  
## См. также  
 <xref:System.ComponentModel.AsyncOperation>   
 <xref:System.ComponentModel.AsyncOperationManager>   
 <xref:System.Windows.Forms.WindowsFormsSynchronizationContext>