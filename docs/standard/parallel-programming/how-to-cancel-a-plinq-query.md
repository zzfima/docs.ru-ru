---
title: "Практическое руководство. Отмена запроса PLINQ"
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
- PLINQ queries, how to cancel
- cancellation, PLINQ
ms.assetid: 80b14640-edfa-4153-be1b-3e003d3e9c1a
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d8031758462df45c030b8b75a3507f1bfb44bfd0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-cancel-a-plinq-query"></a>Практическое руководство. Отмена запроса PLINQ
В следующих примерах показано два способа отмены запроса PLINQ. В первом примере показано, как отменить запрос, который состоит в основном из обхода данных. Во втором примере показано, как отменить запрос, который содержит пользовательскую функцию, требовательных к вычислительным ресурсам.  
  
> [!NOTE]
>  Если включен «Только мой код», Visual Studio прерывает выполнение программы на строке, в которой создается исключение и выводит сообщение об ошибке «исключение, которое не может быть обработано пользовательским кодом». Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.  
>   
>  Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[PLINQ#16](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#16)]
 [!code-vb[PLINQ#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#16)]  
  
 Платформа PLINQ не помещает одно <xref:System.OperationCanceledException> в <xref:System.AggregateException?displayProperty=nameWithType>; <xref:System.OperationCanceledException> должно обрабатываться в отдельном блоке catch. Если один или несколько пользовательских делегатов вызывает OperationCanceledException(externalCT) (с помощью внешней <xref:System.Threading.CancellationToken?displayProperty=nameWithType>), но не другие исключения, а запрос был определен как `AsParallel().WithCancellation(externalCT)`, а затем PLINQ выдаст один <xref:System.OperationCanceledException> (externalCT), а не <xref:System.AggregateException?displayProperty=nameWithType>. Тем не менее, если один пользовательский делегат вызывает <xref:System.OperationCanceledException>и другой делегат создает другой тип исключения, а затем оба исключения помещаются в <xref:System.AggregateException>.  
  
 Общие рекомендации по отмене выглядит следующим образом:  
  
1.  Если выполнить отмену пользовательский делегат PLINQ должен информирования о внешних <xref:System.Threading.CancellationToken> и исключение <xref:System.OperationCanceledException>(externalCT).  
  
2.  Если произошла отмена и другие исключения не возникают, необходимо обработать <xref:System.OperationCanceledException> вместо <xref:System.AggregateException>.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как обработка отмены, когда имеется функция требовательных к вычислительным ресурсам в пользовательском коде.  
  
 [!code-csharp[PLINQ#17](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#17)]
 [!code-vb[PLINQ#17](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#17)]  
  
 При обработке отмены в пользовательском коде, не нужно использовать <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> в определении запроса. Однако рекомендуется это сделать, так как <xref:System.Linq.ParallelEnumerable.WithCancellation%2A> не влияет на производительность запросов и позволяет отмену может быть обработано операторов запроса и пользовательского кода.  
  
 Чтобы обеспечить отклик системы, рекомендуется проверять отмену приблизительно каждую миллисекунду. Тем не менее любой период до 10 миллисекунд считается допустимым. Эта частота не должен отрицательно повлиять на производительность кода.  
  
 При удалении перечислителя, например когда код прерывается вне цикла foreach (For Each в Visual Basic), выполняющего итерацию результатов запроса, а затем запрос отменяется, но исключение не возникает.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)  
 [Отмена в управляемых потоках](../../../docs/standard/threading/cancellation-in-managed-threads.md)
