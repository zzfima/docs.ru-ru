---
title: "Walkthrough: Creating a Custom Dataflow Block Type | Microsoft Docs"
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
  - "TPL dataflow library, creating custom dataflow blocks"
  - "dataflow blocks, creating custom in TPL"
ms.assetid: a6147146-0a6a-4d9b-ab0f-237b3c1ac691
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Walkthrough: Creating a Custom Dataflow Block Type
Хотя библиотека потоков данных предоставляет несколько типов блоков потока данных, которые содержат различные функции, можно также создавать пользовательские типы блоков.  В этом документе описано, как создать тип блока потока данных, который реализует пользовательское расширение функциональности.  
  
## Обязательные компоненты  
 Ознакомьтесь с разделом [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) перед тем, как читать этот документ.  
  
> [!TIP]
>  Библиотека потоков данных TPL \(пространство имен <xref:System.Threading.Tasks.Dataflow?displayProperty=fullName>\) не поставляется с [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].  Чтобы установить пространство имен <xref:System.Threading.Tasks.Dataflow>, откройте ваш проект в [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], выберите пункт **Manage NuGet Packages** в меню Проект и выполните поиск пакета `Microsoft.Tpl.Dataflow` в сети.  
  
## Определение блока потока данных скользящего окна  
 Рассмотрим приложение потока данных, которое требует, чтобы входные значения были буферизированы и затем выводились по принципу скользящего окна.  Например, для входных значений {0, 1, 2, 3, 4, 5} и размера окна 3, блок потока данных скользящего окна создает массивы вывода {0, 1, 2}, {1, 2, 3}, {2, 3, 4} и {3, 4, 5}.  В следующих разделах описываются два способа создания типа блока потока данных, который реализует это пользовательское расширение функциональности.  Первый способ используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A>, чтобы объединить возможности объекта <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> и объекта <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> в один блок распространения.  Второй способ определяет класс, производный от <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>, и объединяет существующие функциональные возможности для предоставления пользовательского расширения функциональности.  
  
## Использование метода инкапсуляции для определения блока потока данных скользящего окна  
 В следующем примере используется метод <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Encapsulate%2A> для создания блока распространения из источника и целевого объекта.  Блок распространения позволяет блокам источника и целевого объекта использоваться в качестве отправителя и получателя данных.  
  
 Этот способ полезен, когда требуется пользовательская функциональность потока данных, но нет необходимости в типе, который предоставляет дополнительные методы, свойства или поля.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#1)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#1)]  
  
## Наследование от IPropagatorBlock для определения блока потока данных скользящего окна  
 В следующем примере показан класс `SlidingWindowBlock`.  Этот класс является производным от <xref:System.Threading.Tasks.Dataflow.IPropagatorBlock%602>, поэтому способен действовать и как источник, и как целевой объект данных.  Как и в предыдущем примере, класс `SlidingWindowBlock` построен на основе существующих типов блоков потока данных.  Однако класс `SlidingWindowBlock` также реализует методы, необходимые для интерфейсов <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>, <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> и <xref:System.Threading.Tasks.Dataflow.IDataflowBlock>.  Все эти методы переадресуют работу членам предопределенных типов блоков потока данных.  Например, метод `Post` передает работу члену данных `m_target`, также являющемуся объектом <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>.  
  
 Этот способ полезен, когда требуется пользовательская функциональность потока данных и тип, который предоставляет дополнительные методы, свойства или поля.  Например, класс `SlidingWindowBlock` также является производным от <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601>, чтобы он мог предоставлять методы <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> и <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceiveAll%2A>.  Класс `SlidingWindowBlock` также демонстрирует расширяемость, предоставляя свойство `WindowSize`, которое возвращает количество элементов в скользящем окне.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#2)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#2)]  
  
## Полный код примера  
 В следующем примере приведен полный код этого руководства.  Также показано, как использовать оба блока скользящего окна в методе, который записывает в блок, считывает из него, а результаты выводятся на консоль.  
  
 [!code-csharp[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_slidingwindowblock/cs/slidingwindowblock.cs#100)]
 [!code-vb[TPLDataflow_SlidingWindowBlock#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_slidingwindowblock/vb/slidingwindowblock.vb#100)]  
  
## Компиляция кода  
 Скопируйте код примера и вставьте его в проект Visual Studio или в файл с именем `SlidingWindowBlock.cs` \(`SlidingWindowBlock.vb` для [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), затем выполните в окне командной строки Visual Studio следующую команду.  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 **csc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.cs**  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 **vbc.exe \/r:System.Threading.Tasks.Dataflow.dll SlidingWindowBlock.vb**  
  
## Следующие действия  
  
## См. также  
 [Поток данных](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)