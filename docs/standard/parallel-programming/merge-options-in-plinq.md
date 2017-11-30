---
title: "Параметры слияние в PLINQ"
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
helpviewer_keywords: PLINQ queries, merge options
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e9bf586c1805fc5b5f1cc5f96f4e6b08d80c199a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="merge-options-in-plinq"></a>Параметры слияние в PLINQ
Когда запрос выполняется как параллельный, PLINQ разделяет исходной последовательности, чтобы несколько потоков могли работать с разными частями параллельно, обычно в отдельных потоках. Если результаты будут использоваться в одном потоке, например, в `foreach` (`For Each` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) цикла, а затем результаты из каждого потока необходимо объединить в одну последовательность. Тип слияния, выполняемого PLINQ, зависит от операторов, которые присутствуют в запросе. Например операторы, указывающие новый заказ на результаты должны буфер все элементы из всех потоков. С точки зрения потоке-потребителе (который также является пользователя приложения) полностью буферизованный запрос может выполняться в течение значительного периода времени до момента создания первого результата. Другие операторы по умолчанию являются частично буферизованными. они возвращают результаты в пакетах. Один оператор, <xref:System.Linq.ParallelEnumerable.ForAll%2A> не буферизуется по умолчанию. Он выдает все элементы из всех потоков немедленно.  
  
 С помощью <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A> метода, как показано в следующем примере, можно предоставлять подсказку PLINQ, указывающую тип выполняемого слияния.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Полный пример см. в разделе [как: задание параметров слияния в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Если определенный запрос не поддерживает запрошенный параметр, параметр просто быть обрабатывается. В большинстве случаев не нужно указывать параметр слияния для запроса PLINQ. Однако в некоторых случаях, возможно, тестирования и измерения, что запрос выполняется в режиме не по умолчанию наилучшим образом. Этот параметр обычно используется для принудительного оператор слияния блоков выдавать результаты в потоке, чтобы обеспечить отклика пользовательского интерфейса.  
  
## <a name="parallelmergeoptions"></a>ParallelMergeOptions  
 <xref:System.Linq.ParallelMergeOptions> Перечисление включает следующие параметры, указывающие поддерживаемым формам запроса, как упорядочиваются конечного результата запроса, если они используются в одном потоке:  
  
-   `Not Buffered`  
  
     <xref:System.Linq.ParallelMergeOptions.NotBuffered> Вынуждает каждого обработанного элемента должны быть возвращены из каждого потока сразу же после его создания. Это поведение аналогично «streaming» выходные данные. Если <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> оператор присутствует в запросе, `NotBuffered` сохраняет порядок исходных элементов. Несмотря на то что `NotBuffered` начинает возвращать результаты, как только они становятся доступными, общее время для получения всех результатов может по-прежнему превышать с помощью одного из других параметров слияния.  
  
-   `Auto Buffered`  
  
     При использовании параметра <xref:System.Linq.ParallelMergeOptions.AutoBuffered> запрос собирает элементы в буфер и затем периодически выдает все содержимое буфера сразу потоку-потребителю. Это аналогично выдаче исходных данных в виде «фрагментов» вместо «потоковой передачи» поведение `NotBuffered`. `AutoBuffered`может занять больше времени, чем `NotBuffered` чтобы сделать доступным на первый элемент в потоке-потребителе. Размер буфера и точное поведение выдачи не могут быть изменены и может различаться в зависимости от различных факторов, относящихся к запросу.  
  
-   `FullyBuffered`  
  
     <xref:System.Linq.ParallelMergeOptions.FullyBuffered> Параметр в результате выходные данные всего запроса буферизуются до любого элемента, формируется. При использовании этого параметра может занять больше времени, до первого элемента можно найти в потоке-потребителе, но полные результаты по-прежнему могут производиться быстрее по сравнению с использованием других параметров.  
  
## <a name="query-operators-that-support-merge-options"></a>Операторы запроса, поддерживающие параметры слияния  
 В следующей таблице перечислены операторы, которые поддерживают все режимы параметров слияния в зависимости от указанных ограничений.  
  
|Оператор|Ограничения|  
|--------------|------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Неупорядоченные запросы, имеющие массива или списка источники.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Неупорядоченные запросы, имеющие массива или списка источники.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Нет|  
  
 Все остальные операторы запроса PLINQ может игнорировать параметры слияния, предоставленные пользователем. Некоторые операторы запроса, например, <xref:System.Linq.ParallelEnumerable.Reverse%2A> и <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, нельзя использовать оператор yield какие-либо элементы, пока все созданные и переупорядочены. Таким образом, когда <xref:System.Linq.ParallelMergeOptions> используется в запросе, который также содержится оператор, такой как <xref:System.Linq.ParallelEnumerable.Reverse%2A>, поведение при объединении не применяются в запросе, пока после этот оператор создаст его результаты.  
  
 Возможность некоторых операторов обрабатывать параметры слияния зависит от типа исходной последовательности и является ли <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> использован оператор ранее в запросе. <xref:System.Linq.ParallelEnumerable.ForAll%2A>всегда <xref:System.Linq.ParallelMergeOptions.NotBuffered> ; он возвращает его элементы немедленно. <xref:System.Linq.ParallelEnumerable.OrderBy%2A>всегда <xref:System.Linq.ParallelMergeOptions.FullyBuffered>; прежде чем он возвращает его нужно отсортировать весь список.  
  
## <a name="see-also"></a>См. также  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Практическое руководство. Задание параметров слияния в PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)
