---
title: Учебник. Определение контракта службы Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: ba88fc6ba4cba8d46ed1b43080d471b1b7c4bd75
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928878"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="f5e19-102">Учебник. Определение контракта службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="f5e19-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="f5e19-103">В этом руководстве описывается первая из пяти задач, необходимых для создания приложения Basic Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f5e19-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="f5e19-104">Общие сведения о учебниках см. в [разделе Учебник. Приступая к работе с](getting-started-tutorial.md)Windows Communication Foundation приложениями.</span><span class="sxs-lookup"><span data-stu-id="f5e19-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="f5e19-105">При создании службы WCF первая задача заключается в определении контракта службы.</span><span class="sxs-lookup"><span data-stu-id="f5e19-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="f5e19-106">В контракте службы указаны операции, поддерживаемые службой.</span><span class="sxs-lookup"><span data-stu-id="f5e19-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="f5e19-107">Операцию можно представлять себе как метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="f5e19-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="f5e19-108">Контракты служб создаются путем определения визуального C# элемента или интерфейса Visual Basic (VB).</span><span class="sxs-lookup"><span data-stu-id="f5e19-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="f5e19-109">Интерфейс имеет следующие характеристики.</span><span class="sxs-lookup"><span data-stu-id="f5e19-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="f5e19-110">Каждый метод в интерфейсе соответствует определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="f5e19-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="f5e19-111">Для каждого интерфейса необходимо применить <xref:System.ServiceModel.ServiceContractAttribute> атрибут.</span><span class="sxs-lookup"><span data-stu-id="f5e19-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="f5e19-112">Для каждой операции или метода необходимо применить <xref:System.ServiceModel.OperationContractAttribute> атрибут.</span><span class="sxs-lookup"><span data-stu-id="f5e19-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="f5e19-113">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="f5e19-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f5e19-114">Создайте проект **библиотеки служб WCF** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="f5e19-115">Определите интерфейс контракта службы.</span><span class="sxs-lookup"><span data-stu-id="f5e19-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="f5e19-116">Создание проекта библиотеки службы WCF и определение интерфейса контракта службы</span><span class="sxs-lookup"><span data-stu-id="f5e19-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="f5e19-117">Откройте Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="f5e19-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="f5e19-118">Для этого выберите программу Visual Studio в меню **Пуск** , а затем в контекстном меню выберите пункт **другие** > **Запуск от имени администратора** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="f5e19-119">Создайте проект **библиотеки служб WCF** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="f5e19-120">В меню **Файл** выберите пункт **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="f5e19-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="f5e19-121">В диалоговом окне **Новый проект** в левой части разверните узел  **C# визуальный** элемент или **Visual Basic**, а затем выберите категорию **WCF** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="f5e19-122">Visual Studio отображает список шаблонов проектов в центральной части окна.</span><span class="sxs-lookup"><span data-stu-id="f5e19-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="f5e19-123">Выберите **библиотеку служб WCF**.</span><span class="sxs-lookup"><span data-stu-id="f5e19-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="f5e19-124">Если вы не видите категорию шаблона проекта **WCF** , может потребоваться установить компонент **Windows Communication Foundation** Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5e19-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="f5e19-125">В диалоговом окне **Новый проект** выберите ссылку **открыть Visual Studio Installer** в левой части.</span><span class="sxs-lookup"><span data-stu-id="f5e19-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="f5e19-126">Перейдите на вкладку **отдельные компоненты** , а затем найдите и выберите **Windows Communication Foundation** в категории **действия разработки** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="f5e19-127">Нажмите кнопку **изменить** , чтобы начать установку компонента.</span><span class="sxs-lookup"><span data-stu-id="f5e19-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="f5e19-128">В нижнем разделе окна введите *жеттингстартедлиб* в качестве **имени** и *GettingStarted* в качестве **имени решения**.</span><span class="sxs-lookup"><span data-stu-id="f5e19-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="f5e19-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f5e19-129">Select **OK**.</span></span>

      <span data-ttu-id="f5e19-130">Visual Studio создаст проект с тремя файлами: *IService1.CS* (или *IService1. vb* для проекта Visual Basic), *Service1.CS* (или *Service1. vb* для Visual Basic проекта) и *app. config*. Visual Studio определяет эти файлы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f5e19-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="f5e19-131">Файл *IService1* содержит определение контракта службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f5e19-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="f5e19-132">Файл *Service1* содержит реализацию по умолчанию контракта службы.</span><span class="sxs-lookup"><span data-stu-id="f5e19-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="f5e19-133">Файл *app. config* содержит сведения о конфигурации, необходимые для загрузки службы по умолчанию с помощью средства размещения службы WCF Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f5e19-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="f5e19-134">Дополнительные сведения о средстве размещения службы WCF см. в разделе [узел службы WCF (WcfSvcHost. exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f5e19-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="f5e19-135">Если вы установили Visual Studio с параметрами среды разработчика Visual Basic, решение может быть скрыто.</span><span class="sxs-lookup"><span data-stu-id="f5e19-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="f5e19-136">В этом случае выберите в меню **Сервис** пункт **Параметры** , а затем в окне **Параметры** выберите **проекты и решения** > **Общие** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="f5e19-137">Выберите **всегда показывать решение**.</span><span class="sxs-lookup"><span data-stu-id="f5e19-137">Select **Always show solution**.</span></span> <span data-ttu-id="f5e19-138">Убедитесь также, что выбран параметр **сохранять новые проекты при создании** .</span><span class="sxs-lookup"><span data-stu-id="f5e19-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="f5e19-139">В **Обозреватель решений**откройте файл **IService1.CS** или **IService1. vb** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="f5e19-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="f5e19-140">В этом контракте определен калькулятор в сети.</span><span class="sxs-lookup"><span data-stu-id="f5e19-140">This contract defines an online calculator.</span></span> <span data-ttu-id="f5e19-141">Обратите `ICalculator` внимание, что интерфейс помечен <xref:System.ServiceModel.ServiceContractAttribute> атрибутом (с `ServiceContract`упрощенным именем).</span><span class="sxs-lookup"><span data-stu-id="f5e19-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="f5e19-142">Этот атрибут определяет пространство имен для устранения неоднозначности имени контракта.</span><span class="sxs-lookup"><span data-stu-id="f5e19-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="f5e19-143">Код помечает каждую операцию <xref:System.ServiceModel.OperationContractAttribute> калькулятора атрибутом (упрощенный как `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="f5e19-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5e19-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="f5e19-144">Next steps</span></span>

<span data-ttu-id="f5e19-145">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="f5e19-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="f5e19-146">Создайте проект библиотеки служб WCF.</span><span class="sxs-lookup"><span data-stu-id="f5e19-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="f5e19-147">Определите интерфейс контракта службы.</span><span class="sxs-lookup"><span data-stu-id="f5e19-147">Define a service contract interface.</span></span>

<span data-ttu-id="f5e19-148">Перейдите к следующему руководству, чтобы узнать, как реализовать контракт службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f5e19-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5e19-149">Учебник. Реализация контракта службы WCF</span><span class="sxs-lookup"><span data-stu-id="f5e19-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
