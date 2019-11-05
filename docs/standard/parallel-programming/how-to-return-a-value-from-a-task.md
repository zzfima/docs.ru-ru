---
title: Практическое руководство. Возврат значения из задачи
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to return a value
ms.assetid: c4bc0f44-eba2-4e96-9e03-1cc787461e61
ms.openlocfilehash: 495f68114bfe960b8182be4ab76b72043b2d0cc7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141668"
---
# <a name="how-to-return-a-value-from-a-task"></a>Практическое руководство. Возврат значения из задачи
В этом примере показано, как использовать тип <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> для возврата значения из свойства <xref:System.Threading.Tasks.Task%601.Result%2A>. Здесь требуется, чтобы каталог C:\Users\Public\Pictures\Sample Pictures\ существовал и содержал файлы.  
  
## <a name="example"></a>Пример  
 [!code-csharp[TPL#10](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/returnavalue10.cs#10)]
 [!code-vb[TPL#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/10_returnavalue.vb#10)]  
  
 Свойство <xref:System.Threading.Tasks.Task%601.Result%2A> блокирует вызывающий поток до завершения задачи.  
  
 Дополнительные сведения о том, как передать результат одной <xref:System.Threading.Tasks.Task%601?displayProperty=nameWithType> в задачу продолжения, см. в руководстве по [созданию цепочки задач с помощью задач продолжения](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md).  
  
## <a name="see-also"></a>См. также

- [Асинхронное программирование на основе задач](../../../docs/standard/parallel-programming/task-based-asynchronous-programming.md)
- [Лямбда-выражения в PLINQ и TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md)
