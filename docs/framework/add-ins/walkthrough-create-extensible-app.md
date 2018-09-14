---
title: Пошаговое руководство. Создание расширяемого приложения
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d2aaeaffaf3abbe1e8efcdb57d40e6ae60f89b5
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45591961"
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="96b4c-102">Пошаговое руководство. Создание расширяемого приложения</span><span class="sxs-lookup"><span data-stu-id="96b4c-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="96b4c-103">В этом пошаговом руководстве описывается, как создать конвейер для надстройки, которая выполняет функции простого калькулятора.</span><span class="sxs-lookup"><span data-stu-id="96b4c-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="96b4c-104">Он не демонстрирует реальной ситуации; Вместо этого он демонстрирует основные функциональные возможности конвейера, и как надстройка может предоставлять службы для узла.</span><span class="sxs-lookup"><span data-stu-id="96b4c-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="96b4c-105">В этом пошаговом руководстве описаны следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="96b4c-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="96b4c-106">Создание решения Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="96b4c-107">Создание структуры каталогов конвейера.</span><span class="sxs-lookup"><span data-stu-id="96b4c-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="96b4c-108">Создание контракта и представлений.</span><span class="sxs-lookup"><span data-stu-id="96b4c-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="96b4c-109">Создание адаптера на стороне надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="96b4c-110">Создание адаптера на стороне узла.</span><span class="sxs-lookup"><span data-stu-id="96b4c-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="96b4c-111">Создание основного приложения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="96b4c-112">Создание надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="96b4c-113">Развертывание конвейера.</span><span class="sxs-lookup"><span data-stu-id="96b4c-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="96b4c-114">Запуск основного приложения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-114">Running the host application.</span></span>  
  
 <span data-ttu-id="96b4c-115">Этот конвейер передает только сериализуемые типы (<xref:System.Double> и <xref:System.String>), между узлом и надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="96b4c-116">Пример, в котором показано, как передавать коллекции сложных типов данных, см. в разделе [Пошаговое руководство: передача коллекций между узлами и Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span><span class="sxs-lookup"><span data-stu-id="96b4c-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="96b4c-117">Контракт для этого конвейера определяет модель объекта из четырех арифметических операций: добавить, вычесть, умножить и разделить.</span><span class="sxs-lookup"><span data-stu-id="96b4c-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="96b4c-118">Узел предоставляет надстройки с помощью формулы для вычисления, например 2 + 2, и надстройка возвращает результат к узлу.</span><span class="sxs-lookup"><span data-stu-id="96b4c-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="96b4c-119">Версия 2 надстройки калькулятора предоставляются дополнительные возможности вычисления и показано управление версиями.</span><span class="sxs-lookup"><span data-stu-id="96b4c-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="96b4c-120">Он описан в [Пошаговое руководство: Включение обратной совместимости, как узел изменений](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="96b4c-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="96b4c-121">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="96b4c-121">Prerequisites</span></span>  
 <span data-ttu-id="96b4c-122">Для выполнения данного пошагового руководства необходимо следующее:</span><span class="sxs-lookup"><span data-stu-id="96b4c-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="96b4c-123">Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="96b4c-124">Создание решения Visual Studio</span><span class="sxs-lookup"><span data-stu-id="96b4c-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="96b4c-125">Используйте решение в Visual Studio будут содержаться проекты сегментов конвейера.</span><span class="sxs-lookup"><span data-stu-id="96b4c-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="96b4c-126">Чтобы создать решение конвейера</span><span class="sxs-lookup"><span data-stu-id="96b4c-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="96b4c-127">В Visual Studio создайте новый проект с именем `Calc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="96b4c-128">Основу **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-129">Назовите решение `CalculatorV1`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="96b4c-130">Создание структуры каталогов конвейера</span><span class="sxs-lookup"><span data-stu-id="96b4c-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="96b4c-131">Модель надстроек требуется сборок сегмента конвейера размещены в указанную структуру каталогов.</span><span class="sxs-lookup"><span data-stu-id="96b4c-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="96b4c-132">Дополнительные сведения о структуре конвейера см. в разделе [требования к разработке конвейера](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="96b4c-132">For more information about the pipeline structure, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="96b4c-133">Для создания структуры каталогов конвейера</span><span class="sxs-lookup"><span data-stu-id="96b4c-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="96b4c-134">Создайте папку приложения в любом месте на компьютере.</span><span class="sxs-lookup"><span data-stu-id="96b4c-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="96b4c-135">В этой папке создайте следующую структуру:</span><span class="sxs-lookup"><span data-stu-id="96b4c-135">In that folder, create the following structure:</span></span>  
  
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
  
     <span data-ttu-id="96b4c-136">Нет необходимости размещать структуру папок конвейера в папке приложения; Это делается только для удобства.</span><span class="sxs-lookup"><span data-stu-id="96b4c-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="96b4c-137">На определенном этапе пошагового руководства объясняется, как изменения кода в том случае, если используется структура папок конвейера в другом месте.</span><span class="sxs-lookup"><span data-stu-id="96b4c-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="96b4c-138">См. в обсуждении требований каталогов конвейера в [требования к разработке конвейера](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="96b4c-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96b4c-139">`CalcV2` Папку в этом пошаговом руководстве не используется; он является заполнителем для [Пошаговое руководство: Включение обратной совместимости, как узел изменений](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span><span class="sxs-lookup"><span data-stu-id="96b4c-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="96b4c-140">Создание контракта и представлений</span><span class="sxs-lookup"><span data-stu-id="96b4c-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="96b4c-141">Определяет сегмент контракта для этого конвейера `ICalc1Contract` интерфейс, который определяет четыре метода: `add`, `subtract`, `multiply`, и `divide`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="96b4c-142">Создание контракта</span><span class="sxs-lookup"><span data-stu-id="96b4c-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="96b4c-143">В решении Visual Studio с именем `CalculatorV1`откройте `Calc1Contract` проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="96b4c-144">В **обозревателе решений**, добавьте ссылки на следующие сборки `Calc1Contract` проекта:</span><span class="sxs-lookup"><span data-stu-id="96b4c-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="96b4c-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="96b4c-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="96b4c-147">В **обозревателе решений**, исключите класс по умолчанию, который добавляется новое **библиотеки классов** проектов.</span><span class="sxs-lookup"><span data-stu-id="96b4c-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="96b4c-148">В **обозревателе решений**, добавьте новый элемент в проект с помощью **интерфейс** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="96b4c-149">В **Добавление нового элемента** диалоговом окне имя интерфейса `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="96b4c-150">В файле интерфейса добавьте ссылки на пространства имен для <xref:System.AddIn.Contract> и <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="96b4c-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="96b4c-151">Используйте следующий код, чтобы завершить этот сегмент контракта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="96b4c-152">Обратите внимание, что этот интерфейс должен иметь <xref:System.AddIn.Pipeline.AddInContractAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="96b4c-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="96b4c-153">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="96b4c-154">Решение не может выполняться, пока последняя процедура, но ее построение после каждой процедуры гарантирует, что каждый проект исправления.</span><span class="sxs-lookup"><span data-stu-id="96b4c-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="96b4c-155">Так как представление надстройки и узлом представление надстройки обычно имеют один и тот же код, особенно в первой версии надстройки, вы можете легко создавать представления в то же время.</span><span class="sxs-lookup"><span data-stu-id="96b4c-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="96b4c-156">Они отличаются только одним из факторов: требуется представление надстройки <xref:System.AddIn.Pipeline.AddInBaseAttribute> атрибут, хотя серверное представление надстройки не требует какие-либо атрибуты.</span><span class="sxs-lookup"><span data-stu-id="96b4c-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="96b4c-157">Создание представления "надстройки"</span><span class="sxs-lookup"><span data-stu-id="96b4c-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="96b4c-158">Добавление нового проекта с именем `Calc1AddInView` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="96b4c-159">Основу **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-160">В **обозревателе решений**, добавьте ссылку на System.AddIn.dll для `Calc1AddInView` проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="96b4c-161">В **обозревателе решений**, исключите класс по умолчанию, который добавляется новое **библиотеки классов** проектов и добавить новый элемент в проект с помощью **интерфейс** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="96b4c-162">В **Добавление нового элемента** диалоговом окне имя интерфейса `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="96b4c-163">В файле интерфейса добавьте ссылку на пространство имен <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="96b4c-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="96b4c-164">Используйте следующий код для завершения этого представления надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="96b4c-165">Обратите внимание, что этот интерфейс должен иметь <xref:System.AddIn.Pipeline.AddInBaseAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="96b4c-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="96b4c-166">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="96b4c-167">Чтобы создать серверное представление надстройки</span><span class="sxs-lookup"><span data-stu-id="96b4c-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="96b4c-168">Добавление нового проекта с именем `Calc1HVA` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="96b4c-169">Основу **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-170">В **обозревателе решений**, исключите класс по умолчанию, который добавляется новое **библиотеки классов** проектов и добавить новый элемент в проект с помощью **интерфейс** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="96b4c-171">В **Добавление нового элемента** диалоговом окне имя интерфейса `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="96b4c-172">В файле интерфейса используйте следующий код для завершения серверное представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="96b4c-173">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="96b4c-174">Создание адаптера на стороне надстройки</span><span class="sxs-lookup"><span data-stu-id="96b4c-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="96b4c-175">Этот адаптер на стороне надстройки состоит из одного адаптера представление контракт.</span><span class="sxs-lookup"><span data-stu-id="96b4c-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="96b4c-176">Этот сегмент конвейера преобразует типы из представления надстройки в контракт.</span><span class="sxs-lookup"><span data-stu-id="96b4c-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="96b4c-177">В этом конвейере надстройка предоставляет службу для размещения и типы направляются из надстройки к узлу.</span><span class="sxs-lookup"><span data-stu-id="96b4c-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="96b4c-178">Так как никакие типы не направляются от ведущего приложения надстройки, у вас нет необходимости включать контракт представление адаптер со стороны надстройки этот конвейер.</span><span class="sxs-lookup"><span data-stu-id="96b4c-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="96b4c-179">Чтобы создать адаптер на стороне надстройки</span><span class="sxs-lookup"><span data-stu-id="96b4c-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="96b4c-180">Добавление нового проекта с именем `Calc1AddInSideAdapter` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="96b4c-181">Основу **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-182">В **обозревателе решений**, добавьте ссылки на следующие сборки `Calc1AddInSideAdapter` проекта:</span><span class="sxs-lookup"><span data-stu-id="96b4c-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="96b4c-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="96b4c-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="96b4c-185">Добавьте ссылки проекта на проекты прилегающих сегментов конвейера:</span><span class="sxs-lookup"><span data-stu-id="96b4c-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="96b4c-186">Выберите ссылку каждого проекта и в **свойства** задать **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="96b4c-187">В Visual Basic, использовать **ссылки** вкладке **свойства проекта** присвоить **Копировать локально** для **False** для двух ссылки проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="96b4c-188">Переименуйте класс по умолчанию проекта `CalculatorViewToContractAddInSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="96b4c-189">В файле класса добавьте ссылки на пространства имен для <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="96b4c-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="96b4c-190">В файле класса добавьте ссылки на пространства имен для соседних сегментов: `CalcAddInViews` и `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="96b4c-191">(В Visual Basic, эти ссылки на пространства имен являются `Calc1AddInView.CalcAddInViews` и `Calc1Contract.CalculatorContracts`, если вы не отключали функцию пространства имен по умолчанию в проектах Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="96b4c-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="96b4c-192">Применить <xref:System.AddIn.Pipeline.AddInAdapterAttribute> атрибут `CalculatorViewToContractAddInSideAdapter` класса, чтобы он определялся как адаптер на стороне надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="96b4c-193">Сделать `CalculatorViewToContractAddInSideAdapter` наследовать класс <xref:System.AddIn.Pipeline.ContractBase>, который предоставляет реализацию по умолчанию <xref:System.AddIn.Contract.IContract> интерфейс и реализовать интерфейс контракта для конвейера, `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="96b4c-194">Добавьте открытый конструктор, принимающий `ICalculator`, кэширует его в скрытом поле и вызывает конструктор базового класса.</span><span class="sxs-lookup"><span data-stu-id="96b4c-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="96b4c-195">Чтобы реализовать члены `ICalc1Contract`, просто вызовите соответствующими членами объекта `ICalculator` экземпляр, который передается в конструктор и возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="96b4c-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="96b4c-196">Это адаптирует представление (`ICalculator`) к контракту (`ICalc1Contract`).</span><span class="sxs-lookup"><span data-stu-id="96b4c-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="96b4c-197">Приведенный ниже показан завершенный адаптер на стороне надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="96b4c-198">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="96b4c-199">Создание адаптера на стороне узла</span><span class="sxs-lookup"><span data-stu-id="96b4c-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="96b4c-200">Этот адаптер состоит из одного адаптера контракт представление.</span><span class="sxs-lookup"><span data-stu-id="96b4c-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="96b4c-201">Этот сегмент адаптирует контракт для серверное представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="96b4c-202">В этом конвейере надстройка предоставляет службу, на узел и последовательности типов из надстройки к узлу.</span><span class="sxs-lookup"><span data-stu-id="96b4c-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="96b4c-203">Так как никакие типы не направляются от ведущего приложения надстройки, у вас нет для включения адаптера представление контракт.</span><span class="sxs-lookup"><span data-stu-id="96b4c-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="96b4c-204">Для реализации управления жизненным циклом, используйте <xref:System.AddIn.Pipeline.ContractHandle> объект необходимо подключить маркер времени жизни на контракте.</span><span class="sxs-lookup"><span data-stu-id="96b4c-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="96b4c-205">Необходимо хранить ссылку на этот дескриптор в порядке для управления жизненным циклом для работы.</span><span class="sxs-lookup"><span data-stu-id="96b4c-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="96b4c-206">После применения маркера без дополнительного программирования не требуется, поскольку система надстройки может удалить объекты, если они больше не используются и сделать их доступными для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="96b4c-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="96b4c-207">Дополнительные сведения см. в разделе [управления жизненным циклом](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span><span class="sxs-lookup"><span data-stu-id="96b4c-207">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="96b4c-208">Чтобы создать адаптер на стороне узла</span><span class="sxs-lookup"><span data-stu-id="96b4c-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="96b4c-209">Добавление нового проекта с именем `Calc1HostSideAdapter` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="96b4c-210">Основу **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-211">В **обозревателе решений**, добавьте ссылки на следующие сборки `Calc1HostSideAdapter` проекта:</span><span class="sxs-lookup"><span data-stu-id="96b4c-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="96b4c-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="96b4c-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="96b4c-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="96b4c-214">Добавление ссылок на проект в проекты прилегающих сегментов:</span><span class="sxs-lookup"><span data-stu-id="96b4c-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="96b4c-215">Выберите ссылку каждого проекта и в **свойства** задать **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="96b4c-216">В Visual Basic, использовать **ссылки** вкладке **свойства проекта** присвоить **Копировать локально** для **False** для двух ссылки проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="96b4c-217">Переименуйте класс по умолчанию проекта `CalculatorContractToViewHostSideAdapter`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="96b4c-218">В файле класса добавьте ссылки на пространства имен для <xref:System.AddIn.Pipeline>.</span><span class="sxs-lookup"><span data-stu-id="96b4c-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="96b4c-219">В файле класса добавьте ссылки на пространства имен для соседних сегментов: `CalcHVAs` и `CalculatorContracts`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="96b4c-220">(В Visual Basic, эти ссылки на пространства имен являются `Calc1HVA.CalcHVAs` и `Calc1Contract.CalculatorContracts`, если вы не отключали функцию пространства имен по умолчанию в проектах Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="96b4c-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="96b4c-221">Применить <xref:System.AddIn.Pipeline.HostAdapterAttribute> атрибут `CalculatorContractToViewHostSideAdapter` класса, чтобы он определялся как сегмент адаптера узла.</span><span class="sxs-lookup"><span data-stu-id="96b4c-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="96b4c-222">Сделать `CalculatorContractToViewHostSideAdapter` класс реализует интерфейс, представляющий серверное представление надстройки: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="96b4c-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="96b4c-223">Добавьте открытый конструктор, который принимает тип контракта конвейера `ICalc1Contract`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="96b4c-224">Конструктор должен кэшировать ссылку на контракт.</span><span class="sxs-lookup"><span data-stu-id="96b4c-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="96b4c-225">Необходимо также создать и кэшировать новый <xref:System.AddIn.Pipeline.ContractHandle> для контракта, для управления временем жизни надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="96b4c-226"><xref:System.AddIn.Pipeline.ContractHandle> Является критически важным для управления жизненным циклом.</span><span class="sxs-lookup"><span data-stu-id="96b4c-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="96b4c-227">Если не сохранить ссылку на <xref:System.AddIn.Pipeline.ContractHandle> объекта, сборщик мусора освободит его, а конвейер завершит работу, когда приложение не ожидает ее.</span><span class="sxs-lookup"><span data-stu-id="96b4c-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="96b4c-228">Это может привести к ошибкам, которые трудно диагностировать, например <xref:System.AppDomainUnloadedException>.</span><span class="sxs-lookup"><span data-stu-id="96b4c-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="96b4c-229">Завершение работы является неотъемлемым этапом работы конвейера, поэтому нет способа для кода управления временем существования обнаружить, что это состояние возникает ошибка.</span><span class="sxs-lookup"><span data-stu-id="96b4c-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="96b4c-230">Чтобы реализовать члены `ICalculator`, просто вызовите соответствующими членами объекта `ICalc1Contract` экземпляр, который передается в конструктор и возвращает результаты.</span><span class="sxs-lookup"><span data-stu-id="96b4c-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="96b4c-231">Это адаптирует контракт (`ICalc1Contract`) в представление (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="96b4c-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="96b4c-232">Приведенный ниже показан завершенный адаптер на стороне узла.</span><span class="sxs-lookup"><span data-stu-id="96b4c-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="96b4c-233">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="96b4c-234">Создание основного приложения</span><span class="sxs-lookup"><span data-stu-id="96b4c-234">Creating the Host</span></span>  
 <span data-ttu-id="96b4c-235">Ведущее приложение взаимодействует с надстройкой через серверное представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="96b4c-236">Он использует, чтобы добавить в методы обнаружения и активации предоставляемых <xref:System.AddIn.Hosting.AddInStore> и <xref:System.AddIn.Hosting.AddInToken> классы для следующих целей:</span><span class="sxs-lookup"><span data-stu-id="96b4c-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="96b4c-237">Обновите кэш данных конвейера и надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="96b4c-238">Поиск надстроек типа представления узла `ICalculator`, в корневом каталоге указанного конвейера.</span><span class="sxs-lookup"><span data-stu-id="96b4c-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="96b4c-239">Запрос, чтобы пользователь указал, что надстройка для использования.</span><span class="sxs-lookup"><span data-stu-id="96b4c-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="96b4c-240">Активация выбранной надстройки в новом домене приложения с выбранным уровнем доверия.</span><span class="sxs-lookup"><span data-stu-id="96b4c-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="96b4c-241">Запуска специального `RunCalculator` метод, который вызывает методы add в соответствии с серверное представление надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="96b4c-242">Чтобы создать узел</span><span class="sxs-lookup"><span data-stu-id="96b4c-242">To create the host</span></span>  
  
1.  <span data-ttu-id="96b4c-243">Добавление нового проекта с именем `Calc1Host` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="96b4c-244">Основу **консольное приложение** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-245">В **обозревателе решений**, добавьте ссылку на сборку System.AddIn.dll `Calc1Host` проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="96b4c-246">Добавьте в проект ссылку на `Calc1HVA` проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="96b4c-247">Выберите ссылку на проект, а затем в **свойства** задать **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="96b4c-248">В Visual Basic, использовать **ссылки** вкладке **свойства проекта** присвоить **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="96b4c-249">Переименуйте файл (модуль в Visual Basic) класса `MathHost1`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="96b4c-250">В Visual Basic, использовать **приложения** вкладке **свойства проекта** диалоговое окно, чтобы задать **автоматически запускаемый объект** для **Sub Main**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="96b4c-251">В файле класса или модуля, добавьте ссылку на пространство имен <xref:System.AddIn.Hosting>.</span><span class="sxs-lookup"><span data-stu-id="96b4c-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="96b4c-252">В файле класса или модуля, добавьте ссылку на пространство имен для серверного представления надстройки: `CalcHVAs`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="96b4c-253">(В Visual Basic — это ссылка на пространство имен `Calc1HVA.CalcHVAs`, если вы не отключали функцию пространства имен по умолчанию в проектах Visual Basic.)</span><span class="sxs-lookup"><span data-stu-id="96b4c-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="96b4c-254">В **обозревателе решений**, выберите решение и из **проекта** меню выберите команду **свойства**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="96b4c-255">В **страницы свойств решения** диалоговом окне set **один запускаемый проект** быть этот проект ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="96b4c-256">В файле класса или модуля, используйте <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> метод для обновления кэша.</span><span class="sxs-lookup"><span data-stu-id="96b4c-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="96b4c-257">Используйте <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> метод для получения коллекции маркеров и <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> метод для активации надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="96b4c-258">В следующем коде показано завершение основного приложения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="96b4c-259">Этот код предполагает, что структура папок конвейера находится в папке приложения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="96b4c-260">Если находится в другом месте, измените строку кода, который задает `addInRoot` переменной, таким образом, чтобы переменная содержит путь к структуре каталогов конвейера.</span><span class="sxs-lookup"><span data-stu-id="96b4c-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="96b4c-261">Код использует `ChooseCalculator` метод для отображения списка токенов и предлагать пользователю выбрать надстройку.</span><span class="sxs-lookup"><span data-stu-id="96b4c-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="96b4c-262">`RunCalculator` Метод запрашивает у пользователя простые математические выражения, с помощью `Parser` класс и отображаются результаты, возвращенные надстройкой.</span><span class="sxs-lookup"><span data-stu-id="96b4c-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="96b4c-263">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="96b4c-264">Создание надстройки</span><span class="sxs-lookup"><span data-stu-id="96b4c-264">Creating the Add-In</span></span>  
 <span data-ttu-id="96b4c-265">Надстройка реализует методы, указанные представления надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="96b4c-266">Эта надстройка реализует `Add`, `Subtract`, `Multiply`, и `Divide` операции и возвращает результаты на узел.</span><span class="sxs-lookup"><span data-stu-id="96b4c-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="96b4c-267">Чтобы создать надстройку</span><span class="sxs-lookup"><span data-stu-id="96b4c-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="96b4c-268">Добавление нового проекта с именем `AddInCalcV1` для `CalculatorV1` решения.</span><span class="sxs-lookup"><span data-stu-id="96b4c-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="96b4c-269">Основу **библиотеки классов** шаблона.</span><span class="sxs-lookup"><span data-stu-id="96b4c-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="96b4c-270">В **обозревателе решений**, добавьте в проект ссылку на сборку System.AddIn.dll.</span><span class="sxs-lookup"><span data-stu-id="96b4c-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="96b4c-271">Добавьте в проект ссылку на `Calc1AddInView` проекта.</span><span class="sxs-lookup"><span data-stu-id="96b4c-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="96b4c-272">Выберите ссылку на проект, а затем в **свойства**, задайте **Копировать локально** для **False**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="96b4c-273">В Visual Basic, использовать **ссылки** вкладке **свойства проекта** присвоить **Копировать локально** для **False** для ссылки на проект.</span><span class="sxs-lookup"><span data-stu-id="96b4c-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="96b4c-274">Переименуйте класс `AddInCalcV1`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="96b4c-275">В файле класса добавьте ссылку на пространство имен <xref:System.AddIn> и сегмент представления надстройки: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="96b4c-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="96b4c-276">Применить <xref:System.AddIn.AddInAttribute> атрибут `AddInCalcV1` класса, чтобы идентифицировать класс как надстройку.</span><span class="sxs-lookup"><span data-stu-id="96b4c-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="96b4c-277">Сделать `AddInCalcV1` класс реализует интерфейс, представляющий представление надстройки: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="96b4c-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="96b4c-278">Реализовать члены `ICalculator` возвращаются результаты соответствующих вычислений.</span><span class="sxs-lookup"><span data-stu-id="96b4c-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="96b4c-279">В следующем коде показано законченная надстройка.</span><span class="sxs-lookup"><span data-stu-id="96b4c-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="96b4c-280">При необходимости создайте решение Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="96b4c-281">Развертывание конвейера</span><span class="sxs-lookup"><span data-stu-id="96b4c-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="96b4c-282">Теперь вы готовы для создания и развертывания в структуре каталогов конвейера требуется сегменты надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="96b4c-283">Чтобы развернуть сегменты в конвейере</span><span class="sxs-lookup"><span data-stu-id="96b4c-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="96b4c-284">Для каждого проекта в решении, используйте **построения** вкладке **свойства проекта** ( **компиляции** вкладке в Visual Basic) для задания значения **выходной путь**  ( **выходной путь построения** в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="96b4c-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="96b4c-285">Если имя папки приложения `MyApp`, к примеру, построение проектов будет осуществляться в следующих папках:</span><span class="sxs-lookup"><span data-stu-id="96b4c-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="96b4c-286">Проект</span><span class="sxs-lookup"><span data-stu-id="96b4c-286">Project</span></span>|<span data-ttu-id="96b4c-287">Путь</span><span class="sxs-lookup"><span data-stu-id="96b4c-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="96b4c-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="96b4c-288">AddInCalcV1</span></span>|<span data-ttu-id="96b4c-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="96b4c-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="96b4c-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="96b4c-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="96b4c-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="96b4c-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="96b4c-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="96b4c-292">Calc1AddInView</span></span>|<span data-ttu-id="96b4c-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="96b4c-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="96b4c-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="96b4c-294">Calc1Contract</span></span>|<span data-ttu-id="96b4c-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="96b4c-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="96b4c-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="96b4c-296">Calc1Host</span></span>|<span data-ttu-id="96b4c-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="96b4c-297">MyApp</span></span>|  
    |<span data-ttu-id="96b4c-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="96b4c-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="96b4c-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="96b4c-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="96b4c-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="96b4c-300">Calc1HVA</span></span>|<span data-ttu-id="96b4c-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="96b4c-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="96b4c-302">Если вы решили разместить структуру папок конвейера в папке, отличной от папки приложения, необходимо изменить пути, приведенные в таблице, соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="96b4c-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="96b4c-303">См. в обсуждении требований каталогов конвейера в [требования к разработке конвейера](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="96b4c-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="96b4c-304">Выполните сборку решения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="96b4c-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="96b4c-305">Проверьте каталоги приложения и конвейера, чтобы убедиться, что сборки были скопированы в соответствующие папки и что нет дополнительных копий сборок установлены в других папках.</span><span class="sxs-lookup"><span data-stu-id="96b4c-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96b4c-306">Если вы не изменяли **Копировать локально** для **False** для `Calc1AddInView` ссылку на в проект `AddInCalcV1` проекта, проблемы контекст загрузчика будет препятствовать надстройки, чтобы искать его.</span><span class="sxs-lookup"><span data-stu-id="96b4c-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="96b4c-307">Сведения о развертывании в конвейер, см. в разделе [требования к разработке конвейера](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span><span class="sxs-lookup"><span data-stu-id="96b4c-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="96b4c-308">Запуск основного приложения</span><span class="sxs-lookup"><span data-stu-id="96b4c-308">Running the Host Application</span></span>  
 <span data-ttu-id="96b4c-309">Теперь вы готовы запустить узел и взаимодействовать с надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="96b4c-310">Для запуска ведущего приложения</span><span class="sxs-lookup"><span data-stu-id="96b4c-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="96b4c-311">В командной строке перейдите в каталог приложения и запустите ведущим приложением, `Calc1Host.exe`.</span><span class="sxs-lookup"><span data-stu-id="96b4c-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="96b4c-312">Узел находит все доступные надстройки его типа и вам будет предложено выбрать надстройку.</span><span class="sxs-lookup"><span data-stu-id="96b4c-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="96b4c-313">Введите **1** только доступные надстройки.</span><span class="sxs-lookup"><span data-stu-id="96b4c-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="96b4c-314">Введите формулу для калькулятора, такие как **2 + 2**.</span><span class="sxs-lookup"><span data-stu-id="96b4c-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="96b4c-315">Должно быть пробелов между номером и оператора.</span><span class="sxs-lookup"><span data-stu-id="96b4c-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="96b4c-316">Тип **выйти из** и нажмите клавишу **ввод** клавишу, чтобы закрыть приложение.</span><span class="sxs-lookup"><span data-stu-id="96b4c-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b4c-317">См. также</span><span class="sxs-lookup"><span data-stu-id="96b4c-317">See Also</span></span>  
 [<span data-ttu-id="96b4c-318">Пошаговое руководство: Включение обратной совместимости при изменении основного приложения</span><span class="sxs-lookup"><span data-stu-id="96b4c-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="96b4c-319">Пошаговое руководство: Передача коллекций между узлами и надстройки</span><span class="sxs-lookup"><span data-stu-id="96b4c-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="96b4c-320">Требования к разработке конвейера</span><span class="sxs-lookup"><span data-stu-id="96b4c-320">Pipeline Development Requirements</span></span>](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="96b4c-321">Контракты, представления и адаптеры</span><span class="sxs-lookup"><span data-stu-id="96b4c-321">Contracts, Views, and Adapters</span></span>](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="96b4c-322">Разработка конвейера</span><span class="sxs-lookup"><span data-stu-id="96b4c-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
