---
title: Как выполнить Использование JoinBlock для чтения данных из нескольких источников
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, joining blocks in
- dataflow blocks, joining in TPL
ms.assetid: e9c1ada4-ac57-4704-87cb-2f5117f8151d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0031e352fea845ca4831b4df3a67c9cc6b67e876
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222289"
---
# <a name="how-to-use-joinblock-to-read-data-from-multiple-sources"></a>Как выполнить Использование JoinBlock для чтения данных из нескольких источников
В этом документе объясняется, как использовать класс <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> для выполнения операции, если данные доступны из нескольких источников. Также здесь показано, как использовать нежадный режим, чтобы разрешить нескольким блокам соединения совместно использовать источник данных более эффективно.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Пример  
 В следующем примере определяется три типа ресурсов: `NetworkResource`, `FileResource` и `MemoryResource`, и выполняются операции, когда ресурсы становятся доступными. В этом примере требуется пара `NetworkResource` и `MemoryResource` для выполнения первой операции и пара `FileResource` и `MemoryResource` для выполнения второй операции. Чтобы позволить выполнение этих операций, когда доступны все необходимые ресурсы, в этом примере используется класс <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>. Если объект <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> получает данные из всех источников, он распространяет эти данные по целевым объектам, в этом примере — объекту <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>. Оба объекта <xref:System.Threading.Tasks.Dataflow.JoinBlock%602> выполняют чтение из общего пула объектов `MemoryResource`.  
  
 [!code-csharp[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_nongreedyjoin/cs/nongreedyjoin.cs#1)]
 [!code-vb[TPLDataflow_NonGreedyJoin#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_nongreedyjoin/vb/nongreedyjoin.vb#1)]  
  
 Чтобы включить рациональное использование общего пула объектов `MemoryResource`, в этом примере определяется объект <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions>, у которого свойству <xref:System.Threading.Tasks.Dataflow.GroupingDataflowBlockOptions.Greedy%2A> задано значение `False`, для создания объектов <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>, действующих в нежадном режиме. Нежадный блок соединения откладывает все входящие сообщения до тех пор, пока значение не станет доступно из каждого источника. Если какое-либо из отложенных сообщений, принято другим блоком, блок соединения перезапускает процесс. Нежадный режим позволяет блокам соединения, которые совместно используют один или несколько блоков источника, выполнять работу, пока другие блоки ожидают данных. В этом примере, если объект `MemoryResource` добавляется в пул `memoryResources`, первый блок соединения для получения его второго источника данных может выполняться. Если бы в этом примере использовался жадный режим, устанавливаемый по умолчанию, один блок соединения мог бы занять объект `MemoryResource` и ожидать, пока второй ресурс не станет доступным. Однако, если для другого блока соединения доступен второй источник данных, он не может выполняться, поскольку объект `MemoryResource` был занят другим блоком соединения.  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowNonGreedyJoin.cs` (`DataflowNonGreedyJoin.vb` для Visual Basic), затем выполните в окне командной строки разработчика для Visual Studio следующую команду.  
  
 Visual C#  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.cs**  
  
 Visual Basic  
  
 **vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowNonGreedyJoin.vb**  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Использование нежадных соединений также может помочь предотвратить взаимоблокировку в приложении. В приложении программного обеспечения *взаимоблокировка* возникает, когда два или несколько процессов используют ресурс и одновременно ожидают, пока другой процесс не освободит какой-либо из ресурсов. Рассмотрим приложение, определяющее два объекта <xref:System.Threading.Tasks.Dataflow.JoinBlock%602>. Оба объекта считывают данные из двух общих блоков источника. В жадном режиме, если один блок соединения считывает из первого источника, а второй блок соединения считывает из второго источника, в приложении может произойти взаимоблокировка, поскольку оба блока соединения ожидают освобождения ресурса другим блоком. В нежадном режиме каждый блок соединения считывает из своих источников, только если все данные доступны, и таким образом устраняется риск взаимоблокировки.  
  
## <a name="see-also"></a>См. также

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
