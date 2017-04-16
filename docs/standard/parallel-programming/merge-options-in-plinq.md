---
title: "Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, merge options"
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Merge Options in PLINQ
Если запрос выполняется как параллельный, PLINQ разделяет исходную последовательность, чтобы несколько потоков могли работать с различными частями параллельно, обычно в отдельных потоках.  Если результаты необходимо получить в одном потоке, например в цикле `foreach` \(`For Each` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), результаты из каждого потока должны быть объединены в одну последовательность.  Тип слияния, выполняемого PLINQ, зависит от операторов, которые присутствуют в запросе.  Например, операторы, указывающие новую последовательность результатов, должны помещать в буфер все элементы из всех потоков.  Для потока\-потребителя \(который также является потоком пользователя приложения\) полностью буферизованный запрос может выполняться в течение значительного периода времени до момента создания первого результата.  Другие операторы по умолчанию являются частично буферизованными. Они выдают результаты в пакетах.  Один оператор, <xref:System.Linq.ParallelEnumerable.ForAll%2A>, не буферизован по умолчанию.  Он выдает все элементы из всех потоков немедленно.  
  
 С помощью метода <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>, как показано в следующем примере, можно предоставить подсказку PLINQ, указывающую тип выполняемого слияния.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Полный пример см. в разделе [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Если определенный запрос не поддерживает запрошенный параметр, параметр просто будет игнорироваться.  В большинстве случаев нет необходимости указывать параметр слияния для запроса PLINQ.  Однако в некоторых случаях в результате тестирования и измерения можно обнаружить, что запрос выполняется быстрее в режиме, который не задан по умолчанию.  Этот параметр обычно используется для указания оператору слияния блоков выдавать результаты в потоке, чтобы сократить время ответа пользовательского интерфейса.  
  
## ParallelMergeOptions  
 Перечисление <xref:System.Linq.ParallelMergeOptions> включает следующие параметры, указывающие поддерживаемым формам запроса, как выдаются конечные результаты запроса, если они используются в одном потоке.  
  
-   `Not Buffered`  
  
     Параметр <xref:System.Linq.ParallelMergeOptions> приводит к возврату каждого обработанного элемента из каждого потока сразу после его создания.  Такое поведение аналогично потоковой передаче выходных данных.  При наличии в запросе оператора <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> параметр `NotBuffered` сохраняет порядок исходных элементов.  Несмотря на то что параметр `NotBuffered` начинается возвращать результаты, как только они становятся доступными, общее время для получения всех результатов может по\-прежнему быть больше по сравнению с использованием других параметров слияния.  
  
-   `Auto Buffered`  
  
     При использовании параметра <xref:System.Linq.ParallelMergeOptions> запрос собирает элементы в буфер и затем периодически выдает все содержимое буфера сразу в поток\-потребитель.  Это аналогично выдаче исходных данных в блоках вместо использования поведения потоковой передачи `NotBuffered`.  Параметру `AutoBuffered` может потребоваться больше времени, чем параметру `NotBuffered`, чтобы сделать первый элемент доступным в потоке\-потребителе.  Размер буфера и точное поведение выдачи не настраиваются и могут различаться в зависимости от различных факторов, относящихся к запросу.  
  
-   `FullyBuffered`  
  
     При выборе параметра <xref:System.Linq.ParallelMergeOptions> выходные данные всего запроса буферизуются до выдачи какого\-либо элемента.  При использовании этого параметра может потребоваться больше времени для того, чтобы сделать первый элемент доступным в потоке\-потребителе, но полные результаты по\-прежнему могут производиться быстрее по сравнению с использованием других параметров.  
  
## Операторы запроса, поддерживающие параметры слияния  
 В следующей таблице перечислены операторы, поддерживающие все режимы параметров слияния в зависимости от указанных ограничений.  
  
|Оператор|Ограничения|  
|--------------|-----------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Неупорядоченные запросы, содержащие только массив или источник списка.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Неупорядоченные запросы, содержащие только массив или источник списка.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|Нет|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|Нет|  
  
 Все другие операторы запроса PLINQ могут игнорировать параметры слияния, предоставленные пользователем.  Некоторые операторы запроса, например <xref:System.Linq.ParallelEnumerable.Reverse%2A> и <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, не могут выдавать какие\-либо элементы, пока не будут созданы и переупорядочены все элементы.  Таким образом, при использовании <xref:System.Linq.ParallelMergeOptions> в запросе, в котором также содержится оператор, например <xref:System.Linq.ParallelEnumerable.Reverse%2A>, поведение слияния не будет применяться в запросе, пока этот оператор не создаст все результаты.  
  
 Возможность некоторых операторов обрабатывать параметры слияния зависит от типа исходной последовательности и от того, использовался ли оператор <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> ранее в запросе.  Метод <xref:System.Linq.ParallelEnumerable.ForAll%2A> всегда является <xref:System.Linq.ParallelMergeOptions>, он выдает элементы немедленно.  Метод <xref:System.Linq.ParallelEnumerable.OrderBy%2A> всегда является <xref:System.Linq.ParallelMergeOptions>, он должен сортировать весь список перед выдачей.  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)