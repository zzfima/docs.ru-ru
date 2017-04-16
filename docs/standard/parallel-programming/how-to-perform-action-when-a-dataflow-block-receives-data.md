---
title: "How to: Perform Action When a Dataflow Block Receives Data | Microsoft Docs"
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
  - "TPL dataflow library, receiving data"
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Perform Action When a Dataflow Block Receives Data
Типы *Блока выполнения потока данных* вызывают предоставленный пользователем делегат при получении данных.  Классы <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=fullName>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName> и <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName> являются типами блоков выполнения потока данных.  Можно использовать ключевое слово `delegate` \(`Sub` в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), <xref:System.Action%601>, <xref:System.Func%602> или лямбда\-выражение при реализации рабочей функции для блока выполнения потока данных.  В этом документе описано, как использовать <xref:System.Func%602> и лямбда\-выражения для выполнения действий в блоках выполнения.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Пример  
 В следующем примере используется поток данных для считывания файла с диска и вычисления количества равных нулю байтов в этом файле.  Он использует <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> для считывания файла и вычисления числа нулевых байтов и <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> для печати числа нулевых байтов на консоль.  Объект <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> определяет объект <xref:System.Func%602> для выполнения работы, когда блоки получают данные.  Объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> использует лямбда\-выражение для печати на консоль числа прочитанных нулевых байтов.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 Хотя можно предоставить объекту <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> лямбда\-выражение, в этом примере используется <xref:System.Func%602>, чтобы позволить использовать метод `CountBytes` другому коду.  Объект <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> использует лямбда\-выражение, потому что работа, которую следует выполнить, специфична для этой задачи и вряд ли будет полезна для использования из другого кода.  Дополнительные сведения о работе лямбда\-выражений в библиотеке параллельных задач см. в разделе [Lambda Expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 В разделе Сводка о типах делегатов документа [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) перечислены типы делегатов, которые можно предоставлять объектам <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> и <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>.  В таблице также указано, работает ли делегат данного типа синхронно или асинхронно.  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowExecutionBlocks.cs` \(`DataflowExecutionBlocks.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## Отказоустойчивость  
 Этот пример предоставляет делегат типа <xref:System.Func%602> объекту <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> для синхронного выполнения задачи блока потока данных.  Чтобы позволить блоку потока данных работать асинхронно, предоставьте блоку потока данных делегат типа <xref:System.Func%601>.  Когда блок потока данных работает асинхронно, задача блока потока данных завершена, только если возвращенный объект <xref:System.Threading.Tasks.Task%601> завершается.  В следующем примере изменяется метод `CountBytes` и используются операторы [async](../Topic/async%20\(C%23%20Reference\).md) и [await](../Topic/await%20\(C%23%20Reference\).md) \([Async](../Topic/Async%20\(Visual%20Basic\).md) и [Await](../Topic/Await%20Operator%20\(Visual%20Basic\).md) в [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\) для асинхронного подсчета количества нулевых байтов в предоставленном файле.  Метод <xref:System.IO.FileStream.ReadAsync%2A> выполняет операции чтения файла асинхронно.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 Можно также использовать асинхронные лямбда\-выражения для выполнения действий в блоке выполнения потока данных.  В следующем примере изменяется объект <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, используемый в предыдущем примере, чтобы он использовал лямбда\-выражение для выполнения работы в асинхронном режиме.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)