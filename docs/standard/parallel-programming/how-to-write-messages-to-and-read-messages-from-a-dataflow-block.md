---
title: Практическое руководство. Запись и чтение сообщений в блоке потока данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
ms.openlocfilehash: 58927803b741acf6c1964b35f6603e6901f9cbf1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139290"
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Практическое руководство. Запись и чтение сообщений в блоке потока данных
В этом документе описываются способы использования библиотеки потоков данных TPL для записи сообщений в блок потока данных и считывания сообщений из него. Библиотека потоков данных TPL предоставляет как синхронные, так и асинхронные методы для записи сообщений в блок потока данных и чтения сообщений из него. В этом документе используется класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>. Класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> помещает сообщения в буфер и работает и в качестве источника сообщений, и как адресат сообщения.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="writing-to-and-reading-from-a-dataflow-block-synchronously"></a>Синхронная запись в блок потока данных и чтение из него  
 В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> для записи в блок потока данных <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> для чтения из того же объекта.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 Можно также использовать метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> для чтения из блока потока данных, как показано в следующем примере. Метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> не блокирует текущий поток и удобен, если необходимо периодически запрашивать данные.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Поскольку метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> действует синхронно, объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> в предыдущих примерах получает все данные, прежде чем второй цикл считывает данные. Следующий пример расширяет первый пример путем использования <xref:System.Threading.Tasks.Parallel.Invoke%2A> для чтения и записи в блок сообщений в параллельном режиме. Поскольку <xref:System.Threading.Tasks.Parallel.Invoke%2A> выполняет действия параллельно, значения не записываются в объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> в каком-либо определенном порядке.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## <a name="writing-to-and-reading-from-a-dataflow-block-asynchronously"></a>Асинхронная запись в блок потока данных и чтение из него  
 В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> для асинхронной записи в объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> для асинхронного чтения из того же объекта. В этом образце используются операторы [async](../../csharp/language-reference/keywords/async.md) и [await](../../csharp/language-reference/operators/await.md) ([Async](../../visual-basic/language-reference/modifiers/async.md) и [Await](../../visual-basic/language-reference/operators/await-operator.md) в Visual Basic) для асинхронной передачи данных и считывания их из блока целевого объекта. Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> рекомендуется, если необходимо обеспечить возможность использования отложенных сообщений для потока данных. Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> полезен для использования, если вы собираетесь работать с данными, когда они становятся доступны. Дополнительные сведения о распространении сообщений среди блоков сообщений см. в разделе "Передача сообщений" документа [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Полный пример  
 В следующем примере приведен полный код для этого документа.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="next-steps"></a>Следующие шаги  
 В этом примере показано, как считывать и записывать в блок сообщений напрямую. Можно также подключить блоки потока данных для создания *конвейеров*, которые являются линейными последовательностями блоков потока данных, или *сетей*, являющихся графами блоков потоков данных. Конвейеры или сети асинхронно распространяют исходные данные целевым объектам, когда данные становятся доступны. Пример создания базового конвейера потока данных см. в разделе [Пошаговое руководство. Создание конвейера потока данных](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md). Пример создания более сложной сети потока данных см. в разделе [Пошаговое руководство. Использование потока данных в приложении Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)  
  
## <a name="see-also"></a>См. также

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
