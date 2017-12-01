---
title: "Практическое руководство. Обработка исключений в запросе PLINQ"
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
helpviewer_keywords: PLINQ queries, how to handle exceptions
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 209e0c1bf89f231d03647ae4351279bfdb172e68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-handle-exceptions-in-a-plinq-query"></a>Практическое руководство. Обработка исключений в запросе PLINQ
Первый пример в этом разделе показано, как обрабатывать <xref:System.AggregateException?displayProperty=nameWithType> , может быть создано из запроса PLINQ при его выполнении. Во втором примере показано, как поместить блоки try-catch в делегаты максимально близко к которой будет создано исключение. Таким образом можно перехватить сразу после их выполнения и, возможно, продолжить выполнение запроса. Если исключения могут всплывать обратно в присоединяемый поток, запрос может продолжить обработку некоторых элементов после создания исключения.  
  
 В некоторых случаях при PLINQ возвращается к последовательному выполнению, и возникает исключение, исключение может быть распространяться напрямую и не заключены в <xref:System.AggregateException>. Кроме того <xref:System.Threading.ThreadAbortException>всегда распространяются напрямую.  
  
> [!NOTE]
>  Если включен «Только мой код», Visual Studio прерывает выполнение программы на строке, в которой создается исключение и выводит сообщение об ошибке «исключение, которое не может быть обработано пользовательским кодом». Эта ошибка не является критической. Вы можете нажать клавишу F5, чтобы продолжить выполнение программы и увидеть поведение системы при обработке этого исключения, которое продемонстрировано в примерах ниже. Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, снимите флажок «Только мой код» в разделе **Сервис, параметры, отладка, Общие**.  
>   
>  Этот пример предназначен для демонстрации использования и может выполняться не быстрее аналогичного последовательного запроса LINQ to Objects. Дополнительные сведения об увеличении скорости см. в разделе [понимание ускорении выполнения в PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## <a name="example"></a>Пример  
 В этом примере показано, как поместить блоки try-catch вокруг кода, который выполняет запрос, чтобы перехватить все <xref:System.AggregateException?displayProperty=nameWithType>, которые вызываются.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 В этом примере запрос не может продолжить после исключения. На момент времени, код приложения перехватывает исключение PLINQ уже остановлена запроса во всех потоках.  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как поместить блок try-catch в делегат, чтобы сделать возможным перехват исключения и продолжение выполнения запроса.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Чтобы скомпилировать и запустить эти примеры, скопируйте их в пример данных PLINQ и вызовите метод из Main.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Не перехватывайте исключение, если вы знаете, как его обработать, чтобы не нарушить состояние программы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.ParallelEnumerable>  
 [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
