---
title: Практическое руководство. Определение контракта службы Windows Communication Foundation
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009012"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="68049-102">Практическое руководство. Определение контракта службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="68049-102">How to: Define a Windows Communication Foundation Service Contract</span></span>

<span data-ttu-id="68049-103">Это первый из шести задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="68049-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="68049-104">Общие сведения обо всех шести задачах можно получить в разделе [Учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="68049-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

 <span data-ttu-id="68049-105">При создании службы WCF, первым делом следует определить контракт службы.</span><span class="sxs-lookup"><span data-stu-id="68049-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="68049-106">В контракте службы указаны операции, поддерживаемые службой.</span><span class="sxs-lookup"><span data-stu-id="68049-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="68049-107">Операцию можно представлять себе как метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="68049-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="68049-108">Контракты создаются путем определения интерфейса C++, C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="68049-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="68049-109">Каждый метод в интерфейсе соответствует определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="68049-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="68049-110">К каждому интерфейсу должен быть применен атрибут <xref:System.ServiceModel.ServiceContractAttribute>, и к каждой операции должен быть применен атрибут <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="68049-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="68049-111">Если один из методов в интерфейсе, имеющем атрибут <xref:System.ServiceModel.ServiceContractAttribute>, не имеет атрибута <xref:System.ServiceModel.OperationContractAttribute>, этот метод не представлен службой.</span><span class="sxs-lookup"><span data-stu-id="68049-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>

 <span data-ttu-id="68049-112">Код, используемый для выполнения этой задачи, приведен в примере после описания процедуры.</span><span class="sxs-lookup"><span data-stu-id="68049-112">The code used for this task is provided in the example following the procedure.</span></span>

## <a name="define-a-service-contract"></a><span data-ttu-id="68049-113">Определите контракт службы</span><span class="sxs-lookup"><span data-stu-id="68049-113">Define a service contract</span></span>

1. <span data-ttu-id="68049-114">Откройте Visual Studio с правами администратора, щелкнув правой кнопкой мыши в программе в **запустить** меню и выбрав **дополнительные** > **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="68049-114">Open Visual Studio as an administrator by right-clicking the program in the **Start** menu and selecting **More** > **Run as administrator**.</span></span>

2. <span data-ttu-id="68049-115">Создайте проект библиотеки служб WCF.</span><span class="sxs-lookup"><span data-stu-id="68049-115">Create a WCF Service Library project.</span></span>

   1. <span data-ttu-id="68049-116">В меню **Файл** выберите пункт **Создать** > **Проект**.</span><span class="sxs-lookup"><span data-stu-id="68049-116">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="68049-117">В **новый проект** диалоговое окно, в левой части окна разверните **Visual C#** или **Visual Basic**, а затем выберите **WCF** категории.</span><span class="sxs-lookup"><span data-stu-id="68049-117">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="68049-118">Шаблоны проектов отображаются в центральной части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="68049-118">A list of project templates is displayed in the center section of the dialog.</span></span> <span data-ttu-id="68049-119">Выберите **библиотека службы WCF**.</span><span class="sxs-lookup"><span data-stu-id="68049-119">Select **WCF Service Library**.</span></span>

   3. <span data-ttu-id="68049-120">Введите `GettingStartedLib` в **имя** textbox и `GettingStarted` в **имя решения** текстовое поле в нижней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="68049-120">Enter `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>

   > [!NOTE]
   > <span data-ttu-id="68049-121">Если вы не видите **WCF** Категория шаблона проекта, может потребоваться установить **Windows Communication Foundation** компонент Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="68049-121">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="68049-122">В **новый проект** диалогового окна выберите ссылку **открыть установщик Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="68049-122">In the **New Project** dialog box, click the link that says **Open Visual Studio Installer**.</span></span> <span data-ttu-id="68049-123">Выберите **отдельные компоненты** вкладке, а затем найдите и выберите **Windows Communication Foundation** под **действия разработки** категории.</span><span class="sxs-lookup"><span data-stu-id="68049-123">Select the **Individual Components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="68049-124">Выберите **изменить** для начала установки компонента.</span><span class="sxs-lookup"><span data-stu-id="68049-124">Choose **Modify** to begin installing the component.</span></span>

   <span data-ttu-id="68049-125">Visual Studio создает проект, содержащий 3 файла: IService1.cs (или IService1.vb), Service1.cs (или Service1.vb) и App.config. В файле IService1 содержится контракт службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68049-125">Visual Studio creates the project, which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config. The IService1 file contains a default service contract.</span></span> <span data-ttu-id="68049-126">В файле Service1 содержится контракт службы, реализованный методом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="68049-126">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="68049-127">В файле App.config содержатся настройки, необходимые для загрузки службы по умолчанию средством WCF Service Host в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="68049-127">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="68049-128">Дополнительные сведения о средстве WCF Service Host см. в разделе [узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="68049-128">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>

3. <span data-ttu-id="68049-129">Откройте файл IService1.cs или IService1.vb и удалите код в объявление пространства имен, оставив объявление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="68049-129">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration, leaving the namespace declaration.</span></span> <span data-ttu-id="68049-130">В пределах объявления пространства имен определите новый интерфейс с именем `ICalculator`, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="68049-130">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>

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

     <span data-ttu-id="68049-131">В этом контракте определен калькулятор в сети.</span><span class="sxs-lookup"><span data-stu-id="68049-131">This contract defines an online calculator.</span></span> <span data-ttu-id="68049-132">Обратите внимание, что интерфейс `ICalculator` помечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="68049-132">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="68049-133">Этот атрибут определяет пространство имен, которое используется для устранения неоднозначности имени контракта.</span><span class="sxs-lookup"><span data-stu-id="68049-133">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="68049-134">Каждая операция калькулятора помечена атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="68049-134">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68049-135">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="68049-135">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="68049-136">Практическое: реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="68049-136">How to: Implement a service contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a><span data-ttu-id="68049-137">См. также</span><span class="sxs-lookup"><span data-stu-id="68049-137">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="68049-138">Практическое руководство. Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="68049-138">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="68049-139">Начало работы</span><span class="sxs-lookup"><span data-stu-id="68049-139">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="68049-140">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="68049-140">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)