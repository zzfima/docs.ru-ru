---
title: "Практическое руководство. Написание простого цикла Parallel.ForEach"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 16d8cd3c3c01c2f9d83786e78f0eb1c45a38a49b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a>Практическое руководство. Написание простого цикла Parallel.ForEach
В этом примере показано, как использовать <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> цикла, чтобы включить параллелизм данных по какой-либо <xref:System.Collections.IEnumerable?displayProperty=nameWithType> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> источника данных.  
  
> [!NOTE]
>  В этой документации для определения делегатов в PLINQ используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Объект <xref:System.Threading.Tasks.Parallel.ForEach%2A> цикла работает как <xref:System.Threading.Tasks.Parallel.For%2A> цикла. Исходная коллекция секционируются и выполнения работы в нескольких потоках, в зависимости от среды системы. Несколько процессоров в системе, тем быстрее параллельного выполнения метода. Для некоторых исходных коллекций последовательный цикл может выполняться быстрее в зависимости от размера источника и типа выполняемых работ. Дополнительные сведения о производительности см. в разделе [потенциальных проблем в данных и задач](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md)  
  
 Дополнительные сведения о параллельных циклах см. в разделе [как: написание простого цикла Parallel.For](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Для использования <xref:System.Threading.Tasks.Parallel.ForEach%2A> с неуниверсальной коллекции, можно использовать <xref:System.Linq.Enumerable.Cast%2A> метода расширения для преобразования коллекции базовой коллекции, как показано в следующем примере:  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Можно также использовать параллельный LINQ (PLINQ) для параллельной обработки <xref:System.Collections.Generic.IEnumerable%601> источники данных. PLINQ позволяет использовать декларативный синтаксис запроса для выражения поведения цикла. Дополнительные сведения см. в разделе [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Скопируйте и вставьте этот код в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010 проект консольного приложения.  
  
-   Добавьте ссылку на System.Drawing.dll  
  
-   Нажмите клавишу F5  
  
## <a name="see-also"></a>См. также  
 [Параллелизм данных](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)  
 [Параллельное программирование](../../../docs/standard/parallel-programming/index.md)  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
