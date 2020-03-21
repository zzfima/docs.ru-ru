---
title: 'Учебник: Определите контракт на обслуживание Фонда связи Windows'
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184097"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="131b8-102">Учебник: Определите контракт на обслуживание Фонда связи Windows</span><span class="sxs-lookup"><span data-stu-id="131b8-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="131b8-103">В этом уроке описана первая из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="131b8-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="131b8-104">Для обзора учебников [см.](getting-started-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="131b8-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="131b8-105">При создании службы WCF ваша первая задача состоит в определении договора на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="131b8-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="131b8-106">Контракт службы определяет, какие операции поддерживает служба.</span><span class="sxs-lookup"><span data-stu-id="131b8-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="131b8-107">Операцию можно представлять себе как метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="131b8-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="131b8-108">Вы создаете сервисные контракты, определяя интерфейс СЗ или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="131b8-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="131b8-109">Интерфейс имеет следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="131b8-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="131b8-110">Каждый метод в интерфейсе соответствует определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="131b8-110">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="131b8-111">Для каждого интерфейса необходимо <xref:System.ServiceModel.ServiceContractAttribute> применить атрибут.</span><span class="sxs-lookup"><span data-stu-id="131b8-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="131b8-112">Для каждой операции/метода <xref:System.ServiceModel.OperationContractAttribute> необходимо применить атрибут.</span><span class="sxs-lookup"><span data-stu-id="131b8-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="131b8-113">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="131b8-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="131b8-114">Создайте проект **библиотеки обслуживания WCF.**</span><span class="sxs-lookup"><span data-stu-id="131b8-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="131b8-115">Определите интерфейс контракта на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="131b8-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="131b8-116">Создание проекта Библиотеки обслуживания WCF и определение интерфейса контракта на обслуживание</span><span class="sxs-lookup"><span data-stu-id="131b8-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="131b8-117">Откройте Visual Studio от имени администратора.</span><span class="sxs-lookup"><span data-stu-id="131b8-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="131b8-118">Для этого выберите программу Visual Studio в меню **«Пуск»,** а затем выберите **More** > Run в**качестве администратора** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="131b8-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="131b8-119">Создайте проект **библиотеки обслуживания WCF.**</span><span class="sxs-lookup"><span data-stu-id="131b8-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="131b8-120">В меню **Файл** выберите пункт **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="131b8-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="131b8-121">В диалоге **Нового проекта,** на левой стороне, расширьте **Visual C или** Visual **Basic,** а затем выберите категорию **WCF.**</span><span class="sxs-lookup"><span data-stu-id="131b8-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="131b8-122">Visual Studio отображает список шаблонов проекта в центральной части окна.</span><span class="sxs-lookup"><span data-stu-id="131b8-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="131b8-123">Выберите **библиотеку обслуживания WCF**.</span><span class="sxs-lookup"><span data-stu-id="131b8-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="131b8-124">Если вы не видите категорию шаблона проекта **WCF,** возможно, потребуется установить компонент **Windows Communication Foundation** visual Studio.</span><span class="sxs-lookup"><span data-stu-id="131b8-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="131b8-125">В диалоговом окне **нового проекта** выберите ссылку Open Visual **Studio Installer** на левой стороне.</span><span class="sxs-lookup"><span data-stu-id="131b8-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="131b8-126">Выберите вкладку **Отдельные компоненты,** а затем найдите и выберите **Фонд связи Windows** в категории **«Деятельность развития».**</span><span class="sxs-lookup"><span data-stu-id="131b8-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="131b8-127">Выберите **изменение,** чтобы начать установку компонента.</span><span class="sxs-lookup"><span data-stu-id="131b8-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="131b8-128">В нижней части окна введите *GettingStartedLib* для **имени** и *GettingStarted* для **имени решения.**</span><span class="sxs-lookup"><span data-stu-id="131b8-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="131b8-129">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="131b8-129">Select **OK**.</span></span>

      <span data-ttu-id="131b8-130">Visual Studio создает проект, который состоит из трех файлов: *IService1.cs* (или *IService1.vb* для визуального базового проекта), *Service1.cs* (или *Service1.vb* для визуального базового проекта) и *App.config*. Visual Studio определяет эти файлы следующим образом:</span><span class="sxs-lookup"><span data-stu-id="131b8-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="131b8-131">Файл *IService1* содержит определение контракта службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="131b8-131">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="131b8-132">Файл *Service1* содержит выполнение контракта службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="131b8-132">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="131b8-133">Файл *App.config* содержит информацию о конфигурации, необходимую для загрузки службы по умолчанию с помощью инструмента Visual Studio WCF Service Host.</span><span class="sxs-lookup"><span data-stu-id="131b8-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="131b8-134">Для получения дополнительной информации об инструменте WCF Service Host [см.](wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="131b8-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="131b8-135">Если вы установили Visual Studio с настройками среды Visual Basic, решение может быть скрыто.</span><span class="sxs-lookup"><span data-stu-id="131b8-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="131b8-136">Если это так, выберите **Параметры** из меню **Инструментов,** а затем выберите **проекты и** > **общие** решения в окне **опционов.**</span><span class="sxs-lookup"><span data-stu-id="131b8-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="131b8-137">Выберите **Всегда показывать решение.**</span><span class="sxs-lookup"><span data-stu-id="131b8-137">Select **Always show solution**.</span></span> <span data-ttu-id="131b8-138">Кроме того, убедитесь, что **Сохранение новых проектов при создании** выбрано.</span><span class="sxs-lookup"><span data-stu-id="131b8-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="131b8-139">От **Solution Explorer**откройте файл **IService1.cs** или **IService1.vb** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="131b8-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="131b8-140">В этом контракте определен калькулятор в сети.</span><span class="sxs-lookup"><span data-stu-id="131b8-140">This contract defines an online calculator.</span></span> <span data-ttu-id="131b8-141">Обратите `ICalculator` внимание, что <xref:System.ServiceModel.ServiceContractAttribute> интерфейс помечен `ServiceContract`атрибутом (упрощенкак).</span><span class="sxs-lookup"><span data-stu-id="131b8-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="131b8-142">Этот атрибут определяет пространство имен для того, чтобы отослать название контракта.</span><span class="sxs-lookup"><span data-stu-id="131b8-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="131b8-143">Код помечает каждую <xref:System.ServiceModel.OperationContractAttribute> операцию калькулятора атрибутом (упрощенным как). `OperationContract`</span><span class="sxs-lookup"><span data-stu-id="131b8-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="131b8-144">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="131b8-144">Next steps</span></span>

<span data-ttu-id="131b8-145">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="131b8-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="131b8-146">Создайте проект библиотеки обслуживания WCF.</span><span class="sxs-lookup"><span data-stu-id="131b8-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="131b8-147">Определите интерфейс контракта на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="131b8-147">Define a service contract interface.</span></span>

<span data-ttu-id="131b8-148">Перейти к следующему учебнику, чтобы узнать, как реализовать контракт на обслуживание WCF.</span><span class="sxs-lookup"><span data-stu-id="131b8-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="131b8-149">Учебник: Реализация контракта на обслуживание WCF</span><span class="sxs-lookup"><span data-stu-id="131b8-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
