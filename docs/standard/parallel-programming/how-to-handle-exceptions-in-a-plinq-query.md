---
title: "How to: Handle Exceptions in a PLINQ Query | Microsoft Docs"
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
  - "PLINQ queries, how to handle exceptions"
ms.assetid: 8d56ff9b-a571-4d31-b41f-80c0b51b70a5
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Handle Exceptions in a PLINQ Query
В первом примере этого раздела показано, как обработать исключение <xref:System.AggregateException?displayProperty=fullName>, которое может быть создано из запроса PLINQ при его выполнении.  Во втором примере показано, как поместить блоки try\-catch в делегаты максимально близко к месту создания исключения.  Таким образом их можно перехватить, как только они появятся, и, возможно, продолжить выполнение запроса.  Если позволить исключениям маршрутизироваться по восходящей обратно в присоединяемый поток, запрос может продолжить обработку некоторых элементов после создания исключения.  
  
 В некоторых случаях, если PLINQ возвращается к последовательному выполнению и происходит исключение, оно может распространяться напрямую, а не заключенное в оболочку <xref:System.AggregateException>.  Кроме того, исключения <xref:System.Threading.ThreadAbortException> всегда распространяются напрямую.  
  
> [!NOTE]
>  Если включен режим "Только мой код", Visual Studio прервет выполнение программы на строке, в которой создается исключение, и отобразит сообщение об ошибке "Исключение, которое не может быть обработано пользовательским кодом". Эта ошибка не является критической.  Можно нажать F5, чтобы продолжить выполнение с этой ошибки. См. поведение системы при обработке этого исключения в примерах ниже.  Чтобы предотвратить прерывание выполнения после первой ошибки в Visual Studio, необходимо снять флажок "Только мой код" в меню **Сервис, Параметры, Отладка, Общие**.  
>   
>  Этот пример демонстрирует использование и может выполняться медленнее, чем аналогичный последовательный запрос LINQ to Objects.  Дополнительные сведения об увеличении скорости см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Пример  
 В этом примере показано, как поместить блоки try\-catch рядом с кодом, который выполняет запрос для перехвата любых созданных исключений <xref:System.AggregateException?displayProperty=fullName>.  
  
 [!code-csharp[PLINQ#41](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#41)]
 [!code-vb[PLINQ#41](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#41)]  
  
 В этом примере запрос не может быть продолжен после создания исключения.  К моменту перехвата кодом приложения исключения PLINQ уже останавливает выполнение запроса во всех потоках.  
  
## Пример  
 В следующем примере показано, как поместить блок try\-catch в делегат, чтобы сделать возможным перехват исключения и продолжение выполнения запроса.  
  
 [!code-csharp[PLINQ#42](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#42)]
 [!code-vb[PLINQ#42](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinqsnippets1.vb#42)]  
  
## Компиляция кода  
  
-   Чтобы скомпилировать и запустить эти примеры, скопируйте их в пример данных PLINQ и вызовите метод из Main.  
  
## Отказоустойчивость  
 Не перехватывайте исключение, если неизвестно, как его обрабатывать, чтобы не нарушить состояние программы.  
  
## См. также  
 <xref:System.Linq.ParallelEnumerable>   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)