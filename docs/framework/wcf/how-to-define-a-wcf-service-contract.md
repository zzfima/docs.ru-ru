---
title: "Практическое руководство. Определение контракта службы Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: "58"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c69f79d8629acee80a2e59346032e7733ec37dea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="83d37-102">Практическое руководство. Определение контракта службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="83d37-102">How to: Define a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="83d37-103">Это первый из шести шагов, необходимых для создания базового приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="83d37-103">This is the first of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="83d37-104">Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="83d37-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="83d37-105">При создании службы [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] необходимо в первую очередь определить контракт службы.</span><span class="sxs-lookup"><span data-stu-id="83d37-105">When creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service, the first task is to define a service contract.</span></span> <span data-ttu-id="83d37-106">В контракте службы указаны операции, поддерживаемые службой.</span><span class="sxs-lookup"><span data-stu-id="83d37-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="83d37-107">Операцию можно представлять себе как метод веб-службы.</span><span class="sxs-lookup"><span data-stu-id="83d37-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="83d37-108">Контракты создаются путем определения интерфейса C++, C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83d37-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="83d37-109">Каждый метод в интерфейсе соответствует определенной операции службы.</span><span class="sxs-lookup"><span data-stu-id="83d37-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="83d37-110">К каждому интерфейсу должен быть применен атрибут <xref:System.ServiceModel.ServiceContractAttribute>, и к каждой операции должен быть применен атрибут <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="83d37-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="83d37-111">Если один из методов в интерфейсе, имеющем атрибут <xref:System.ServiceModel.ServiceContractAttribute>, не имеет атрибута <xref:System.ServiceModel.OperationContractAttribute>, этот метод не представлен службой.</span><span class="sxs-lookup"><span data-stu-id="83d37-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>  
  
 <span data-ttu-id="83d37-112">Код, используемый для выполнения этой задачи, приведен в примере после описания процедуры.</span><span class="sxs-lookup"><span data-stu-id="83d37-112">The code used for this task is provided in the example following the procedure.</span></span>  
  
### <a name="to-define-a-service-contract"></a><span data-ttu-id="83d37-113">Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="83d37-113">To define a service contract</span></span>  
  
1.  <span data-ttu-id="83d37-114">Откройте [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] от имени администратора, щелкнув правой кнопкой мыши программу в **запустить** , выберите в меню **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="83d37-114">Open  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as an administrator by right-clicking the program in the **Start** menu and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="83d37-115">Создание проекта библиотеки службы WCF, щелкнув **файл** , выберите в меню **New**, **проекта**.</span><span class="sxs-lookup"><span data-stu-id="83d37-115">Create a WCF Service Library project by clicking the **File** menu and selecting **New**, **Project**.</span></span> <span data-ttu-id="83d37-116">В **новый проект** диалоговое окно, в левой части диалогового окна разверните **Visual C#** для проекта C# или **другие языки** и затем **Visual Basic** для проекта Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83d37-116">In the **New Project** dialog, on the left-hand side of the dialog expand **Visual C#** for a C# project or **Other Languages** and then **Visual Basic** for a Visual Basic project.</span></span> <span data-ttu-id="83d37-117">В выбранном языке выберите **WCF** список шаблонов проекта отображается в центральной части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="83d37-117">Under the language selected select **WCF** and a list of project templates will be displayed on the center section of the dialog.</span></span> <span data-ttu-id="83d37-118">Выберите **библиотеки службы WCF**и тип `GettingStartedLib` в **имя** текстового поля и `GettingStarted` в **имя решения** текстовое поле в нижней части диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="83d37-118">Select **WCF Service Library**, and type `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>  
  
3.  <span data-ttu-id="83d37-119">Visual Studio создаст проект, содержащий 3 файла: IService1.cs (или IService1.vb), Service1.cs (или Service1.vb) и App.config.  В файле IService1 содержится контракт службы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83d37-119">Visual Studio will create the project which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config.  The IService1 file contains a default service contract.</span></span>  <span data-ttu-id="83d37-120">В файле Service1 содержится контракт службы, реализованный методом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83d37-120">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="83d37-121">В файле App.config содержатся настройки, необходимые для загрузки службы по умолчанию средством WCF Service Host в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="83d37-121">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="83d37-122">Дополнительные сведения о средстве узел службы WCF см. в разделе [узел службы WCF (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="83d37-122">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>  
  
4.  <span data-ttu-id="83d37-123">Откройте файл IService1.cs или IService1.vb и удалите код в пределах объявления пространства имен, оставив при этом само объявление пространства имен.</span><span class="sxs-lookup"><span data-stu-id="83d37-123">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration leaving the namespace declaration.</span></span> <span data-ttu-id="83d37-124">В пределах объявления пространства имен определите новый интерфейс с именем `ICalculator`, как показано в приведенном ниже примере кода.</span><span class="sxs-lookup"><span data-stu-id="83d37-124">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
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
  
    ```  
    ‘IService.vb  
    Imports System  
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
  
     <span data-ttu-id="83d37-125">В этом контракте определен калькулятор в сети.</span><span class="sxs-lookup"><span data-stu-id="83d37-125">This contract defines an online calculator.</span></span> <span data-ttu-id="83d37-126">Обратите внимание, что интерфейс `ICalculator` помечен атрибутом <xref:System.ServiceModel.ServiceContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="83d37-126">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="83d37-127">Этот атрибут определяет пространство имен, которое используется для устранения неоднозначности имени контракта.</span><span class="sxs-lookup"><span data-stu-id="83d37-127">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="83d37-128">Каждая операция калькулятора помечена атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="83d37-128">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="83d37-129">При использовании атрибутов для добавления заметок к интерфейсу, члену или классу в имени атрибута можно опускать часть Attribute.</span><span class="sxs-lookup"><span data-stu-id="83d37-129">When using attributes to annotate an interface, member, or class, you can drop the "Attribute" part from the attribute name.</span></span> <span data-ttu-id="83d37-130">Таким образом, <xref:System.ServiceModel.ServiceContractAttribute> изменится на `[ServiceContract]` в C# или на `<ServiceContract>` в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="83d37-130">So <xref:System.ServiceModel.ServiceContractAttribute> becomes `[ServiceContract]` in C#, or `<ServiceContract>` in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83d37-131">См. также</span><span class="sxs-lookup"><span data-stu-id="83d37-131">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="83d37-132">Практическое руководство. Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="83d37-132">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="83d37-133">Начало работы</span><span class="sxs-lookup"><span data-stu-id="83d37-133">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="83d37-134">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="83d37-134">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
