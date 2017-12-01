---
title: "Практическое руководство. Управление порядком в запросе PLINQ"
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
helpviewer_keywords: PLINQ queries, how to control ordering
ms.assetid: c67eccc7-004d-4b2f-987e-919cbbd62ef7
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b9e29aa825a68154e32a34a23ca170258092b88a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-ordering-in-a-plinq-query"></a>Практическое руководство. Управление порядком в запросе PLINQ
Эти примеры показывают, как управление порядком в запросе PLINQ с помощью <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> метода расширения.  
  
> [!WARNING]
>  Эти примеры в основном предназначен для демонстрации использования и может выполняться быстрее, чем эквивалентный последовательный LINQ to Objects, запросы.  
  
## <a name="example"></a>Пример  
 Следующий пример сохраняет порядок исходной последовательности. Иногда это необходимо; Например, некоторые операторы запросов требуется упорядоченный исходной последовательности для получения правильных результатов.  
  
 [!code-csharp[PLINQ#12](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#12)]
 [!code-vb[PLINQ#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#12)]  
  
## <a name="example"></a>Пример  
 В следующем примере некоторые операторы, исходная последовательность, возможно, ожидалось упорядоченный запроса. Эти операторы будут работать с неупорядоченными последовательностями, но они могут привести к непредвиденным результатам.  
  
 [!code-csharp[PLINQ#14](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#14)]
 [!code-vb[PLINQ#14](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#14)]  
  
 Чтобы запустить этот метод, вставьте его в класс PLINQDataSample в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) проекта и нажмите клавишу F5.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как сохранить порядок первой части запроса, а затем удалить его для повышения производительности предложения join и повторно применить упорядочение окончательный результат последовательности.  
  
 [!code-csharp[PLINQ#15](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#15)]
 [!code-vb[PLINQ#15](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#15)]  
  
 Чтобы запустить этот метод, вставьте его в класс PLINQDataSample в [пример данных PLINQ](../../../docs/standard/parallel-programming/plinq-data-sample.md) проекта и нажмите клавишу F5.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
