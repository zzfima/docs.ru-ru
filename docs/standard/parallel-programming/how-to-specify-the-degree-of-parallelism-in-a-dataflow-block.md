---
title: "How to: Specify the Degree of Parallelism in a Dataflow Block | Microsoft Docs"
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
  - "dataflow block, specifying parallelism in TPL"
  - "Task Parallel Library, dataflows"
  - "TPL dataflow library, specifying parallelism"
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# How to: Specify the Degree of Parallelism in a Dataflow Block
В этом документе описывается, как задать свойство <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=fullName>, чтобы позволить блоку выполнения потока данных обрабатывать более одного сообщения единовременно.  Это удобно при наличии блока потока данных, который выполняет длительное вычисление и может получить выгоду от обработки сообщений параллельным образом.  В этом примере используется класс <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=fullName> для параллельного выполнения нескольких операций потока данных; однако можно задать максимальную степень параллелизма в любом из предопределенных типов блоков выполнения, предоставляемых библиотекой потоков данных: <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=fullName> и <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=fullName>.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Для установки пространства имен <xref:System.Threading.Tasks.Dataflow> откройте свой проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Управление пакетами NuGet** в меню "Проект" и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Пример  
 В следующем примере выполняется два вычисления потока данных и выводится остаток времени, необходимый для каждого вычисления.  Первое вычисление указывает максимальную степень параллелизма 1, что является значением по умолчанию.  Максимальная степень параллелизма 1 заставляет блок потока данных обрабатывать сообщения последовательно.  Второе вычисление напоминает первое за исключением того, что для него указывается максимальная степень параллелизма, равная числу доступных процессоров.  Это позволяет блоку потока данных выполнять несколько операций параллельно.  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `DataflowDegreeOfParallelism.cs` \(`DataflowDegreeOfParallelism.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**  
  
## Отказоустойчивость  
 По умолчанию все предопределенные блоки потока данных распространяют сообщения в том порядке, в котором они их получают.  Хотя при указании максимальной степени параллелизма больше 1 несколько сообщений обрабатываются одновременно, они по\-прежнему распространяются в порядке, в котором были получены.  
  
 Поскольку свойство <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> представляет максимальную степень параллелизма, блок потока данных может выполняться с меньшей степенью параллелизма, чем задано.  Блок потока данных может использовать меньшую степень параллелизма для удовлетворения функциональных требований или при недостатке доступных системных ресурсов.  Блок потока данных никогда не выбирает степень параллелизма, превосходящую указанную.  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)