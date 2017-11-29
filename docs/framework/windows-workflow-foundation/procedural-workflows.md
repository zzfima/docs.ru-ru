---
title: "Процедурные рабочие процессы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52401de9-9115-472d-8fd9-047af6a072b9
caps.latest.revision: "17"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e8f517b68695457c2819612bbd092b5ea03c5f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="procedural-workflows"></a><span data-ttu-id="5470c-102">Процедурные рабочие процессы</span><span class="sxs-lookup"><span data-stu-id="5470c-102">Procedural Workflows</span></span>
<span data-ttu-id="5470c-103">Процедурные рабочие процессы используют методы управления потоком выполнения, аналогичные таким методам в процедурных языках.</span><span class="sxs-lookup"><span data-stu-id="5470c-103">Procedural workflows use flow-control methods similar to those found in procedural languages.</span></span> <span data-ttu-id="5470c-104">К этим конструкциям относятся `While` и `If`.</span><span class="sxs-lookup"><span data-stu-id="5470c-104">These constructs include `While` and `If`.</span></span> <span data-ttu-id="5470c-105">Такие рабочие процессы можно свободно создавать с применением других действий управления потоком выполнения, таких как <xref:System.Activities.Statements.Flowchart> и <xref:System.Activities.Statements.Sequence>.</span><span class="sxs-lookup"><span data-stu-id="5470c-105">These workflows can be freely composed using other flow control activities such as <xref:System.Activities.Statements.Flowchart> and <xref:System.Activities.Statements.Sequence>.</span></span>  
  
## <a name="controlling-execution-flow"></a><span data-ttu-id="5470c-106">Управление потоком выполнения</span><span class="sxs-lookup"><span data-stu-id="5470c-106">Controlling Execution Flow</span></span>  
 <span data-ttu-id="5470c-107">Библиотека действий рабочих процессов содержит действия для моделирования большинства методов управления потоком выполнения, используемых в процедурных языках.</span><span class="sxs-lookup"><span data-stu-id="5470c-107">The workflow activity library has activities for modeling most flow-control methods used in procedural languages.</span></span> <span data-ttu-id="5470c-108">К ним относятся следующие методы.</span><span class="sxs-lookup"><span data-stu-id="5470c-108">These include:</span></span>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.DoWhile>  
  
-   <xref:System.Activities.Statements.ForEach%601>  
  
-   <xref:System.Activities.Statements.Parallel>  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>  
  
-   <xref:System.Activities.Statements.If>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.Pick>  
  
 <span data-ttu-id="5470c-109">Чтобы использовать действия управления потоком выполнения, путем перетаскивания их из **действия** элементов в составное действие в окне конструктора.</span><span class="sxs-lookup"><span data-stu-id="5470c-109">To use flow control activities, drag and drop them from the **Activity** toolbox into a composite activity inside the designer window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5470c-110">Если для размещения рабочих процессов в веб-ферме используется [!INCLUDE[dublin](../../../includes/dublin-md.md)], AppFabric будет перемещать экземпляры между различными серверами AppFabric.</span><span class="sxs-lookup"><span data-stu-id="5470c-110">If using the [!INCLUDE[dublin](../../../includes/dublin-md.md)] to host workflows on a Web farm, AppFabric will move instances between different AppFabric servers.</span></span> <span data-ttu-id="5470c-111">Для этого необходимо, чтобы ресурсы можно было совместно использовать на всех узлах.</span><span class="sxs-lookup"><span data-stu-id="5470c-111">This requires that the resources are able to be shared between all nodes.</span></span>  <span data-ttu-id="5470c-112">Ни одно из действий рабочих процессов .NET 4 по умолчанию не содержит операций, осуществляющих доступ к локальным ресурсам.</span><span class="sxs-lookup"><span data-stu-id="5470c-112">None of the default NET 4 workflow activities contain any operations that access local resources.</span></span> <span data-ttu-id="5470c-113">Поскольку AppFabric не реализует ни одного механизма пометки рабочего процесса как неперемещаемого, разработчику не следует создавать пользовательские действия, в которых возникает ошибка при перемещении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="5470c-113">Since AppFabric does not offer any mechanism to mark a workflow as immovable, a developer must not create custom activities that fail when a workflow is moved.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5470c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5470c-114">See Also</span></span>  
 [<span data-ttu-id="5470c-115">Рабочие процессы с блок-схемой</span><span class="sxs-lookup"><span data-stu-id="5470c-115">Flowchart Workflows</span></span>](../../../docs/framework/windows-workflow-foundation/flowchart-workflows.md)
