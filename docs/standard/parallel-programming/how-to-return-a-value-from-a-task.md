---
title: "How to: Return a Value from a Task | Microsoft Docs"
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
  - "tasks, how to return a value"
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Return a Value from a Task
В этом примере показано, как использовать тип <xref:System.Threading.Tasks.Task%601?displayProperty=fullName> для возврата значения из свойства <xref:System.Threading.Tasks.Task%601.Result%2A>.  Здесь требуется, чтобы каталог C:\\Users\\Public\\Pictures\\Sample Pictures\\ существовал и содержал файлы.  
  
## Пример  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 Свойство <xref:System.Threading.Tasks.Task%601.Result%2A> блокирует вызывающий поток до завершения задачи.  
  
 Чтобы узнать, как передать результат одной <xref:System.Threading.Tasks.Task%601?displayProperty=fullName> в задачу продолжения, см. раздел [Создание цепочки задач с помощью задач продолжения](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## См. также  
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)   
 [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)