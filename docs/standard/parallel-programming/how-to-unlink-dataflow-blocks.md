---
title: Практическое руководство. Удаление связей с блоками потоков данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ead52a55bfc45cbffc98552f3a7f4b01e1a6aa1e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-unlink-dataflow-blocks"></a>Практическое руководство. Удаление связей с блоками потоков данных
В этом документе описан способ отсоединения целевого блока потока данных от его источника.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Пример  
 В следующем примере создаются три объекта <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, каждый из которых вызывает метод `TrySolution` для вычисления значения. В этом примере для завершения требуется только результат первого вызова `TrySolution`.  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 Чтобы получить значение от первого завершившегося объекта <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, в этом примере определяется метод `ReceiveFromAny(T)`. Метод `ReceiveFromAny(T)` принимает массив объектов <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> и связывает каждый из этих объектов с объектом <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>. При использовании метода <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> для привязки блока источника потока данных к целевому блоку источник передает сообщения целевому объекту по мере поступления данных. Поскольку класс <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> принимает только первое предлагаемое сообщение, метод `ReceiveFromAny(T)` получает результат путем вызова метода <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A>. Таким образом создается первое сообщение, которое предлагается объекту <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601>. Метод <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> имеет перегруженную версию, которая принимает <xref:System.Boolean> параметр `unlinkAfterOne`, который, если он имеет значение `True`, обеспечивает отсоединение источника данных от целевого объекта после того, как целевой объект получит одно сообщение от источника. Для объекта <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> важно отсоединиться от источников, поскольку связь между массивом источников и объектом <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> больше не требуется после того, как объект <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> получает сообщение.  
  
 Чтобы оставшиеся вызовы `TrySolution` могли завершиться после вычисления значения одним из них, метод `TrySolution` принимает объект <xref:System.Threading.CancellationToken>, который отменяется после возврата вызова `ReceiveFromAny(T)`. Метод <xref:System.Threading.SpinWait.SpinUntil%2A> возвращает результат, когда объект <xref:System.Threading.CancellationToken> отменяется.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` для Visual Basic), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 Visual C#  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**  
  
 Visual Basic  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**  

## <a name="see-also"></a>См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
