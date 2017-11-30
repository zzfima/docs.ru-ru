---
title: "Практическое руководство. Запись и чтение сообщений в блоке потока данных"
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
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, reading and writing messages
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bf609a8c350a44fc802cce0ec10693431bbf4f42
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-write-messages-to-and-read-messages-from-a-dataflow-block"></a>Практическое руководство. Запись и чтение сообщений в блоке потока данных
В этом документе описываются способы использования библиотеки потоков данных TPL для записи сообщений в блок потока данных и считывания сообщений из него. Библиотека потоков данных TPL предоставляет как синхронные, так и асинхронные методы для записи сообщений в блок потока данных и чтения сообщений из него. В этом документе используется класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=nameWithType>. Класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> помещает сообщения в буфер и работает и в качестве источника сообщений, и как адресат сообщения.  
  
> [!TIP]
>  Библиотека потоков данных TPL (пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Чтобы установить <xref:System.Threading.Tasks.Dataflow> пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** меню проекта и выполните поиск в Интернете `Microsoft.Tpl.Dataflow` пакета.  
  
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
 В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> для асинхронной записи в объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> для асинхронного чтения из того же объекта. В этом образце используются операторы [async](~/docs/csharp/language-reference/keywords/async.md) и [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) и [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) в Visual Basic) для асинхронной передачи данных и считывания их из блока целевого объекта. Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> рекомендуется, если необходимо обеспечить возможность использования отложенных сообщений для потока данных. Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> полезен для использования, если вы собираетесь работать с данными, когда они становятся доступны. Дополнительные сведения о распространении сообщений среди блоков сообщений см. в разделе "Передача сообщений" документа [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## <a name="a-complete-example"></a>Полный пример  
 В следующем примере приведен полный код для этого документа.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowReadWrite.cs` (`DataflowReadWrite.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## <a name="next-steps"></a>Дальнейшие действия  
 В этом примере показано, как считывать и записывать в блок сообщений напрямую. Можно также подключить блоки потока данных для создания *конвейеров*, которые являются линейными последовательностями блоков потока данных, или *сетей*, являющихся графами блоков потоков данных. Конвейеры или сети асинхронно распространяют исходные данные целевым объектам, когда данные становятся доступны. Пример, в котором создается базовый конвейер потока данных, см. в разделе [Пошаговое руководство. Создание конвейера потока данных](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md). Пример создания более комплексной сети потока данных см. в разделе [Пошаговое руководство. Использование потоков данных в приложении Windows Forms](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## <a name="see-also"></a>См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
