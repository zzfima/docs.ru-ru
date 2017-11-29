---
title: "Программирование дерева элементов модели"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 18de9d7f9cedc40a6c143a4dae5567c9acf2cf88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="506b4-102">Программирование дерева элементов модели</span><span class="sxs-lookup"><span data-stu-id="506b4-102">Programming Model Item Tree</span></span>
<span data-ttu-id="506b4-103">В этом образце показано, как переходить по дереву <xref:System.Activities.Presentation.Model.ModelItem>, используя привязку декларативных данных из представления дерева [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="506b4-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] Tree View.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="506b4-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="506b4-104">Sample Details</span></span>  
 <span data-ttu-id="506b4-105">Дерево <xref:System.Activities.Presentation.Model.ModelItem> является абстракцией, которая используется инфраструктурой [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] для предоставления данных о базовом изменяемом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="506b4-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="506b4-106">На следующей иллюстрации показаны различные слои инфраструктуры внутри [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="506b4-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>  
  
 <span data-ttu-id="506b4-107">![Архитектура конструктора рабочих процессов](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")</span><span class="sxs-lookup"><span data-stu-id="506b4-107">![Workflow Designer Architecture](../../../../docs/framework/windows-workflow-foundation/samples/media/workflowdesignerarch.JPG "WorkflowDesignerArch")</span></span>  
  
 <span data-ttu-id="506b4-108">Элемент <xref:System.Activities.Presentation.Model.ModelItem> состоит из указателя базового значения, а также коллекции объектов <xref:System.Activities.Presentation.Model.ModelProperty>.</span><span class="sxs-lookup"><span data-stu-id="506b4-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="506b4-109">Объект <xref:System.Activities.Presentation.Model.ModelProperty> в свою очередь включает данные, такие как имя и тип свойства, и указатель значения, который в свою очередь является еще одним элементом <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="506b4-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="506b4-110">Преобразователь значений используется для манипуляции некоторыми элементами <xref:System.Activities.Presentation.Model.ModelItem>, возвращаемыми свойством <xref:System.Activities.Presentation.Model.ModelProperty>, чтобы они правильно отображались в представлении дерева.</span><span class="sxs-lookup"><span data-stu-id="506b4-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="506b4-111">Далее в образце показано, как императивно программировать с использованием дерева <xref:System.Activities.Presentation.Model.ModelItem> при помощи императивных инструкций, в соответствии со следующим примером.</span><span class="sxs-lookup"><span data-stu-id="506b4-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>  
  
```csharp  
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;  
ModelProperty mp = mi.Properties["Activities"];  
mp.Collection.Add(new Persist());  
ModelItem justAdded = mp.Collection.Last();  
justAdded.Properties["DisplayName"].SetValue("new name");  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="506b4-112">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="506b4-112">To use this sample</span></span>  
  
1.  <span data-ttu-id="506b4-113">Откройте решение ProgrammingModelItemTree.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="506b4-113">Open the ProgrammingModelItemTree.sln solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="506b4-114">Постройте решение, выбрав **построить решение** из **построения** меню.</span><span class="sxs-lookup"><span data-stu-id="506b4-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>  
  
3.  <span data-ttu-id="506b4-115">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="506b4-115">Press F5 to run the application.</span></span> <span data-ttu-id="506b4-116">Будет показана форма [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="506b4-116">The [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] form is then displayed.</span></span>  
  
4.  <span data-ttu-id="506b4-117">Нажмите кнопку **загрузить WF** кнопку, чтобы загрузить <xref:System.Activities.Presentation.Model.ModelItem> и привязать его к представлению дерева.</span><span class="sxs-lookup"><span data-stu-id="506b4-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>  
  
5.  <span data-ttu-id="506b4-118">Щелкнув **изменить дерево элементов модели** кнопку выполняется предшествующий код, чтобы добавить элемент в дерево и задает свойство.</span><span class="sxs-lookup"><span data-stu-id="506b4-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="506b4-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="506b4-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="506b4-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="506b4-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="506b4-121">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="506b4-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="506b4-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="506b4-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="506b4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="506b4-123">See Also</span></span>  
 <xref:System.Windows.Data.IValueConverter>
