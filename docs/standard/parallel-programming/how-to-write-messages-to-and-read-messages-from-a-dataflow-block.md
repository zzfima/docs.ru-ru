---
title: "How to: Write Messages to and Read Messages from a Dataflow Block | Microsoft Docs"
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
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, reading and writing messages"
ms.assetid: 1a9bf078-aa82-46eb-b95a-f87237f028c5
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Write Messages to and Read Messages from a Dataflow Block
В этом документе описано, как использовать библиотеку потоков данных TPL для записи сообщений в и считывания сообщения из блока потока данных.  Библиотека потоков данных TPL предоставляет синхронные и асинхронные методы для записи сообщений и чтения их из блока потока данных.  В этом документе используется класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601?displayProperty=fullName>.  Класс <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> буферизирует сообщения и работает и в качестве источника сообщений, и как целевой объект сообщения.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Запись и чтение блока потока данных синхронно  
 В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> для записи в <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> блок потока данных и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> для чтения из того же объекта.  
  
 [!code-csharp[TPLDataflow_ReadWrite#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#2)]
 [!code-vb[TPLDataflow_ReadWrite#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#2)]  
  
 Можно также использовать метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> для чтения из блока потока данных, как показано в следующем примере.  Метод <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> не блокирует текущий поток и удобен, если нужно периодически запрашивать данные.  
  
 [!code-csharp[TPLDataflow_ReadWrite#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#3)]
 [!code-vb[TPLDataflow_ReadWrite#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#3)]  
  
 Поскольку метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> действует синхронно, объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> в предыдущих примерах получает все данные, прежде чем второй цикл считывает данные.  Следующий пример расширяет первый пример с помощью <xref:System.Threading.Tasks.Parallel.Invoke%2A> для чтения и записи блока сообщений параллельно.  Поскольку <xref:System.Threading.Tasks.Parallel.Invoke%2A> выполняет действия параллельно, значения не записываются в объект <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> в каком\-либо определенном порядке.  
  
 [!code-csharp[TPLDataflow_ReadWrite#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#4)]
 [!code-vb[TPLDataflow_ReadWrite#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#4)]  
  
## Запись и чтение блока потока данных асинхронно  
 В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> для асинхронной записи в <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> объект и метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> для асинхронного чтения из того же объекта.  В этом образце используются операторы [async](../Topic/async%20\(C%23%20Reference\).md) и [await](../Topic/await%20\(C%23%20Reference\).md) \([Async](../Topic/Async%20\(Visual%20Basic\).md) и [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) в Visual Basic\) для асинхронной передачи данных и считывания их из блока целевого объекта.  Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A> рекомендуется, если необходимо обеспечить возможность отложенных сообщений для потока данных.  Метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A> полезен для использования, если вы собираетесь работать с данными, когда они становятся доступны.  Дополнительные сведения о распространении сообщений среди блоков сообщений см. в разделе [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md).  
  
 [!code-csharp[TPLDataflow_ReadWrite#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#5)]
 [!code-vb[TPLDataflow_ReadWrite#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#5)]  
  
## Полный пример  
 В следующем примере приведен полный код для этого документа.  
  
 [!code-csharp[TPLDataflow_ReadWrite#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_readwrite/cs/dataflowreadwrite.cs#1)]
 [!code-vb[TPLDataflow_ReadWrite#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_readwrite/vb/dataflowreadwrite.vb#1)]  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowReadWrite.cs` \(`DataflowReadWrite.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReadWrite.vb**  
  
## Следующие действия  
 В этом примере показано, как считывать и записывать в блок сообщений напрямую.  Можно также подключить блоки потока данных в для создания *конвейеров*, которые являются линейными последовательностями блоков потока данных, или *сетей*, являющихся графами блоков потоков данных.  Конвейеры или сети асинхронно распространяют данные целевым объектам, когда данные становятся доступны.  Пример, в котором создается базовый конвейер потока данных см. в разделе [Walkthrough: Creating a Dataflow Pipeline](../../../docs/standard/parallel-programming/walkthrough-creating-a-dataflow-pipeline.md).  Пример создания более сложной сети потока данных см. в разделе [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)