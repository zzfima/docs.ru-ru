---
title: "Практическое руководство. Извлечение вложенной задачи из оболочки"
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
helpviewer_keywords: tasks, how to unwrap nested tasks
ms.assetid: a0769dd2-0f6d-48ca-8418-a9d39de7f450
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2da3de912abb693c4342e1ede02f273348e4b571
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-unwrap-a-nested-task"></a>Практическое руководство. Извлечение вложенной задачи из оболочки
Можно вернуть задачу из метода и затем ожидать или продолжить с этой задачи, как показано в следующем примере:  
  
 [!code-csharp[TPL_Unwrap#01](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#01)]
 [!code-vb[TPL_Unwrap#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#01)]  
  
 В предыдущем примере <xref:System.Threading.Tasks.Task%601.Result%2A> свойство относится к типу `string` (`String` в Visual Basic).  
  
 Однако в некоторых сценариях может потребоваться создать задачу в другую задачу, а затем возвращаете вложенной задачи. В этом случае `TResult` присоединенной задачи является задачей. В следующем примере свойство результат является `Task<Task<string>>` в C# или `Task(Of Task(Of String))` в Visual Basic.  
  
 [!code-csharp[TPL_Unwrap#02](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#02)]
 [!code-vb[TPL_Unwrap#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#02)]  
  
 Несмотря на то, что можно написать код для распаковки внешней задачи и извлечения исходной задачи и ее <xref:System.Threading.Tasks.Task%601.Result%2A> свойство, такой код не просто запись, так как необходимо обрабатывать исключения, а также запросы отмены. В этом случае рекомендуется использовать один из <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> методы расширения, как показано в следующем примере.  
  
 [!code-csharp[TPL_UnWrap#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#03)]
 [!code-vb[TPL_UnWrap#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippets1-3.vb#03)]  
  
 <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> Методы можно использовать для преобразования любого `Task<Task>` или `Task<Task<TResult>>` (`Task(Of Task)` или `Task(Of Task(Of TResult))` в Visual Basic) для `Task` или `Task<TResult>` (`Task(Of TResult)` в Visual Basic). Новая задача полностью представляет внутреннюю вложенную задачу и включает состояние отмены и все исключения.  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется использование <xref:System.Threading.Tasks.TaskExtensions.Unwrap%2A> методы расширения.  
  
 [!code-csharp[TPL_UnWrap#04](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_unwrap/cs/unwrapprogram.cs#04)]
 [!code-vb[TPL_UnWrap#04](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_unwrap/vb/snippet04.vb#04)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Tasks.TaskExtensions?displayProperty=nameWithType>  
 [Асинхронное программирование на основе задач](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
