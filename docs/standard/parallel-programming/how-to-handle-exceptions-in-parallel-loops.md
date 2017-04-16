---
title: "How to: Handle Exceptions in Parallel Loops | Microsoft Docs"
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
  - "parallel loops, how to handle exceptions"
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# How to: Handle Exceptions in Parallel Loops
Перегрузки <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> не имеют каких\-либо специальных механизмов для обработки возможных исключений.  В этом отношении они напоминают обычные циклы `for` и `foreach` \(`For` и `For Each` в Visual Basic\): необработанное исключение приводит к немедленному завершению цикла.  
  
 При добавлении собственной логики обработки исключений в параллельные циклы обработка случая, в котором подобные исключения могут создаваться в нескольких потоках одновременно, и случая, в котором исключение создается в одном потоке, приводит к созданию еще одного исключения в другом потоке.  Оба случая можно обработать путем заключения всех исключений из цикла в <xref:System.AggregateException?displayProperty=fullName>.  В примере ниже показан один из возможных способов.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической.  Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примере ниже.  Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис, Параметры, Отладка, Общие**.  
  
## Пример  
 В этом примере все исключения перехватываются и заключаются в созданный объект <xref:System.AggregateException?displayProperty=fullName>.  Вызывающая сторона может решать, какие исключения обрабатывать.  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## См. также  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)