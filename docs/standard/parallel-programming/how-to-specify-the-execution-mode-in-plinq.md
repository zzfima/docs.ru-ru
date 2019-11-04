---
title: Практическое руководство. Задание режима выполнения в PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to use execution mode
ms.assetid: e52ff26c-c5d3-4fab-9fec-c937fb387963
ms.openlocfilehash: c602aba6e18f80b007b15cd61dfd2b48a36dd2c8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139245"
---
# <a name="how-to-specify-the-execution-mode-in-plinq"></a>Практическое руководство. Задание режима выполнения в PLINQ
В этом примере показано, как принудительно отключить эвристический анализ PLINQ по умолчанию, чтобы параллелизовать запрос независимо от его формы.  
  
> [!WARNING]
> Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. См. дополнительные сведения об [ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PLINQ#22](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#22)]
 [!code-vb[PLINQ#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#22)]  
  
 PLINQ разработан для того, чтобы применить преимущества параллелизации. Но не все запросы станут быстрее при параллельном выполнении. Например, если запрос содержит только один пользовательский делегат с небольшим числом задач, последовательно запрос выполняется быстрее. Это связано с тем, что накладные расходы на управление параллельным выполнением превышают полученную выгоду от ускорения работы. По этой причине PLINQ не применяет параллелизацию к каждому запросу автоматически. Сначала он проверяет форму запроса и входящие в него операторы. Исходя из этих результатов анализа, PLINQ в стандартном режиме выполнения самостоятельно решает, нужно ли выполнять параллельно весь запрос или некоторые его элементы. Но в некоторых случаях у вас есть больше сведений о запросе, чем доступно PLINQ на основе такого анализа. Например, вы знаете, что делегат весьма затратный и в любом случае выиграет от применения параллелизации. В таких случаях вы можете применить метод <xref:System.Linq.ParallelEnumerable.WithExecutionMode%2A> со значением <xref:System.Linq.ParallelExecutionMode.ForceParallelism>, чтобы PLINQ всегда выполнял этот запрос параллельно.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте и вставьте этот код в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md), затем вызовите этот метод из `Main`.  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.ParallelEnumerable.AsSequential%2A>
- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
