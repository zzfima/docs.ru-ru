---
title: Практическое руководство. Указание степени параллелизма в блоке потока данных
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
ms.openlocfilehash: 50399d6cd32fe310089395ac8c660b08151ba808
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73141654"
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a>Практическое руководство. Указание степени параллелизма в блоке потока данных
В этом документе описывается, как задать свойство <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType>, чтобы позволить блоку выполнения потока данных обрабатывать более одного сообщения единовременно. Это удобно при наличии блока потока данных, который выполняет длительное вычисление и может получить выгоду от обработки сообщений параллельным образом. В этом примере используется класс <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> для параллельного выполнения нескольких операций потока данных; однако можно задать максимальную степень параллелизма в любом из предопределенных типов блоков выполнения, предоставляемых библиотекой потоков данных: <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> и <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Пример  
 В следующем примере выполняется два вычисления потока данных и выводится остаток времени, необходимый для каждого вычисления. Первое вычисление указывает максимальную степень параллелизма 1, что является значением по умолчанию. Максимальная степень параллелизма 1 заставляет блок потока данных обрабатывать сообщения последовательно. Второе вычисление напоминает первое за исключением того, что для него указывается максимальная степень параллелизма, равная числу доступных процессоров. Это позволяет блоку потока данных выполнять несколько операций параллельно.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 По умолчанию все предопределенные блоки потока данных распространяют сообщения в том порядке, в котором они их получают.  Хотя при указании максимальной степени параллелизма больше 1 несколько сообщений обрабатываются одновременно, они по-прежнему распространяются в порядке, в котором были получены.  
  
 Поскольку свойство <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> представляет максимальную степень параллелизма, блок потока данных может выполняться с меньшей степенью параллелизма, чем задано. Блок потока данных может использовать меньшую степень параллелизма для удовлетворения функциональных требований или при недостатке доступных системных ресурсов. Блок потока данных никогда не выбирает степень параллелизма, превосходящую указанную.  
  
## <a name="see-also"></a>См. также раздел

- [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
