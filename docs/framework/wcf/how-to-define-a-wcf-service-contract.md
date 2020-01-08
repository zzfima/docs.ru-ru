---
title: Учебник. определение контракта службы Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 49526808a65b68c6df734bd7f3e76eff1e4a6bc5
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338296"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="ffd8b-102">Учебник. определение контракта службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="ffd8b-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="ffd8b-103">В этом руководстве описывается первая из пяти задач, необходимых для создания приложения Basic Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="ffd8b-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ffd8b-104">Общие сведения о учебниках см. в разделе [учебник. Начало работы с Windows Communication Foundation приложениями](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="ffd8b-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="ffd8b-105">При создании службы WCF первая задача заключается в определении контракта службы.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="ffd8b-106">В контракте службы указаны операции, поддерживаемые службой.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="ffd8b-107">Операцию можно представлять себе как метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="ffd8b-108">Контракты служб создаются путем определения интерфейса C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="ffd8b-109">Интерфейс имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="ffd8b-110">Каждый метод в интерфейсе соответствует определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="ffd8b-111">Для каждого интерфейса необходимо применить атрибут <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="ffd8b-112">Для каждой операции или метода необходимо применить атрибут <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="ffd8b-113">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="ffd8b-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ffd8b-114">Создайте проект **библиотеки служб WCF** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="ffd8b-115">Определите интерфейс контракта службы.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="ffd8b-116">Создание проекта библиотеки службы WCF и определение интерфейса контракта службы</span><span class="sxs-lookup"><span data-stu-id="ffd8b-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="ffd8b-117">Откройте Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="ffd8b-118">Для этого выберите программу Visual Studio в меню **Пуск** , а затем в контекстном меню выберите пункт **больше** > **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="ffd8b-119">Создайте проект **библиотеки служб WCF** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="ffd8b-120">В меню **Файл** выберите **Создать**  > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="ffd8b-121">В диалоговом окне **Новый проект** в левой части разверните узел  **C# визуальный** элемент или **Visual Basic**, а затем выберите категорию **WCF** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="ffd8b-122">Visual Studio отображает список шаблонов проектов в центральной части окна.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="ffd8b-123">Выберите **библиотеку служб WCF**.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="ffd8b-124">Если вы не видите категорию шаблона проекта **WCF** , может потребоваться установить компонент **Windows Communication Foundation** Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="ffd8b-125">В диалоговом окне **Новый проект** выберите ссылку **открыть Visual Studio Installer** в левой части.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="ffd8b-126">Перейдите на вкладку **отдельные компоненты** , а затем найдите и выберите **Windows Communication Foundation** в категории **действия разработки** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="ffd8b-127">Нажмите кнопку **изменить** , чтобы начать установку компонента.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="ffd8b-128">В нижнем разделе окна введите *жеттингстартедлиб* в качестве **имени** и *GettingStarted* в качестве **имени решения**.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="ffd8b-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-129">Select **OK**.</span></span>

      <span data-ttu-id="ffd8b-130">Visual Studio создаст проект с тремя файлами: *IService1.CS* (или *IService1. vb* для Visual Basic проекта), *Service1.CS* (или *Service1. vb* для Visual Basic проекта) и *app. config*. Visual Studio определяет эти файлы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ffd8b-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="ffd8b-131">Файл *IService1* содержит определение контракта службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="ffd8b-132">Файл *Service1* содержит реализацию по умолчанию контракта службы.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="ffd8b-133">Файл *app. config* содержит сведения о конфигурации, необходимые для загрузки службы по умолчанию с помощью средства размещения службы WCF Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="ffd8b-134">Дополнительные сведения о средстве размещения службы WCF см. в разделе [узел службы WCF (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="ffd8b-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="ffd8b-135">Если вы установили Visual Studio с параметрами среды разработчика Visual Basic, решение может быть скрыто.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="ffd8b-136">В этом случае выберите пункт **Параметры** в меню **Сервис** , а затем выберите **проекты и решения** > **Общие** в окне **Параметры** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="ffd8b-137">Выберите **всегда показывать решение**.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-137">Select **Always show solution**.</span></span> <span data-ttu-id="ffd8b-138">Убедитесь также, что выбран параметр **сохранять новые проекты при создании** .</span><span class="sxs-lookup"><span data-stu-id="ffd8b-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="ffd8b-139">В **Обозреватель решений**откройте файл **IService1.CS** или **IService1. vb** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="ffd8b-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;

    namespace GettingStartedLib
    {
            [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
            public interface ICalculator
            {
                [OperationContract]
                double Add(double n1, double n2);
                [OperationContract]
                double Subtract(double n1, double n2);
                [OperationContract]
                double Multiply(double n1, double n2);
                [OperationContract]
                double Divide(double n1, double n2);
            }
    }
    ```

    ```vb
    Imports System.ServiceModel

    Namespace GettingStartedLib

        <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
        Public Interface ICalculator

            <OperationContract()> _
            Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
            <OperationContract()> _
            Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
        End Interface
    End Namespace
    ```

     <span data-ttu-id="ffd8b-140">В этом контракте определен калькулятор в сети.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-140">This contract defines an online calculator.</span></span> <span data-ttu-id="ffd8b-141">Обратите внимание, что `ICalculator` интерфейс помечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute> (в упрощенном виде `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="ffd8b-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="ffd8b-142">Этот атрибут определяет пространство имен для устранения неоднозначности имени контракта.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="ffd8b-143">Код помечает каждую операцию калькулятора атрибутом <xref:System.ServiceModel.OperationContractAttribute> (в упрощенном виде `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="ffd8b-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffd8b-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ffd8b-144">Next steps</span></span>

<span data-ttu-id="ffd8b-145">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="ffd8b-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ffd8b-146">Создайте проект библиотеки служб WCF.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="ffd8b-147">Определите интерфейс контракта службы.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-147">Define a service contract interface.</span></span>

<span data-ttu-id="ffd8b-148">Перейдите к следующему руководству, чтобы узнать, как реализовать контракт службы WCF.</span><span class="sxs-lookup"><span data-stu-id="ffd8b-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ffd8b-149">Учебник. Реализация контракта службы WCF</span><span class="sxs-lookup"><span data-stu-id="ffd8b-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
