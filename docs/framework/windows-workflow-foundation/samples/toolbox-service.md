---
title: "Служба области элементов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 742212d0-445e-41ed-9739-9ee848ce7f1b
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b800f2d250a918ea2b6c49b121c4ca9040b20631
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="toolbox-service"></a><span data-ttu-id="4e8b0-102">Служба области элементов</span><span class="sxs-lookup"><span data-stu-id="4e8b0-102">Toolbox Service</span></span>
<span data-ttu-id="4e8b0-103">Этот образец демонстрирует, как обновлять действия области элементов [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] на базе контекста рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-103">This sample demonstrates how to update the [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] Toolbox activities based on the context of the workflow.</span></span> <span data-ttu-id="4e8b0-104">Образец содержит рабочий процесс, изменяющий содержание области элементов в зависимости от выбранного пользовательского действия.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-104">The sample contains a workflow that changes the toolbox contents based on whether a custom activity is selected.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="4e8b0-105">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="4e8b0-105">Discussion</span></span>  
 <span data-ttu-id="4e8b0-106">В ходе разработки рабочего процесса клиенты обычно выражают пожелание, чтобы область элементов отображалась по-разному в зависимости от контекста.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-106">During workflow authoring, customers generally want their Toolbox to be context sensitive.</span></span> <span data-ttu-id="4e8b0-107">Например, пользователь может захотеть, чтобы в области элементов отображались дополнительные действия, если в рабочий процесс добавляется определенное действие.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-107">For example, the user may want to ensure that the Toolbox shows a few additional activities when a specific activity is added to the workflow.</span></span> <span data-ttu-id="4e8b0-108">При удалении действий из рабочего процесса область элементов должна соответствующим образом прореагировать на это согласно требованиям домена.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-108">If the activities are removed from the workflow, the toolbox should react appropriately based on the domain requirements.</span></span>  
  
 <span data-ttu-id="4e8b0-109">Находясь в повторно размещенном конструкторе рабочих процессов, можно работать с элементом управления области элементов и обеспечить, чтобы узел, основанный на модели изменения рабочего процесса, включал соответствующие изменения в элемент управления области элементов.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-109">In a re-hosted workflow designer, you control the Toolbox control and can ensure that based on the Model changes in the workflow, the host triggers appropriate changes in the Toolbox control.</span></span> <span data-ttu-id="4e8b0-110">Тем не менее в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] пользователь не может контролировать область элементов, поэтому для изменения его содержания требуется специальный интерфейс.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-110">However, in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], the toolbox is not controlled by the user and thus an interface is required to modify its contents.</span></span> <span data-ttu-id="4e8b0-111">Этот интерфейс - `IActivityToolboxService`.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-111">`IActivityToolboxService` is that interface.</span></span>  
  
 <span data-ttu-id="4e8b0-112">API-интерфейс реализует следующие четыре метода.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-112">The API provides the following four methods.</span></span>  
  
```  
public interface IActivityToolboxService   
{   
        void AddCategory(string categoryName);   
        void RemoveCategory(string categoryName);   
        void AddItem(string qualifiedTypeName, string categoryName);   
        void RemoveItem(string qualifiedTypeName, string categoryName);   
        IList<string> EnumCategories();   
        IList<string> EnumItems(string categoryName);   
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4e8b0-113">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="4e8b0-113">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4e8b0-114">Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл решения WorkflowSimulator.sln.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-114">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WorkflowSimulator.sln solution file.</span></span>  
  
2.  <span data-ttu-id="4e8b0-115">Выполните сборку решения, нажав клавиши CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-115">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="4e8b0-116">Откройте файл Workflow.xaml.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-116">Open the Workflow.xaml file.</span></span>  
  
4.  <span data-ttu-id="4e8b0-117">Добавить **CustomActivity** , перетащив его из области элементов.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-117">Add a **CustomActivity** by dragging and dropping it from the toolbox.</span></span> <span data-ttu-id="4e8b0-118">Обратите внимание, что дополнительная область элементов имеет имя: **новая категория WF** с дополнительным действием **назначить**.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-118">Notice that an additional Toolbox category called: **New WF Category** with an additional activity **Assign**.</span></span>  
  
5.  <span data-ttu-id="4e8b0-119">Снимите выбор **CustomActivity** , перетащив на него другое действие.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-119">Now unselect the **CustomActivity** by dragging another activity into it.</span></span>  
  
6.  <span data-ttu-id="4e8b0-120">Элемент **назначить** в категории **новая категория WF** в области элементов будет удален.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-120">The item **Assign** in the category **New WF Category** under Toolbox is now removed.</span></span> <span data-ttu-id="4e8b0-121">Кроме того, поскольку в категории больше не осталось элементов, будет удалена и сама категория.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-121">Also, because there are no more items left in the category, the category is removed as well.</span></span>  
  
7.  <span data-ttu-id="4e8b0-122">Выберите **CustomActivity** еще раз и категорию и **назначить** действие будет добавлено повторно.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-122">Select the **CustomActivity** again and the category and **Assign** activity is added back.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4e8b0-123">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4e8b0-124">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="4e8b0-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4e8b0-125">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4e8b0-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4e8b0-126">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="4e8b0-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\IActivityToolboxService`
