---
title: "Практическое руководство. Использование JoinBlock для чтения данных из нескольких источников"
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
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41445e4874b94809840ecf9ebda6f27ccc955c9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a>Практическое руководство. Использование JoinBlock для чтения данных из нескольких источников
В этом документе объясняется, как использовать класс <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> для выполнения операции, если данные доступны из нескольких источников. Также здесь показано, как использовать нежадный режим, чтобы разрешить нескольким блокам соединения совместно использовать источник данных более эффективно.  
  
> [!TIP]
>  Библиотека потоков данных TPL (пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]. Чтобы установить <xref:System.Threading.Tasks.Dataflow> пространства имен, откройте проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите **управление пакетами NuGet** меню проекта и выполните поиск в Интернете `Microsoft.Tpl.Dataflow` пакета.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется три типа ресурсов: `NetworkResource`, `FileResource` и `MemoryResource`, и выполняются операции, когда ресурсы становятся доступными. В этом примере требуется пара `NetworkResource` и `MemoryResource` для выполнения первой операции и пара `FileResource` и `MemoryResource` для выполнения второй операции. Чтобы позволить выполнение этих операций, когда доступны все необходимые ресурсы, в этом примере используется класс <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>. Если объект <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> получает данные из всех источников, он распространяет эти данные по целевым объектам, в этом примере — объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Оба объекта <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> выполняют чтение из общего пула объектов `MemoryResource`.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Чтобы включить рациональное использование общего пула объектов `MemoryResource`, в этом примере определяется объект <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>, у которого свойству <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> задано значение `False`, для создания объектов <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>, действующих в нежадном режиме. Нежадный блок соединения откладывает все входящие сообщения до тех пор, пока значение не станет доступно из каждого источника. Если какое-либо из отложенных сообщений, принято другим блоком, блок соединения перезапускает процесс. Нежадный режим позволяет блокам соединения, которые совместно используют один или несколько блоков источника, выполнять работу, пока другие блоки ожидают данных. В этом примере, если объект `MemoryResource` добавляется в пул `memoryResources`, первый блок соединения для получения его второго источника данных может выполняться. Если бы в этом примере использовался жадный режим, устанавливаемый по умолчанию, один блок соединения мог бы занять объект `MemoryResource` и ожидать, пока второй ресурс не станет доступным. Однако, если для другого блока соединения доступен второй источник данных, он не может выполняться, поскольку объект `MemoryResource` был занят другим блоком соединения.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **CSC.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Использование нежадных соединений также может помочь предотвратить взаимоблокировку в приложении. В приложении программного обеспечения *взаимоблокировки* возникает, когда два или несколько процессов каждая удерживает ресурс и ожидает освобождения другого ресурса другим процессом. Рассмотрим приложение, определяющее два объекта <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>. Оба объекта считывают данные из двух общих блоков источника. В жадном режиме, если один блок соединения считывает из первого источника, а второй блок соединения считывает из второго источника, в приложении может произойти взаимоблокировка, поскольку оба блока соединения ожидают освобождения ресурса другим блоком. В нежадном режиме каждый блок соединения считывает из своих источников, только если все данные доступны, и таким образом устраняется риск взаимоблокировки.  
  
## <a name="see-also"></a>См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
