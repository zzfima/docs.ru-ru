---
title: "How to: Write a Simple Parallel.ForEach Loop | Microsoft Docs"
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
  - "foreach, parallel version"
  - "parallel programming, foreach"
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# How to: Write a Simple Parallel.ForEach Loop
В этом примере показано, как использовать цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName>, чтобы включить параллелизм данных для любого источника данных <xref:System.Collections.IEnumerable?displayProperty=fullName> или <xref:System.Collections.Generic.IEnumerable%601?displayProperty=fullName>.  
  
> [!NOTE]
>  В этой документации для определения делегатов в PLINQ используются лямбда\-выражения.  Сведения о лямбда\-выражениях в C\# или Visual Basic см. в разделе [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
## Пример  
 [!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
 [!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]  
  
 Цикл <xref:System.Threading.Tasks.Parallel.ForEach%2A> работает как цикл <xref:System.Threading.Tasks.Parallel.For%2A>.  Исходная коллекция разделяется, и работа планируется для нескольких потоков в зависимости от системной среды.  Чем больше процессоров в системе, тем быстрее выполняется параллельный метод.  В случае некоторых исходных коллекций последовательный цикл может выполняться быстрее в зависимости от размера источника и типа выполняемых работ.  Дополнительные сведения о производительности см. в разделе [Potential Pitfalls in Data and Task Parallelism](../../../docs/standard/parallel-programming/potential-pitfalls-in-data-and-task-parallelism.md).  
  
 Дополнительные сведения о параллельных циклах см. в разделе [How to: Write a Simple Parallel.For Loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).  
  
 Чтобы использовать <xref:System.Threading.Tasks.Parallel.ForEach%2A> с неуниверсальной коллекцией, можно воспользоваться методом расширения <xref:System.Linq.Enumerable.Cast%2A> для преобразования коллекции в универсальную, как показано в следующем примере.  
  
 [!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
 [!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]  
  
 Также можно использовать параллельный LINQ \(PLINQ\) для параллельной обработки источников данных <xref:System.Collections.Generic.IEnumerable%601>.  PLINQ позволяет использовать декларативный синтаксис запроса для выражения поведения цикла.  Для получения дополнительной информации см. [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## Компиляция кода  
  
-   Скопируйте и вставьте этот код в проект консольного приложения [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 2010.  
  
-   Добавьте ссылку на System.Drawing.dll.  
  
-   Нажмите F5.  
  
## См. также  
 [Data Parallelism](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)   
 [Parallel Programming](../../../docs/standard/parallel-programming/index.md)   
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)