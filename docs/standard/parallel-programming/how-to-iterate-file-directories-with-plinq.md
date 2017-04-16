---
title: "How to: Iterate File Directories with PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to iterate directories"
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Iterate File Directories with PLINQ
В этом примере показано два простых способа параллельного выполнения операций в каталогах с файлами.  Первый запрос использует метод <xref:System.IO.Directory.GetFiles%2A> для заполнения массива имен файлов в каталоге и всех подкаталогах.  Этот метод не возвращает результат, пока весь массив не будет заполнен, поэтому он может вызывать задержку в начале операции.  Однако после заполнения массива PLINQ может очень быстро выполнять параллельную обработку.  
  
 Второй запрос использует статические методы <xref:System.IO.Directory.EnumerateDirectories%2A> и <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>, которые сразу же начинают возвращать результаты.  Благодаря такому подходу скорость обработки может быть выше при переборе по большим деревьям каталогов, хотя время обработки в сравнении с первым примером может зависеть от многих факторов.  
  
> [!WARNING]
>  Эти примеры демонстрируют использование и могут выполняться медленнее, чем аналогичный последовательный запрос LINQ to Objects.  Дополнительные сведения об увеличении скорости см. в разделе [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Пример  
 В следующем примере показан метод перебора в каталогах с файлами в простых сценариях, когда есть доступ ко всем каталогам в дереве, файлы не очень большого размера и время доступа не имеет значения.  Этот подход подразумевает задержку в начале операции, пока создается массив имен файлов.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## Пример  
 В следующем примере показан метод перебора в каталогах с файлами в простых сценариях, когда есть доступ ко всем каталогам в дереве, файлы не очень большого размера и время доступа не имеет значения.  При таком подходе результаты появляются быстрее, чем в предыдущем примере.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 При использовании метода <xref:System.IO.Directory.GetFiles%2A> следует убедиться, что имеются соответствующие разрешения для всех каталогов в дереве.  В противном случае возникнет исключение и результаты возвращены не будут.  При использовании метода <xref:System.IO.Directory.EnumerateDirectories%2A> в запросе PLINQ довольно трудно обрабатывать исключения ввода\-вывода удобным способом, при котором можно продолжать перебор.  Если код должен обрабатывать исключения ввода\-вывода или несанкционированного доступа, необходимо обратить внимание на подход, рассмотренный в разделе [Практическое руководство. Перебор каталогов с файлами с помощью параллельного класса](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md).  
  
 Если задержка ввода\-вывода недопустима \(например, при передаче сигналов ввода\-вывода по сети\), рассмотрите возможность использования методики асинхронного ввода\-вывода, описанной в разделе [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) и в этой [статье](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## См. также  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)