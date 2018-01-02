---
title: "Пошаговое руководство. Создание расширяемого приложения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ac4b6fc2ae36d848306178f281cceeeb0654ec03
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="3e6d3-102">Пошаговое руководство. Создание расширяемого приложения</span><span class="sxs-lookup"><span data-stu-id="3e6d3-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="3e6d3-103">В этом пошаговом руководстве описывается создание конвейера надстройки, выполняющий функции простого калькулятора.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="3e6d3-104">Здесь не показаны реальном сценарии; Вместо этого он демонстрирует основные функциональные возможности конвейера и как надстройка может предоставлять службы для узла.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="3e6d3-105">В этом пошаговом руководстве описаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="3e6d3-106">Создание решения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="3e6d3-107">Создание структуры каталогов конвейера.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="3e6d3-108">Создание контракта и представлений.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="3e6d3-109">Создание адаптера на стороне надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="3e6d3-110">Создание адаптера на стороне узла.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="3e6d3-111">Создание узла.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="3e6d3-112">Создание надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="3e6d3-113">Развертывание конвейера.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="3e6d3-114">Запуск основного приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-114">Running the host application.</span></span>  
  
 <span data-ttu-id="3e6d3-115">Этот конвейер передает только сериализуемых типов (<xref:System.Double> и <xref:System.String>), между основным приложением и надстройкой.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="3e6d3-116">Пример, демонстрирующий способы передачи коллекций сложных типов данных см. в разделе [Пошаговое руководство: передача коллекций между узлами и надстройки](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="3e6d3-117">Контракт для этого конвейера определяет модель объекта из четырех арифметических операций: добавить, вычесть, умножить и разделить.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="3e6d3-118">Узел предоставляет надстройки формулу для вычисления, например 2 + 2, и надстройка возвращает результат на узел.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="3e6d3-119">Версия 2 надстройки калькулятора предоставляются дополнительные возможности вычисления и показано управление версиями.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="3e6d3-120">Он описан в [Пошаговое руководство: Включение обратной совместимости, как узел изменений](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e6d3-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="3e6d3-121">Prerequisites</span></span>  
 <span data-ttu-id="3e6d3-122">Для выполнения данного пошагового руководства необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-122">You need the following to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]<span data-ttu-id="3e6d3-123">.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-123">.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="3e6d3-124">Создание решения Visual Studio</span><span class="sxs-lookup"><span data-stu-id="3e6d3-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="3e6d3-125">Используйте решение в [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] проект сегментов конвейера.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-125">Use a solution in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="3e6d3-126">Чтобы создать решение конвейера</span><span class="sxs-lookup"><span data-stu-id="3e6d3-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="3e6d3-127">В [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], создайте новый проект с именем `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-127">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="3e6d3-128">Он должен быть основан на **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-129">Присвойте решению имя `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="3e6d3-130">Создание структуры каталогов конвейера</span><span class="sxs-lookup"><span data-stu-id="3e6d3-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="3e6d3-131">Модель надстроек требуется сборки сегментов конвейера помещается в указанную структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="3e6d3-132">Дополнительные сведения о структуре конвейера см. в разделе [требования к разработке конвейера](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-132">For more information about the pipeline structure, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="3e6d3-133">Чтобы создать структуру каталогов конвейера</span><span class="sxs-lookup"><span data-stu-id="3e6d3-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="3e6d3-134">Создайте папку приложения в любом месте на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="3e6d3-135">В этой папке создайте следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-135">In that folder, create the following structure:</span></span>  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     <span data-ttu-id="3e6d3-136">Нет необходимости размещать структуру папок конвейера в папке приложения; Это делается только для удобства.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="3e6d3-137">На определенном этапе пошагового руководства объясняется, как изменить код, если структура папок конвейера в другом месте.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="3e6d3-138">В разделе описания каталогов конвейера в [требования к разработке конвейера](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e6d3-139">`CalcV2` Папки в этом пошаговом руководстве не используется; он является заполнителем для [Пошаговое руководство: Включение обратной совместимости, как узел изменений](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="3e6d3-140">Создание контракта и представлений</span><span class="sxs-lookup"><span data-stu-id="3e6d3-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="3e6d3-141">Сегмент контракта для этого конвейера определяет `ICalc1Contract` интерфейс, который определяет четыре метода: `add`, `subtract`, `multiply`, и `divide`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="3e6d3-142">Создание контракта</span><span class="sxs-lookup"><span data-stu-id="3e6d3-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="3e6d3-143">В решение Visual Studio, с именем `CalculatorV1`откройте `Calc1Contract` проекта.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="3e6d3-144">В **обозревателе решений**, добавьте ссылки на следующие сборки для `Calc1Contract` проекта:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="3e6d3-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="3e6d3-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="3e6d3-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="3e6d3-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="3e6d3-147">В **обозревателе решений**, исключите класс по умолчанию, который добавляется новый **библиотеки классов** проектов.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="3e6d3-148">В **обозревателе решений**, добавьте новый элемент в проект с помощью **интерфейс** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="3e6d3-149">В **Добавление нового элемента** диалоговом имя интерфейса `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="3e6d3-150">В файле интерфейса добавьте ссылки на пространства имен для <xref:System.AddIn.Contract> и <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="3e6d3-151">Используйте следующий код для завершения этого сегмента контракта.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="3e6d3-152">Обратите внимание, что этот интерфейс должен иметь <xref:System.AddIn.Pipeline.AddInContractAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="3e6d3-153">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="3e6d3-154">Решение не может выполняться, пока заключительную процедуру, но ее построение после каждой процедуры гарантирует, что каждый проект исправления.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="3e6d3-155">Так как представление надстройки и узлом представление надстройки обычно имеют один и тот же код, особенно в первой версии надстройки, можно легко создавать представления в то же время.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="3e6d3-156">Они отличаются только в одном: представление надстройки требует <xref:System.AddIn.Pipeline.AddInBaseAttribute> атрибута, пока хост-представление надстройки не нуждается в атрибутах.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="3e6d3-157">Чтобы создать представление надстройки</span><span class="sxs-lookup"><span data-stu-id="3e6d3-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="3e6d3-158">Добавьте новый проект с именем `Calc1AddInView` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="3e6d3-159">Он должен быть основан на **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-160">В **обозревателе решений**, добавьте ссылку на System.AddIn.dll для `Calc1AddInView` проекта.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="3e6d3-161">В **обозревателе решений**, исключите класс по умолчанию, который добавляется новый **библиотеки классов** проектов и добавить новый элемент в проект с помощью **интерфейс** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="3e6d3-162">В **Добавление нового элемента** диалоговом имя интерфейса `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="3e6d3-163">В файле интерфейса добавьте ссылку на пространство имен <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="3e6d3-164">Используйте следующий код для завершения этого представления надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="3e6d3-165">Обратите внимание, что этот интерфейс должен иметь <xref:System.AddIn.Pipeline.AddInBaseAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="3e6d3-166">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="3e6d3-167">Для создания представления узла надстройки</span><span class="sxs-lookup"><span data-stu-id="3e6d3-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="3e6d3-168">Добавьте новый проект с именем `Calc1HVA` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="3e6d3-169">Он должен быть основан на **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-170">В **обозревателе решений**, исключите класс по умолчанию, который добавляется новый **библиотеки классов** проектов и добавить новый элемент в проект с помощью **интерфейс** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="3e6d3-171">В **Добавление нового элемента** диалоговом имя интерфейса `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="3e6d3-172">В файле интерфейса используйте следующий код для завершения серверное представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="3e6d3-173">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="3e6d3-174">Создание адаптера на стороне надстройки</span><span class="sxs-lookup"><span data-stu-id="3e6d3-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="3e6d3-175">Этот адаптер на стороне надстройки состоит из одного адаптера представление контракт.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="3e6d3-176">Этот сегмент конвейера преобразует типы из представления надстройки в контракт.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="3e6d3-177">В этом конвейере надстройка предоставляет службу на узле, а типы передаются из надстройки узла.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="3e6d3-178">Так как никакие типы не направляются от ведущего приложения надстройки, включают в себя адаптер контракта для просмотра на стороне надстройки в этом конвейере нет.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="3e6d3-179">Чтобы создать адаптер на стороне надстройки</span><span class="sxs-lookup"><span data-stu-id="3e6d3-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="3e6d3-180">Добавьте новый проект с именем `Calc1AddInSideAdapter` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="3e6d3-181">Он должен быть основан на **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-182">В **обозревателе решений**, добавьте ссылки на следующие сборки для `Calc1AddInSideAdapter` проекта:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="3e6d3-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="3e6d3-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="3e6d3-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="3e6d3-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="3e6d3-185">Добавьте ссылки проекта на проекты сегментов конвейера смежные:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="3e6d3-186">Выберите ссылку каждого проекта и в **свойства** задать **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="3e6d3-187">В Visual Basic, используйте **ссылки** вкладке **свойства проекта** для задания **Копировать локально** для **False** для две ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="3e6d3-188">Переименуйте класс по умолчанию проекта `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="3e6d3-189">В файле класса добавьте ссылки на пространства имен для <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="3e6d3-190">В файле класса добавьте ссылки на пространства имен для соседних сегментов: `CalcAddInViews` и `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="3e6d3-191">(В Visual Basic, ссылки на следующие пространства имен `Calc1AddInView.CalcAddInViews` и `Calc1Contract.CalculatorContracts`, если вы отключили пространства имен по умолчанию в проектах Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="3e6d3-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="3e6d3-192">Применить <xref:System.AddIn.Pipeline.AddInAdapterAttribute> атрибут `CalculatorViewToContractAddInSideAdapter` класса, чтобы он определялся как адаптер со стороны надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="3e6d3-193">Сделать `CalculatorViewToContractAddInSideAdapter` наследовать класс <xref:System.AddIn.Pipeline.ContractBase>, который предоставляет реализацию по умолчанию <xref:System.AddIn.Contract.IContract> интерфейса и реализует интерфейс контракта для конвейера, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="3e6d3-194">Добавьте открытый конструктор, принимающий `ICalculator`, кэширует его в закрытом поле и вызывает конструктор базового класса.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="3e6d3-195">Чтобы реализовать члены `ICalc1Contract`, просто вызовите соответствующие элементы из `ICalculator` экземпляр, который передается в конструктор и возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="3e6d3-196">Это адаптирует представление (`ICalculator`) для контракта (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="3e6d3-197">Следующий код показывает завершенный адаптер на стороне надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="3e6d3-198">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="3e6d3-199">Создание адаптера на стороне узла</span><span class="sxs-lookup"><span data-stu-id="3e6d3-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="3e6d3-200">Этот адаптер узла состоит из одного адаптера контракта для просмотра.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="3e6d3-201">Этот сегмент адаптирует контракт для хост-представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="3e6d3-202">В этом конвейере надстройка предоставляет службу, в узел, а также типы потока из надстройки на узел.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="3e6d3-203">Так как никакие типы не направляются от ведущего приложения надстройки, включают в себя представление контракт адаптер нет.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="3e6d3-204">Для управления временем существования, используйте <xref:System.AddIn.Pipeline.ContractHandle> , который необходимо подключить к контракту токен срока существования.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="3e6d3-205">Необходимо сохранить ссылку на этот дескриптор для управления временем жизни для работы.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="3e6d3-206">После применения маркера без дополнительного программирования является обязательным, поскольку система надстройки может удалить объекты, если они больше не используются и сделать их доступными для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="3e6d3-207">Подробнее см. в разделе [Управление жизненным циклом](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-207">For more information, see [Lifetime Management](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="3e6d3-208">Для создания адаптера узла</span><span class="sxs-lookup"><span data-stu-id="3e6d3-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="3e6d3-209">Добавьте новый проект с именем `Calc1HostSideAdapter` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="3e6d3-210">Он должен быть основан на **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-211">В **обозревателе решений**, добавьте ссылки на следующие сборки для `Calc1HostSideAdapter` проекта:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="3e6d3-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="3e6d3-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="3e6d3-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="3e6d3-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="3e6d3-214">Добавьте ссылки проекта на проекты соседних сегментов:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="3e6d3-215">Выберите ссылку каждого проекта и в **свойства** задать **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="3e6d3-216">В Visual Basic, используйте **ссылки** вкладке **свойства проекта** для задания **Копировать локально** для **False** для две ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="3e6d3-217">Переименуйте класс по умолчанию проекта `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="3e6d3-218">В файле класса добавьте ссылки на пространства имен для <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="3e6d3-219">В файле класса добавьте ссылки на пространства имен для соседних сегментов: `CalcHVAs` и `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="3e6d3-220">(В Visual Basic, ссылки на следующие пространства имен `Calc1HVA.CalcHVAs` и `Calc1Contract.CalculatorContracts`, если вы отключили пространства имен по умолчанию в проектах Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="3e6d3-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="3e6d3-221">Применить <xref:System.AddIn.Pipeline.HostAdapterAttribute> атрибут `CalculatorContractToViewHostSideAdapter` класса, чтобы он определялся как адаптер сегмента.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="3e6d3-222">Сделать `CalculatorContractToViewHostSideAdapter` класс реализует интерфейс, представляющий серверное представление надстройки: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="3e6d3-223">Добавьте открытый конструктор, который принимает тип контракта конвейера `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="3e6d3-224">Конструктор должен кэшировать ссылки на контракт.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="3e6d3-225">Необходимо также создать и кэшировать новый <xref:System.AddIn.Pipeline.ContractHandle> для контракта, для управления временем жизни надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3e6d3-226"><xref:System.AddIn.Pipeline.ContractHandle> Крайне важно для управления жизненным циклом.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="3e6d3-227">Если не удалось сохранить ссылку на <xref:System.AddIn.Pipeline.ContractHandle> объекта, сборщик мусора будет восстановить его и конвейера будет завершать работу, если приложение не ожидает его.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="3e6d3-228">Это может привести к ошибкам, которые трудно диагностировать, например <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="3e6d3-229">Завершение работы является неотъемлемым этапом жизненного цикла конвейера, поэтому нет возможности для кода управления временем существования обнаружить, что это условие является ошибкой.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="3e6d3-230">Чтобы реализовать члены `ICalculator`, просто вызовите соответствующие элементы из `ICalc1Contract` экземпляр, который передается в конструктор и возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="3e6d3-231">Это адаптирует контракт (`ICalc1Contract`) в представление (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="3e6d3-232">Следующий код показывает завершенный адаптер на стороне узла.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="3e6d3-233">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="3e6d3-234">Создание узла</span><span class="sxs-lookup"><span data-stu-id="3e6d3-234">Creating the Host</span></span>  
 <span data-ttu-id="3e6d3-235">Основное приложение взаимодействует с надстройкой посредством серверное представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="3e6d3-236">Она использует надстройки обнаружение и активация методы, предоставляемые <xref:System.AddIn.Hosting.AddInStore> и <xref:System.AddIn.Hosting.AddInToken> классы делать следующее:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="3e6d3-237">Обновите кэш данных конвейера и надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="3e6d3-238">Обнаружение надстроек типа представления узла `ICalculator`, корневом каталоге указанного конвейера.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="3e6d3-239">Предложить пользователю указать, что надстройки для использования.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="3e6d3-240">Активация выбранной надстройки в новом домене приложения с выбранным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="3e6d3-241">Запуска пользовательского `RunCalculator` метод, который вызывает методы надстройки в соответствии с хост-представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="3e6d3-242">Для создания узла</span><span class="sxs-lookup"><span data-stu-id="3e6d3-242">To create the host</span></span>  
  
1.  <span data-ttu-id="3e6d3-243">Добавьте новый проект с именем `Calc1Host` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="3e6d3-244">Он должен быть основан на **консольное приложение** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-245">В **обозревателе решений**, добавьте ссылку на сборку System.AddIn.dll `Calc1Host` проекта.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="3e6d3-246">Добавьте ссылку на проект `Calc1HVA` проекта.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="3e6d3-247">Выберите ссылку на проект и в **свойства** задать **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="3e6d3-248">В Visual Basic, используйте **ссылки** вкладке **свойства проекта** для задания **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="3e6d3-249">Переименуйте файл (модуль в Visual Basic) класса `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="3e6d3-250">В Visual Basic, используйте **приложения** вкладке **свойства проекта** диалоговое окно «», чтобы задать **автоматически запускаемый объект** для **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="3e6d3-251">В файле класса или модуля добавьте ссылку на пространство имен <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="3e6d3-252">В файле класса или модуля добавьте ссылку на пространство имен для серверного представления надстройки: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="3e6d3-253">(В Visual Basic — это ссылки на пространство имен `Calc1HVA.CalcHVAs`, если вы отключили пространства имен по умолчанию в проектах Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="3e6d3-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="3e6d3-254">В **обозревателе решений**, выберите решение и из **проекта** меню щелкните **свойства**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="3e6d3-255">В **страницы свойств решения** диалоговое окно, набор **один запускаемый проект** как этот проект основного приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="3e6d3-256">В файле класса или модуля, используйте <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> метод для обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="3e6d3-257">Используйте <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> метод для получения коллекции маркеров и <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> метод, чтобы активировать надстройку.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="3e6d3-258">В следующем коде показано завершение основного приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="3e6d3-259">Данный код предполагает, что структура папок конвейера находится в папке приложения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="3e6d3-260">Если находится в другом месте, измените строку кода, который задает `addInRoot` переменной, чтобы переменная содержит путь к структуре каталогов конвейера.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="3e6d3-261">Код использует `ChooseCalculator` метод для отображения списка маркеров и предложить пользователю выбрать надстройку.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="3e6d3-262">`RunCalculator` Метод запросит у пользователя простые математические выражения, с помощью `Parser` класс и отображаются результаты, возвращенные надстройкой.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="3e6d3-263">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="3e6d3-264">Создание надстройки</span><span class="sxs-lookup"><span data-stu-id="3e6d3-264">Creating the Add-In</span></span>  
 <span data-ttu-id="3e6d3-265">Надстройка реализует методы, указанные в представлении надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="3e6d3-266">Эта надстройка реализует `Add`, `Subtract`, `Multiply`, и `Divide` операции и возвращает результаты на узел.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="3e6d3-267">Чтобы создать надстройку</span><span class="sxs-lookup"><span data-stu-id="3e6d3-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="3e6d3-268">Добавьте новый проект с именем `AddInCalcV1` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="3e6d3-269">Он должен быть основан на **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="3e6d3-270">В **обозревателе решений**, добавьте в проект ссылку на сборку System.AddIn.dll.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="3e6d3-271">Добавьте ссылку на проект `Calc1AddInView` проекта.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="3e6d3-272">Выберите ссылку на проект и в **свойства**, задайте **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="3e6d3-273">В Visual Basic, используйте **ссылки** вкладке **свойства проекта** для задания **Копировать локально** для **False** для ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="3e6d3-274">Переименуйте класс `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="3e6d3-275">В файле класса добавьте ссылку на пространство имен <xref:System.AddIn> и сегмент представления надстройки: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="3e6d3-276">Применить <xref:System.AddIn.AddInAttribute> атрибут `AddInCalcV1` класса, чтобы идентифицировать класс как add-in.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="3e6d3-277">Сделать `AddInCalcV1` класс реализует интерфейс, представляющий представление надстройки: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="3e6d3-278">Реализовать члены `ICalculator` посредством возвращения результатов соответствующих вычислений.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="3e6d3-279">В следующем коде показано завершить надстройку.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="3e6d3-280">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="3e6d3-281">Развертывание конвейера</span><span class="sxs-lookup"><span data-stu-id="3e6d3-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="3e6d3-282">Теперь вы готовы построить и развернуть сегменты надстройки в требуемой структуре каталогов конвейера.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="3e6d3-283">Развертывание сегментов в конвейере</span><span class="sxs-lookup"><span data-stu-id="3e6d3-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="3e6d3-284">Для каждого проекта в решении, используйте **построения** вкладке **свойства проекта** ( **компиляции** вкладки в Visual Basic) для задания значения **выходной путь**  ( **выходной путь построения** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="3e6d3-285">Если имя папки приложения `MyApp`, например, построение проектов будет осуществляться в следующих папках:</span><span class="sxs-lookup"><span data-stu-id="3e6d3-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="3e6d3-286">Проект</span><span class="sxs-lookup"><span data-stu-id="3e6d3-286">Project</span></span>|<span data-ttu-id="3e6d3-287">Путь</span><span class="sxs-lookup"><span data-stu-id="3e6d3-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="3e6d3-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="3e6d3-288">AddInCalcV1</span></span>|<span data-ttu-id="3e6d3-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="3e6d3-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="3e6d3-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="3e6d3-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="3e6d3-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="3e6d3-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="3e6d3-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="3e6d3-292">Calc1AddInView</span></span>|<span data-ttu-id="3e6d3-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="3e6d3-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="3e6d3-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="3e6d3-294">Calc1Contract</span></span>|<span data-ttu-id="3e6d3-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="3e6d3-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="3e6d3-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="3e6d3-296">Calc1Host</span></span>|<span data-ttu-id="3e6d3-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="3e6d3-297">MyApp</span></span>|  
    |<span data-ttu-id="3e6d3-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="3e6d3-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="3e6d3-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="3e6d3-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="3e6d3-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="3e6d3-300">Calc1HVA</span></span>|<span data-ttu-id="3e6d3-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="3e6d3-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="3e6d3-302">Если вы решили разместить структуру папок конвейера в месте, отличном от папки приложения, необходимо изменить путям, показанным в таблице, соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="3e6d3-303">В разделе описания каталогов конвейера в [требования к разработке конвейера](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="3e6d3-304">Выполните сборку решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="3e6d3-305">Проверьте каталоги приложения и конвейера, чтобы убедиться, что сборки были скопированы в соответствующие папки и что нет дополнительных копий сборок были установлены в других папках.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e6d3-306">Если не были изменены **Копировать локально** для **False** для `Calc1AddInView` ссылку в проект `AddInCalcV1` проекта, проблем контекста загрузчика помешает надстройки они находятся.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="3e6d3-307">Сведения о развертывании в конвейер, см. в разделе [требования к разработке конвейера](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="3e6d3-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="3e6d3-308">Запуск основного приложения</span><span class="sxs-lookup"><span data-stu-id="3e6d3-308">Running the Host Application</span></span>  
 <span data-ttu-id="3e6d3-309">Теперь вы готовы запустить узел и взаимодействовать с надстройкой.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="3e6d3-310">Для запуска ведущего приложения</span><span class="sxs-lookup"><span data-stu-id="3e6d3-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="3e6d3-311">В командной строке перейдите в каталог приложения и запустите основное приложение `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="3e6d3-312">Основное приложение находит все доступные надстройки его типа и вам будет предложено выбрать add-in.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="3e6d3-313">Введите **1** только доступные надстройки.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="3e6d3-314">Введите формулу для калькулятора, такие как **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="3e6d3-315">Должно быть пробелов между цифрами и знаком.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="3e6d3-316">Тип **выхода** и нажмите клавишу **ввод** клавишу, чтобы закрыть приложение.</span><span class="sxs-lookup"><span data-stu-id="3e6d3-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e6d3-317">См. также</span><span class="sxs-lookup"><span data-stu-id="3e6d3-317">See Also</span></span>  
 [<span data-ttu-id="3e6d3-318">Пошаговое руководство: Включение обратной совместимости, как изменения узла</span><span class="sxs-lookup"><span data-stu-id="3e6d3-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="3e6d3-319">Пошаговое руководство: Передача коллекций между узлами и надстройки</span><span class="sxs-lookup"><span data-stu-id="3e6d3-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="3e6d3-320">Требования к разработке конвейера</span><span class="sxs-lookup"><span data-stu-id="3e6d3-320">Pipeline Development Requirements</span></span>](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="3e6d3-321">Контракты, представления и адаптеры</span><span class="sxs-lookup"><span data-stu-id="3e6d3-321">Contracts, Views, and Adapters</span></span>](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="3e6d3-322">Разработка конвейера</span><span class="sxs-lookup"><span data-stu-id="3e6d3-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
