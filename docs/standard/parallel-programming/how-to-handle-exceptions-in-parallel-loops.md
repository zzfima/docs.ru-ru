---
title: Практическое руководство. Обработка исключений в параллельных циклах
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parallel loops, how to handle exceptions
ms.assetid: 512f0d5a-4636-4875-b766-88f20044f143
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddf311ad2b79e615f5c3097686035e7bbfbc49c9
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2018
ms.locfileid: "46698098"
---
# <a name="how-to-handle-exceptions-in-parallel-loops"></a>Практическое руководство. Обработка исключений в параллельных циклах
Перегрузки <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> не имеют каких-либо специальных механизмов для обработки возможных исключений. В этом отношении они напоминают обычные циклы `for` и `foreach` (`For` и `For Each` в Visual Basic): необработанное исключение приводит к немедленному завершению цикла.  
  
 При добавлении собственной логики обработки исключений в параллельные циклы обработка случая, в котором подобные исключения могут создаваться в нескольких потоках одновременно, и случая, в котором исключение создается в одном потоке, приводит к созданию еще одного исключения в другом потоке. Оба случая можно обработать путем заключения всех исключений из цикла в <xref:System.AggregateException?displayProperty=nameWithType>. В примере ниже показан один из возможных способов.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio иногда прерывает выполнение программы на строке, в которой создается исключение, и выводит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примере ниже. Чтобы выполнение программы не прерывалось после первой ошибки в Visual Studio, снимите флажок "Только мой код" в меню **Сервис > Параметры > Отладка > Общие**.  
  
## <a name="example"></a>Пример  
 В этом примере все исключения перехватываются и заключаются в созданный объект <xref:System.AggregateException?displayProperty=nameWithType>. Вызывающая сторона может решать, какие исключения обрабатывать.  
  
 [!code-csharp[TPL_Exceptions#08](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#08)]
 [!code-vb[TPL_Exceptions#08](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionsinloops.vb#08)]  
  
## <a name="see-also"></a>См. также

- [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
- [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
