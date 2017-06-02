---
title: "How to: Unlink Dataflow Blocks | Microsoft Docs"
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
  - "dataflow blocks, unlinking in TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, unlinking dataflow blocks"
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# How to: Unlink Dataflow Blocks
В этом документе описано, как разъединить целевой блок потока данных и его источник.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Пример  
 В следующем примере создаются три объекта <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, каждый из которых вызывает метод `TrySolution` для вычисления значения.  В этом примере для завершения требуется только результат первого вызова `TrySolution`.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Чтобы получить значение из первого объекта <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, который завершился, этот пример определяет метод `ReceiveFromAny(T)`.  Метод `ReceiveFromAny(T)` принимает массив объектов <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> и связывает каждый из этих объектов с объектом <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.  При использовании метода <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> для связывания блока источника потока данных с целевым блоком, источник распространяет сообщения целевому объекту по мере поступления данных.  Поскольку класс <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> принимает только первое пришедшее сообщение, метод `ReceiveFromAny(T)` получает результат вызовом <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>.  Этот код создает первое сообщение, которое отправляется объекту <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>.  Метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> имеет перегруженную версию, которая принимает <xref:System.Boolean> параметр `unlinkAfterOne`, который, если он имеет значение `True`, обеспечивает отсоединение источника данных от целевого блока после того, как целевой блок получит одно сообщение от источника.  Для объекта <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> важно отсоединиться от источника, поскольку связь между массивом источников и объектом <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> больше не нужна после того, как объект <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> получает сообщение.  
  
 Чтобы завершить оставшиеся вызовы `TrySolution`, когда один из них вычисляет значение, метод `TrySolution` принимает объект <xref:System.Threading.CancellationToken>, которые отменяется после возврата из метода `ReceiveFromAny(T)`.  Метод <xref:System.Threading.SpinWait.SpinUntil%2A> завершается, когда объект <xref:System.Threading.CancellationToken> отменен.  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowReceiveAny.cs` \(`DataflowReceiveAny.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  
  
## Отказоустойчивость  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)