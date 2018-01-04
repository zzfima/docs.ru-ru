---
title: "Проверка связей действий"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 93cb5e93791c001e3795408a4c6b77be772f26e0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="activity-relationships-validation"></a><span data-ttu-id="b049e-102">Проверка связей действий</span><span class="sxs-lookup"><span data-stu-id="b049e-102">Activity Relationships Validation</span></span>
<span data-ttu-id="b049e-103">Этот образец состоит из трех действий: `CreateCity`, `CreateState` и `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="b049e-103">This sample consists of three activities, `CreateCity`, `CreateState`, and `CreateCountry`.</span></span> <span data-ttu-id="b049e-104">Действие `CreateCity` должно быть внутри действия `CreateState`, а `CreateState` должно быть внутри действия `CreateCountry`.</span><span class="sxs-lookup"><span data-stu-id="b049e-104">`CreateCity` must be inside a `CreateState` activity, and `CreateState` must be inside a `CreateCountry` activity.</span></span> <span data-ttu-id="b049e-105">Для этого образца логика проверки реализуется в коде для действия `CreateState` и в XAML для действия `CreateCity`.</span><span class="sxs-lookup"><span data-stu-id="b049e-105">For the purpose of this sample, the validation logic is in code for the `CreateState` activity, and in XAML for the `CreateCity` activity.</span></span> <span data-ttu-id="b049e-106">Оба ограничения имеют одинаковое поведение.</span><span class="sxs-lookup"><span data-stu-id="b049e-106">Both constraints have the same behavior.</span></span>  
  
 <span data-ttu-id="b049e-107">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] предоставляет следующие три вспомогательных действия, которые позволяют разработчику проверять связи между действиями.</span><span class="sxs-lookup"><span data-stu-id="b049e-107">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] provides the following three helper activities that allow the developer to validate relationships between activities:</span></span>  
  
 <xref:System.Activities.Validation.GetParentChain>  
 <span data-ttu-id="b049e-108">Предоставляет коллекцию из всех действий, принадлежащих родительскому узлу текущего узла.</span><span class="sxs-lookup"><span data-stu-id="b049e-108">Provides the collection of all activities that belong to the parent of the current node</span></span>  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 <span data-ttu-id="b049e-109">Предоставляет коллекцию из всех действий, принадлежащих поддереву текущего узла, за исключением самого текущего узла.</span><span class="sxs-lookup"><span data-stu-id="b049e-109">Provides the collection of all activities that belong to the sub-tree of the current node, excluding the current node</span></span>  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 <span data-ttu-id="b049e-110">Предоставляет коллекцию из всех действий в том же дереве, что и текущий узел.</span><span class="sxs-lookup"><span data-stu-id="b049e-110">Provides the collection of all activities in the same tree as the current node</span></span>  
  
 <span data-ttu-id="b049e-111">В образце действие <xref:System.Activities.Statements.ForEach%601> используется для прохождения коллекции, возвращаемой действием <xref:System.Activities.Validation.GetParentChain>.</span><span class="sxs-lookup"><span data-stu-id="b049e-111">In the sample, a <xref:System.Activities.Statements.ForEach%601> activity is used to walk through the collection returned by <xref:System.Activities.Validation.GetParentChain>.</span></span> <span data-ttu-id="b049e-112">Тип каждого элемента в коллекции сравнивается с типом результата действия `CreateCountry` (или действия `CreateState`, если проверяется `CreateCity`), а после нахождения соответствия флаг результата устанавливается в `true`.</span><span class="sxs-lookup"><span data-stu-id="b049e-112">For every element in the collection, its type is compared to `CreateCountry` (or `CreateState` if `CreateCity` is being validated), and when a match is found the result flag is set to `true`.</span></span> <span data-ttu-id="b049e-113">Наконец <xref:System.Activities.Validation.AssertValidation> используется для формирования ошибки проверки, если флаг результата установлен в `false`.</span><span class="sxs-lookup"><span data-stu-id="b049e-113">Finally, an <xref:System.Activities.Validation.AssertValidation> is used to generate a validation error if the result flag is set to `false`.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="b049e-114">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="b049e-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="b049e-115">Откройте образец решения ContainmentValidation.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b049e-115">Open the ContainmentValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="b049e-116">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="b049e-116">Build the solution.</span></span>  
  
3.  <span data-ttu-id="b049e-117">Чтобы запустить программу, нажмите сочетание клавиш CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="b049e-117">Press CTRL + F5 to launch the program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b049e-118">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b049e-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b049e-119">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b049e-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b049e-120">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b049e-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b049e-121">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="b049e-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
