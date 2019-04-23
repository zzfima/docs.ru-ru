---
title: Учебник. Определение контракта службы Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228397"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="26079-102">Учебник. Определение контракта службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="26079-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="26079-103">В данном учебнике первый из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="26079-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="26079-104">Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="26079-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="26079-105">При создании службы WCF, в первую очередь является определение контракта службы.</span><span class="sxs-lookup"><span data-stu-id="26079-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="26079-106">В контракте службы указаны операции, поддерживаемые службой.</span><span class="sxs-lookup"><span data-stu-id="26079-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="26079-107">Операцию можно представлять себе как метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="26079-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="26079-108">Вы создаете контракты служб, определяя визуального C# или Visual Basic (Visual Basic) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="26079-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="26079-109">Интерфейс имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="26079-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="26079-110">Каждый метод в интерфейсе соответствует определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="26079-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="26079-111">Для каждого интерфейса, необходимо применить <xref:System.ServiceModel.ServiceContractAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="26079-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="26079-112">Для каждой операции или метода, необходимо применить <xref:System.ServiceModel.OperationContractAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="26079-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="26079-113">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="26079-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="26079-114">Создание **библиотека службы WCF** проекта.</span><span class="sxs-lookup"><span data-stu-id="26079-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="26079-115">Определите интерфейс контракта службы.</span><span class="sxs-lookup"><span data-stu-id="26079-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="26079-116">Создайте проект библиотеки служб WCF и определить интерфейс контракта службы</span><span class="sxs-lookup"><span data-stu-id="26079-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="26079-117">Откройте Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="26079-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="26079-118">Чтобы сделать это, выберите в программе Visual Studio в **запустить** меню, а затем выберите **дополнительные** > **Запуск от имени администратора** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="26079-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="26079-119">Создание **библиотека службы WCF** проекта.</span><span class="sxs-lookup"><span data-stu-id="26079-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="26079-120">В меню **Файл** выберите пункт **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="26079-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="26079-121">В **новый проект** диалоговое окно, в левой части окна разверните **Visual C#** или **Visual Basic**, а затем выберите **WCF** категории.</span><span class="sxs-lookup"><span data-stu-id="26079-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="26079-122">Visual Studio отображает список шаблонов проектов в центральной части окна.</span><span class="sxs-lookup"><span data-stu-id="26079-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="26079-123">Выберите **библиотека службы WCF**.</span><span class="sxs-lookup"><span data-stu-id="26079-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="26079-124">Если вы не видите **WCF** Категория шаблона проекта, может потребоваться установить **Windows Communication Foundation** компонент Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="26079-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="26079-125">В **новый проект** выберите **открыть установщик Visual Studio** ссылку в левой части.</span><span class="sxs-lookup"><span data-stu-id="26079-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="26079-126">Выберите **отдельные компоненты** вкладке, а затем найдите и выберите **Windows Communication Foundation** под **действия разработки** категории.</span><span class="sxs-lookup"><span data-stu-id="26079-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="26079-127">Выберите **изменить** для начала установки компонента.</span><span class="sxs-lookup"><span data-stu-id="26079-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="26079-128">В нижней части окна, введите *GettingStartedLib* для **имя** и *GettingStarted* для **имя решения**.</span><span class="sxs-lookup"><span data-stu-id="26079-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="26079-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="26079-129">Select **OK**.</span></span>

      <span data-ttu-id="26079-130">Visual Studio создает проект, который имеет три файла: *IService1.cs* (или *IService1.vb* для проекта Visual Basic), *Service1.cs* (или *Service1.vb* для проекта Visual Basic), и  *App.config*. Visual Studio определяет эти файлы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="26079-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="26079-131">*IService1* файл содержит определение контракта службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="26079-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="26079-132">*Service1* файл содержит реализацию по умолчанию контракта службы.</span><span class="sxs-lookup"><span data-stu-id="26079-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="26079-133">*App.config* файл содержит сведения о конфигурации, необходимые для загрузки службы по умолчанию с помощью средства узел службы WCF Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="26079-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="26079-134">Дополнительные сведения о средстве WCF Service Host см. в разделе [узел службы WCF (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span><span class="sxs-lookup"><span data-stu-id="26079-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="26079-135">Если вы установили Visual Studio с параметрами среды разработки Visual Basic, решение может быть скрыт.</span><span class="sxs-lookup"><span data-stu-id="26079-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="26079-136">Если это так, выберите **параметры** из **средства** меню, затем выберите **проекты и решения** > **Общие** в **параметры** окна.</span><span class="sxs-lookup"><span data-stu-id="26079-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="26079-137">Выберите **всегда показывать решение**.</span><span class="sxs-lookup"><span data-stu-id="26079-137">Select **Always show solution**.</span></span> <span data-ttu-id="26079-138">Кроме того, убедитесь, что **сохранять новые проекты при создании** выбран.</span><span class="sxs-lookup"><span data-stu-id="26079-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="26079-139">Из **обозревателе решений**откройте **IService1.cs** или **IService1.vb** файл и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="26079-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="26079-140">В этом контракте определен калькулятор в сети.</span><span class="sxs-lookup"><span data-stu-id="26079-140">This contract defines an online calculator.</span></span> <span data-ttu-id="26079-141">Обратите внимание, что `ICalculator` интерфейс отмечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute> атрибут (упрощенная как `ServiceContract`).</span><span class="sxs-lookup"><span data-stu-id="26079-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="26079-142">Этот атрибут определяет пространство имен для устранения неоднозначности имени контракта.</span><span class="sxs-lookup"><span data-stu-id="26079-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="26079-143">Каждая операция калькулятора с помечает код <xref:System.ServiceModel.OperationContractAttribute> атрибут (упрощенная как `OperationContract`).</span><span class="sxs-lookup"><span data-stu-id="26079-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="26079-144">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="26079-144">Next steps</span></span>

<span data-ttu-id="26079-145">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="26079-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="26079-146">Создайте проект библиотеки служб WCF.</span><span class="sxs-lookup"><span data-stu-id="26079-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="26079-147">Определите интерфейс контракта службы.</span><span class="sxs-lookup"><span data-stu-id="26079-147">Define a service contract interface.</span></span>

<span data-ttu-id="26079-148">Перейдите к следующему руководству, чтобы узнать, как реализовать контракт службы WCF.</span><span class="sxs-lookup"><span data-stu-id="26079-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="26079-149">Учебник. Реализация контракта службы WCF</span><span class="sxs-lookup"><span data-stu-id="26079-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
