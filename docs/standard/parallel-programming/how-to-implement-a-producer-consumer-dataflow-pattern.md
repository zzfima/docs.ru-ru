---
title: Практическое руководство. Реализация шаблона потока данных "производитель-получатель"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
ms.openlocfilehash: 2db8cfcfc26b001703e08a501c430be4313aca03
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73091490"
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a>Практическое руководство. Реализация шаблона потока данных "производитель-получатель"
В этом документе описан способ использования библиотеки потоков данных TPL для реализации шаблона "производитель-получатель". В этом шаблоне *производитель* отправляет сообщения в блок сообщений, а *потребитель* считывает сообщения из этого блока.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a>Пример  
 В следующем примере показана базовая модель "производитель-получатель", которая использует поток данных. Метод `Produce` записывает массивы, содержащие случайные байты данных, в объект <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType>, а метод `Consume` выполняет чтение байтов из объекта <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>. Используя интерфейсы <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> и <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> вместо их производных типов, можно создавать пригодный для повторного использования код, который может работать с различными типами блоков потока данных. В этом примере используется класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>. Поскольку класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> действует и как блок источника, и как целевой блок, потребитель и производитель могут использовать общий объект для передачи данных.  
  
 Метод `Produce` вызывает метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> в цикле для синхронной записи данных в целевой блок. После того, как метод `Produce` записывает все данные в целевой блок, он вызывает метод <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A>, чтобы указать, что у этого блока никогда не будет дополнительных доступных данных. Метод `Consume` использует операторы [async](../../csharp/language-reference/keywords/async.md) и [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) и [Await](../../visual-basic/language-reference/operators/await-operator.md) в Visual Basic) для асинхронного вычисления общего числа байтов, полученных от объекта <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>. Для асинхронной работы метод `Consume` вызывает метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>, чтобы получать уведомления, если блок источника получит доступные данные и если у блока источника никогда не будет дополнительных доступных данных.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 В предыдущем примере используется только один получатель для обработки исходных данных. При наличии нескольких получателей в приложении следует использовать метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> для чтения данных из блока источника, как показано в следующем примере.  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 Метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> возвращает `False`, когда нет доступных данных. Когда несколько потребителей должны использовать блок источника параллельно, этот механизм гарантирует, что данные все еще будут доступны после вызова <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.  
  
## <a name="see-also"></a>См. также раздел

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
