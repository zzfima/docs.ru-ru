---
title: "How to: Unwrap a Nested Task | Microsoft Docs"
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
  - "tasks, how to unwrap nested tasks"
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unwrap a Nested Task
Можно вернуть задачу из метода, а затем подождать или продолжить с этой задачи, как показано в следующем примере:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 В предыдущем примере свойство <xref:System.Threading.Tasks.Task%601.Result%2A> строкового типа `string` \(`String` в Visual Basic\).  
  
 Однако в некоторых сценариях, может возникнуть необходимость создания задачи в рамках другой задачи, а затем возврата вложенной задачи.  В таком случае `TResult` присоединенной задачи является задачей.  В следующем примере свойство Result имеет значение `Task<Task<string>>` в C\# или `Task(Of Task(Of String))` в Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Несмотря на то что существует возможность написания кода для развертывания внешней задачи и извлечения исходной задачи и ее свойства <xref:System.Threading.Tasks.Task%601.Result%2A>, такой код непрост в написании, поскольку в нем необходимо обрабатывать исключения и запросы отмены.  В такой ситуации рекомендуется использовать один из методов расширения <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>, как показано в следующем примере.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 Методы <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> можно использовать для преобразования любого `Task<Task>` или `Task<Task<TResult>>` \(`Task(Of Task)` или `Task(Of Task(Of TResult))` в Visual Basic\) в `Task` или `Task<TResult>`  \(`Task(Of TResult)` в Visual Basic\).  Новая задача полностью представляет внутреннюю вложенную задачу и включает состояние отмены и все исключения.  
  
## Пример  
 В следующем примере демонстрируется использование методов расширения <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A>.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## См. также  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=fullName>   
 [Task Parallelism](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)