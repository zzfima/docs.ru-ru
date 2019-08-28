---
title: Программирование дерева элементов модели
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f2d89cb2a3b0f6167f043148ea793ec1c264a556
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70038174"
---
# <a name="programming-model-item-tree"></a><span data-ttu-id="05bfa-102">Программирование дерева элементов модели</span><span class="sxs-lookup"><span data-stu-id="05bfa-102">Programming Model Item Tree</span></span>
<span data-ttu-id="05bfa-103">В этом образце показано, как <xref:System.Activities.Presentation.Model.ModelItem> перемещаться по дереву с помощью декларативной привязки данных из древовидного представления Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="05bfa-103">This sample demonstrates how to navigate the <xref:System.Activities.Presentation.Model.ModelItem> tree using declarative data binding from the Windows Presentation Foundation (WPF) Tree View.</span></span>

## <a name="sample-details"></a><span data-ttu-id="05bfa-104">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="05bfa-104">Sample Details</span></span>
 <span data-ttu-id="05bfa-105">Дерево <xref:System.Activities.Presentation.Model.ModelItem> является абстракцией, которая используется инфраструктурой [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] для предоставления данных о базовом изменяемом экземпляре.</span><span class="sxs-lookup"><span data-stu-id="05bfa-105">The <xref:System.Activities.Presentation.Model.ModelItem> tree is the abstraction that is used by the [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] infrastructure to expose the data about the underlying instance being edited.</span></span> <span data-ttu-id="05bfa-106">На следующей иллюстрации показаны различные слои инфраструктуры внутри [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05bfa-106">The following illustration is a depiction of the various layers of infrastructure within the [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)].</span></span>

 ![Схема, показывающая архитектуру конструктор рабочих процессов.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <span data-ttu-id="05bfa-108">Элемент <xref:System.Activities.Presentation.Model.ModelItem> состоит из указателя базового значения, а также коллекции объектов <xref:System.Activities.Presentation.Model.ModelProperty>.</span><span class="sxs-lookup"><span data-stu-id="05bfa-108">A <xref:System.Activities.Presentation.Model.ModelItem> consists of a pointer to the underlying value, as well as a collection of <xref:System.Activities.Presentation.Model.ModelProperty> objects.</span></span> <span data-ttu-id="05bfa-109">Объект <xref:System.Activities.Presentation.Model.ModelProperty> в свою очередь включает данные, такие как имя и тип свойства, и указатель значения, который в свою очередь является еще одним элементом <xref:System.Activities.Presentation.Model.ModelItem>.</span><span class="sxs-lookup"><span data-stu-id="05bfa-109">A <xref:System.Activities.Presentation.Model.ModelProperty> object in turn, consists of data such as the name and type of the property and then a pointer to the value, which in turn, is another <xref:System.Activities.Presentation.Model.ModelItem>.</span></span> <span data-ttu-id="05bfa-110">Преобразователь значений используется для манипуляции некоторыми элементами <xref:System.Activities.Presentation.Model.ModelItem>, возвращаемыми свойством <xref:System.Activities.Presentation.Model.ModelProperty>, чтобы они правильно отображались в представлении дерева.</span><span class="sxs-lookup"><span data-stu-id="05bfa-110">A value converter is used to manipulate some of the <xref:System.Activities.Presentation.Model.ModelItem>s returned from a <xref:System.Activities.Presentation.Model.ModelProperty> to make them appear correctly in the tree view.</span></span> <span data-ttu-id="05bfa-111">Далее в образце показано, как императивно программировать с использованием дерева <xref:System.Activities.Presentation.Model.ModelItem> при помощи императивных инструкций, в соответствии со следующим примером.</span><span class="sxs-lookup"><span data-stu-id="05bfa-111">The sample then demonstrates how to imperatively program against the <xref:System.Activities.Presentation.Model.ModelItem> tree using the imperative syntax, as seen in the following example.</span></span>

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="05bfa-112">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="05bfa-112">To use this sample</span></span>

1. <span data-ttu-id="05bfa-113">Откройте решение Программингмоделитемтри. sln в Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="05bfa-113">Open the ProgrammingModelItemTree.sln solution in Visual Studio 2010.</span></span>

2. <span data-ttu-id="05bfa-114">Создайте решение, выбрав пункт **построить решение** в меню **Сборка** .</span><span class="sxs-lookup"><span data-stu-id="05bfa-114">Build the solution by selecting **Build Solution** from the **Build** menu.</span></span>

3. <span data-ttu-id="05bfa-115">Нажмите клавишу F5 для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="05bfa-115">Press F5 to run the application.</span></span> <span data-ttu-id="05bfa-116">Затем отображается форма WPF.</span><span class="sxs-lookup"><span data-stu-id="05bfa-116">The WPF form is then displayed.</span></span>

4. <span data-ttu-id="05bfa-117">Нажмите кнопку **Загрузить WF** , чтобы загрузить <xref:System.Activities.Presentation.Model.ModelItem> и привязать его к представлению в виде дерева.</span><span class="sxs-lookup"><span data-stu-id="05bfa-117">Click the **Load WF** button to load the <xref:System.Activities.Presentation.Model.ModelItem> and bind it to the tree view.</span></span>

5. <span data-ttu-id="05bfa-118">При нажатии кнопки " **изменить дерево элементов модели** " выполняется предыдущий код для добавления элемента в дерево и задания свойства.</span><span class="sxs-lookup"><span data-stu-id="05bfa-118">Clicking the **Change Model Item Tree** button executes the preceding code to add an item into the tree and set a property.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05bfa-119">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="05bfa-119">The samples may already be installed on your computer.</span></span> <span data-ttu-id="05bfa-120">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="05bfa-120">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="05bfa-121">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры.</span><span class="sxs-lookup"><span data-stu-id="05bfa-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05bfa-122">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="05bfa-122">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a><span data-ttu-id="05bfa-123">См. также</span><span class="sxs-lookup"><span data-stu-id="05bfa-123">See also</span></span>

- <xref:System.Windows.Data.IValueConverter>
