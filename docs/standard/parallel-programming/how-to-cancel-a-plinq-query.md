---
title: "How to: Cancel a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to cancel"
  - "cancellation, PLINQ"
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# How to: Cancel a PLINQ Query
В следующих примерах показано два способа отмены запроса PLINQ.  В первом примере показано, как отменить запрос, состоящий в основном из обхода данных.  Во втором примере показано, как отменить запрос, который содержит пользовательскую функцию, требующую больших затрат компьютерных ресурсов.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio прервет выполнение программы на строке, в которой создается исключение, и отобразит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической.  Можно нажать F5, чтобы продолжить выполнение с этой ошибки. См. поведение системы при обработке этого исключения в примерах ниже.  Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок "Только мой код" в меню **Сервис, Параметры, Отладка, Общие**.  
>   
>  Этот пример демонстрирует использование и может выполняться медленнее, чем аналогичный последовательный запрос LINQ to Objects.  Дополнительные сведения об увеличении скорости см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Пример  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 Платформа PLINQ не помещает одно исключение <xref:System.OperationCanceledException> в исключение <xref:System.AggregateException?displayProperty=fullName>. Исключение <xref:System.OperationCanceledException> должно обрабатываться в отдельном блоке catch.  Если один или несколько пользовательских делегатов создают исключение OperationCanceledException\(externalCT\) \(с помощью внешнего токена <xref:System.Threading.CancellationToken?displayProperty=fullName>\) и не создают другого исключения, а запрос был определен как `AsParallel().WithCancellation(externalCT)`, PLINQ сгенерирует одно исключение <xref:System.OperationCanceledException> \(externalCT\) вместо <xref:System.AggregateException?displayProperty=fullName>.  Однако если один пользовательский делегат создает исключение <xref:System.OperationCanceledException>, а другой делегат создает другой тип исключения, оба исключения помещаются в <xref:System.AggregateException>.  
  
 Ниже приводятся общие рекомендации по отмене.  
  
1.  Если выполняется отмена с помощью пользовательского делегата, необходимо сообщить PLINQ о внешнем токене <xref:System.Threading.CancellationToken> и создать исключение <xref:System.OperationCanceledException> \(externalCT\).  
  
2.  Если произошла отмена и другие исключения не созданы, необходимо обработать <xref:System.OperationCanceledException> вместо <xref:System.AggregateException>.  
  
## Пример  
 В следующем примере показана обработка отмены при наличии в пользовательском коде функции, требующей больших затрат компьютерных ресурсов.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 При обработке отмены в пользовательском коде нет необходимости использовать метод <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> в определении запроса.  Однако рекомендуется это делать, поскольку метод <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> не оказывает влияния на производительность запросов и позволяет обрабатывать отмену с помощью операторов запроса и пользовательского кода.  
  
 Чтобы обеспечить отклик системы, рекомендуется проверять отмену приблизительно каждую миллисекунду. Однако допускается любой период до 10 миллисекунд.  Эта частота не должна оказывать отрицательное влияние на производительность кода.  
  
 При удалении перечислителя, например когда код прерывается вне цикла foreach \(в Visual Basic — For Each\), выполняющего итерацию результатов запроса, запрос отменяется, но исключение не создается.  
  
## См. также  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [Cancellation in Managed Threads](../../../docs/standard/threading/cancellation-in-managed-threads.md)