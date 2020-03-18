---
title: Практическое руководство. Создание и выполнение простого запроса PLINQ
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PLINQ queries, how to create
ms.assetid: 983b4213-bddd-4a44-9262-cbe59186df4c
ms.openlocfilehash: 349cc8d78e9a080d720e09a7e3e5e314752605c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73106960"
---
# <a name="how-to-create-and-execute-a-simple-plinq-query"></a>Практическое руководство. Создание и выполнение простого запроса PLINQ
В следующем примере показано, как создать простой параллельный запрос LINQ (PLINQ) с помощью метода расширения <xref:System.Linq.ParallelEnumerable.AsParallel%2A> исходной последовательности, а также выполнить запрос с помощью метода <xref:System.Linq.ParallelEnumerable.ForAll%2A>.  
  
> [!NOTE]
> В этой документации для определения делегатов в PLINQ используются лямбда-выражения. Если вы не знакомы с лямбда-выражениями в C# или Visual Basic, см. раздел [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PLINQ#11](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/create1.cs#11)]
 [!code-vb[PLINQ#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/create1.vb#11)]  
  
 В данном примере показан базовый шаблон для создания и выполнения любого параллельного запроса LINQ в случае, когда порядок последовательности результатов не имеет значения; неупорядоченные запросы обычно выполняются быстрее упорядоченных. Запрос делит источник на задачи, выполняемые асинхронно в нескольких потоках. Порядок выполнения каждой из задач зависит не только от объема работы по обработке элементов в разделе, но и от внешних факторов, например, от планирования каждого из потоков операционной системой. Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. Дополнительные сведения см. в статье [Общее представление об ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md). См. дополнительные сведения о [сохранении порядка элементов в запросе PLINQ](../../../docs/standard/parallel-programming/how-to-control-ordering-in-a-plinq-query.md).  
  
## <a name="see-also"></a>См. также раздел

- [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
