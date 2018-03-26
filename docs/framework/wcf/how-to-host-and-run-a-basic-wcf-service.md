---
title: Практическое руководство. Размещение и запуск базовой службы Windows Communication Foundation
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1e1c00abfec36622f5da493165259fb1786ab8d6
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/26/2018
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="9ddad-102">Практическое руководство. Размещение и запуск базовой службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="9ddad-102">How to: Host and Run a Basic Windows Communication Foundation Service</span></span>
<span data-ttu-id="9ddad-103">Это третий из шести шагов, необходимый для создания приложения [!INCLUDE[indigo1](../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ddad-103">This is the third of six tasks required to create a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="9ddad-104">Общие сведения обо всех шести задач см. в разделе [учебник по началу работы](../../../docs/framework/wcf/getting-started-tutorial.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="9ddad-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="9ddad-105">В этом разделе описывается размещение службы [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="9ddad-105">This topic describes how to host a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service in a console application.</span></span> <span data-ttu-id="9ddad-106">Эта процедура состоит из следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="9ddad-106">This procedure consists of the following steps:</span></span>  
  
-   <span data-ttu-id="9ddad-107">Создайте консольное приложение для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-107">Create a console application project to host the service.</span></span>  
  
-   <span data-ttu-id="9ddad-108">Создайте узел службы для данной службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-108">Create a service host for the service.</span></span>  
  
-   <span data-ttu-id="9ddad-109">Включите обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="9ddad-109">Enable metadata exchange.</span></span>  
  
-   <span data-ttu-id="9ddad-110">Откройте узел службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-110">Open the service host.</span></span>  
  
 <span data-ttu-id="9ddad-111">Полный список кодов, составленных при выполнении этой задачи, приведен в примере после описания процедуры.</span><span class="sxs-lookup"><span data-stu-id="9ddad-111">A complete listing of the code written in this task is provided in the example following the procedure.</span></span>  
  
## <a name="to-create-a-new-console-application-to-host-the-service"></a><span data-ttu-id="9ddad-112">Создайте новое консольное приложение для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-112">To create a new console application to host the service</span></span>  
  
1.  <span data-ttu-id="9ddad-113">Создайте новый проект консольного приложения, щелкнув решение Приступая к работе, выбрав, **добавить**, **новый проект**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-113">Create a new Console Application project by right-clicking on the Getting Started solution, selecting, **Add**, **New Project**.</span></span> <span data-ttu-id="9ddad-114">В **Добавление нового проекта** диалогового окна в левой части окна выберите **Windows** под **C#** или **VB**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-114">In the **Add New Project** dialog on the left hand side of the dialog select **Windows** under **C#** or **VB**.</span></span> <span data-ttu-id="9ddad-115">В центральной части диалогового окна выберите **консольное приложение**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-115">In the center section of the dialog select **Console Application**.</span></span> <span data-ttu-id="9ddad-116">Задайте имя для проекта GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="9ddad-116">Name the project GettingStartedHost.</span></span>  
  
2.  <span data-ttu-id="9ddad-117">Значение целевой платформы проекта GettingStartedHost .NET Framework 4.5, щелкнув правой кнопкой мыши **GettingStartedHost** в обозревателе решений и выбрав **свойства**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-117">Set the target framework of the GettingStartedHost project to .NET Framework 4.5 by right clicking on **GettingStartedHost** in the Solution Explorer and selecting **Properties**.</span></span> <span data-ttu-id="9ddad-118">В раскрывающемся списке **требуемой версии .NET Framework** выберите **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-118">In the dropdown box labeled **Target Framework** select **.NET Framework 4.5**.</span></span> <span data-ttu-id="9ddad-119">Установка требуемой версии .NET framework для проекта Visual Basic несколько отличается, в диалоговом окне свойств проекта GettingStartedHost, щелкните **компиляции** с левой стороны экрана, а затем щелкните **Advanced компиляции Параметры** кнопки в левом нижнем углу диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="9ddad-119">Setting the target framework for a VB project is a little different, in the GettingStartedHost project properties dialog, click the **Compile** tab on the left-hand side of the screen, and then click the **Advanced Compile Options** button at the lower left-hand corner of the dialog.</span></span> <span data-ttu-id="9ddad-120">Выберите **.NET Framework 4.5** в раскрывающемся списке **требуемой версии .NET Framework**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-120">Then select **.NET Framework 4.5** in the dropdown box labeled **Target Framework**.</span></span>  
  
     <span data-ttu-id="9ddad-121">Настройка целевой версии .NET framework приведет к [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] к перезагрузке решения, нажмите клавишу **ОК** при появлении запроса.</span><span class="sxs-lookup"><span data-stu-id="9ddad-121">Setting the target framework will cause [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] to reload the solution, press **OK** when prompted.</span></span>  
  
3.  <span data-ttu-id="9ddad-122">Добавьте ссылку на проект GettingStartedLib в проект gettingstartedhost, щелкните правой кнопкой мыши **ссылки** папки в проекте GettingStartedHost в обозревателе решений и выберите **Добавление ссылки** .</span><span class="sxs-lookup"><span data-stu-id="9ddad-122">Add a reference to the GettingStartedLib project to the GettingStartedHost project by right clicking on the **References** folder under the GettingStartedHost project in the solution explorer and select **Add Reference**.</span></span> <span data-ttu-id="9ddad-123">В **добавить ссылку** диалогового окна выберите **решения** с левой стороны диалогового окна, выберите GettingStartedLib в центральной части окна и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="9ddad-123">In the **Add Reference** dialog, select **Solution** on the left-hand side of the dialog and select GettingStartedLib in the center section of the dialog and click **Add**.</span></span> <span data-ttu-id="9ddad-124">Это делает типы, определенные в GettingStartedLib, доступными в проекте GettingStartedHost.</span><span class="sxs-lookup"><span data-stu-id="9ddad-124">This makes the types defined in GettingStartedLib available to the GettingStartedHost project.</span></span>  
  
4.  <span data-ttu-id="9ddad-125">Добавить ссылку на сборку System.ServiceModel в проекте GettingStartedHost, щелкните правой кнопкой мыши **ссылки** папки в проекте GettingStartedHost в обозревателе решений и выберите **добавить** Ссылка.</span><span class="sxs-lookup"><span data-stu-id="9ddad-125">Add a reference to System.ServiceModel to the GettingStartedHost project by right-clicking the **Reference** folder under the GettingStartedHost project in Solution Explorer and select **Add** Reference.</span></span> <span data-ttu-id="9ddad-126">В **добавить ссылку** окна выберите **Framework** с левой стороны диалогового окна.</span><span class="sxs-lookup"><span data-stu-id="9ddad-126">In the **Add Reference** dialog select **Framework** on the left-hand side of the dialog.</span></span> <span data-ttu-id="9ddad-127">В текстовом поле «Поиск сборок» введите `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="9ddad-127">In the Search Assemblies textbox, type in `System.ServiceModel`.</span></span> <span data-ttu-id="9ddad-128">В центральной части диалогового окна выберите **System.ServiceModel**, нажмите кнопку **добавить** и нажмите кнопку **закрыть** кнопки.</span><span class="sxs-lookup"><span data-stu-id="9ddad-128">In the center section of the dialog select **System.ServiceModel**, click the **Add** button, and click the **Close** button.</span></span> <span data-ttu-id="9ddad-129">Сохраните решение, нажав кнопку «Сохранить все» под главным меню.</span><span class="sxs-lookup"><span data-stu-id="9ddad-129">Save the solution by clicking the Save All button below the main menu.</span></span>  
  
### <a name="to-host-the-service"></a><span data-ttu-id="9ddad-130">Размещение службы</span><span class="sxs-lookup"><span data-stu-id="9ddad-130">To host the service</span></span>  
  
-   <span data-ttu-id="9ddad-131">Откройте файл Program.cs или Module.vb и введите следующий код:</span><span class="sxs-lookup"><span data-stu-id="9ddad-131">Open the Program.cs or Module.vb file and enter the following code:</span></span>  
  
    ```csharp
    // program.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using System.ServiceModel;  
    using GettingStartedLib;  
    using System.ServiceModel.Description;   
  
    namespace GettingStartedHost  
    {  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                // Step 1 Create a URI to serve as the base address.  
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");  
  
                // Step 2 Create a ServiceHost instance  
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
  
                try  
                {  
                    // Step 3 Add a service endpoint.  
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");  
  
                    // Step 4 Enable metadata exchange.  
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
                    smb.HttpGetEnabled = true;  
                    selfHost.Description.Behaviors.Add(smb);  
  
                    // Step 5 Start the service.  
                    selfHost.Open();  
                    Console.WriteLine("The service is ready.");  
                    Console.WriteLine("Press <ENTER> to terminate service.");  
                    Console.WriteLine();  
                    Console.ReadLine();  
  
                    // Close the ServiceHostBase to shutdown the service.  
                    selfHost.Close();  
                }  
                catch (CommunicationException ce)  
                {  
                    Console.WriteLine("An exception occurred: {0}", ce.Message);  
                    selfHost.Abort();  
                }  
            }  
        }  
    }  
    ```  
  
    ```vb
    'Module1.vb  
    Imports System  
    Imports System.ServiceModel  
    Imports System.ServiceModel.Description  
    Imports GettingStartedLibVB.GettingStartedLib  
  
    Module Service  
  
        Class Program  
            Shared Sub Main()  
                ' Step 1 Create a URI to serve as the base address  
                Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
                ' Step 2 Create a ServiceHost instance  
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)  
                Try  
  
                    ' Step 3 Add a service endpoint  
                    ' Add a service endpoint  
                    selfHost.AddServiceEndpoint( _  
                        GetType(ICalculator), _  
                        New WSHttpBinding(), _  
                        "CalculatorService")  
  
                    ' Step 4 Enable metadata exchange.  
                    Dim smb As New ServiceMetadataBehavior()  
                    smb.HttpGetEnabled = True  
                    selfHost.Description.Behaviors.Add(smb)  
  
                    ' Step 5 Start the service  
                    selfHost.Open()  
                    Console.WriteLine("The service is ready.")  
                    Console.WriteLine("Press <ENTER> to terminate service.")  
                    Console.WriteLine()  
                    Console.ReadLine()  
  
                    ' Close the ServiceHostBase to shutdown the service.  
                    selfHost.Close()  
                Catch ce As CommunicationException  
                    Console.WriteLine("An exception occurred: {0}", ce.Message)  
                    selfHost.Abort()  
                End Try  
            End Sub  
        End Class  
  
    End Module  
    ```  
  
    1.  <span data-ttu-id="9ddad-132">Шаг 1. Создает экземпляр класса с именем с базовым адресом службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-132">Step 1 - Creates an instance of the Uri class to hold the base address of the service.</span></span> <span data-ttu-id="9ddad-133">Службы задаются URL-адресом, содержащим базовый адрес и дополнительный универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="9ddad-133">Services are identified by a URL which contains a base address and an optional URI.</span></span> <span data-ttu-id="9ddad-134">Базовый адрес имеет следующий формат: [транспорт] :// [имя компьютера или домена] [: необязательно порт #] / [необязательно-сегмент URI] базовый адрес службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI «Приступая к работе»</span><span class="sxs-lookup"><span data-stu-id="9ddad-134">The base address is formatted as follows:[transport]://[machine-name or domain][:optional port #]/[optional URI segment]The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment "GettingStarted"</span></span>  
  
    2.  <span data-ttu-id="9ddad-135">Шаг 2. Создает экземпляр класса <xref:System.ServiceModel.ServiceHost> для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-135">Step 2 – Creates an instance of the <xref:System.ServiceModel.ServiceHost> class to host the service.</span></span> <span data-ttu-id="9ddad-136">Конструктор принимает 2 параметра: тип класса, который реализует контракт службы, и базовый адрес службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-136">The constructor takes two parameters, the type of the class that implements the service contract, and the base address of the service.</span></span>  
  
    3.  <span data-ttu-id="9ddad-137">Шаг 3 – создает <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9ddad-137">Step 3 – Creates a <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` instance.</span></span> <span data-ttu-id="9ddad-138">Конечная точка службы состоит из адреса, привязки и контракта службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-138">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="9ddad-139"><!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint` Таким образом конструктор принимает тип интерфейса контракта службы, привязку и адрес.</span><span class="sxs-lookup"><span data-stu-id="9ddad-139">The <!--zz <xref:System.ServiceModel.ServiceEndpoint>--> ` System.ServiceModel.ServiceEndpoint`  constructor therefore takes the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="9ddad-140">Контракт службы - `ICalculator`. Он определен и реализуется в типе службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-140">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="9ddad-141">В этом образце используется встроенная привязка <xref:System.ServiceModel.WSHttpBinding> для подключения к конечным точкам, соответствующим спецификациями WS-\*.</span><span class="sxs-lookup"><span data-stu-id="9ddad-141">The binding used in this sample is <xref:System.ServiceModel.WSHttpBinding> which is a built-in binding that is used for connecting to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="9ddad-142">Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](../../../docs/framework/wcf/bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-142">For more information about WCF bindings, see [WCF Bindings Overview](../../../docs/framework/wcf/bindings-overview.md).</span></span> <span data-ttu-id="9ddad-143">Адрес добавляется к базовому адресу для определения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="9ddad-143">The address is appended to the base address to identify the endpoint.</span></span> <span data-ttu-id="9ddad-144">Адрес, указанный в этом коде является «CalculatorService», поэтому полного адреса конечной точки `"http://localhost:8000/GettingStarted/CalculatorService"` Добавление конечной точки службы, обязательно при использовании .NET Framework 4.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9ddad-144">The address specified in this code is "CalculatorService" so the fully qualified address for the endpoint is `"http://localhost:8000/GettingStarted/CalculatorService"` Adding a service endpoint is optional when using .NET Framework 4.0 or later.</span></span> <span data-ttu-id="9ddad-145">В этих версиях, если конечные точки не заданы в коде или в конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="9ddad-145">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="9ddad-146">Дополнительные сведения о умолчанию конечные точки в разделе [Задание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-146">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9ddad-147"> о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-147"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="9ddad-148">Добавление конечной точки службы не обязательно при использовании .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="9ddad-148">Adding a service endpoint is optional when using .NET Framework 4 or later.</span></span> <span data-ttu-id="9ddad-149">В этих версиях, если конечные точки не заданы в коде или в конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого базового адреса в каждом контракте, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="9ddad-149">In these versions, if no endpoints are added in code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="9ddad-150">Дополнительные сведения о умолчанию конечные точки в разделе [Задание адреса конечной точки](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-150">For more information about default endpoints see [Specifying an Endpoint Address](../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9ddad-151"> о конечных точках по умолчанию, привязках и режимах работы см. в разделах [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-151"> default endpoints, bindings, and behaviors, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
    4.  <span data-ttu-id="9ddad-152">Шаг 4. Включение обмена метаданными.</span><span class="sxs-lookup"><span data-stu-id="9ddad-152">Step 4 – Enable metadata exchange.</span></span> <span data-ttu-id="9ddad-153">Клиенты могут использовать обмен метаданными для создания прокси-объектов, которые будут использоваться для вызова операции службы.</span><span class="sxs-lookup"><span data-stu-id="9ddad-153">Clients will use metadata exchange to generate proxies that will be used to call the service operations.</span></span> <span data-ttu-id="9ddad-154">Включение обмена метаданными создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior> экземпляра, установите его на <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> свойства `true`и добавьте поведение <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  --> `System.ServiceModel.ServiceHost.Behaviors%2A` коллекцию <xref:System.ServiceModel.ServiceHost> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9ddad-154">To enable metadata exchange create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set it’s <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, and add the behavior to the <!--zz <xref:System.ServiceModel.ServiceHost.Behaviors%2A>  -->`System.ServiceModel.ServiceHost.Behaviors%2A` collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>  
  
    5.  <span data-ttu-id="9ddad-155">Шаг 5. Откройте <xref:System.ServiceModel.ServiceHost>, чтобы прослушивать входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="9ddad-155">Step 5 – Open the <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="9ddad-156">Обратите внимание, что код ожидает, пока пользователь не нажмет ENTER.</span><span class="sxs-lookup"><span data-stu-id="9ddad-156">Notice the code waits for the user to hit enter.</span></span> <span data-ttu-id="9ddad-157">Если этого не сделать, то приложение немедленно закроется и служба завершит работу. Также обратите внимание, что используется блок try/catch.</span><span class="sxs-lookup"><span data-stu-id="9ddad-157">If you do not do this, the app will close immediately and the service will shut down.Also notice a  try/catch block used.</span></span> <span data-ttu-id="9ddad-158">После создания экземпляра <xref:System.ServiceModel.ServiceHost> другой код находится в блоке try/catch.</span><span class="sxs-lookup"><span data-stu-id="9ddad-158">After the <xref:System.ServiceModel.ServiceHost> has been instantiated, all other code is placed in a try/catch block.</span></span> <span data-ttu-id="9ddad-159">Дополнительные сведения о перехвате исключений, вызванных безопасно <xref:System.ServiceModel.ServiceHost>, в разделе [как избежать проблем при использовании операторов](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span><span class="sxs-lookup"><span data-stu-id="9ddad-159">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)</span></span>  
  
### <a name="to-verify-the-service-is-working"></a><span data-ttu-id="9ddad-160">Проверка работы службы</span><span class="sxs-lookup"><span data-stu-id="9ddad-160">To verify the service is working</span></span>  
  
1.  <span data-ttu-id="9ddad-161">Запустите консольное приложение GettingStartedHost с [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9ddad-161">Run the GettingStartedHost console application from inside [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="9ddad-162">В [!INCLUDE[wv](../../../includes/wv-md.md)] и более поздних операционных системах служба должна запускаться пользователем с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9ddad-162">When running on [!INCLUDE[wv](../../../includes/wv-md.md)] and later operating systems, the service must be run with administrator privileges.</span></span> <span data-ttu-id="9ddad-163">Так как [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] была запущена с правами администратора, GettingStartedHost также запускается с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="9ddad-163">Because [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] was run with Administrator privileges, GettingStartedHost is also run with Administrator privileges.</span></span> <span data-ttu-id="9ddad-164">Вы также можете запустить новую командную строку с правами администратора, а затем в ней запустить service.exe.</span><span class="sxs-lookup"><span data-stu-id="9ddad-164">You can also start a new command prompt running it with Administrator privileges and run service.exe within it.</span></span>  
  
2.  <span data-ttu-id="9ddad-165">Откройте Internet Explorer и перейдите на страницу отладки службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="9ddad-165">Open Internet Explorer and browse to the service's debug page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ddad-166">Пример</span><span class="sxs-lookup"><span data-stu-id="9ddad-166">Example</span></span>  
 <span data-ttu-id="9ddad-167">Нижеприведенный пример иллюстрирует создание контракта службы и ее реализацию (см. предыдущие шаги в руководстве), а также размещение службы в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="9ddad-167">The following example includes the service contract and implementation from previous steps in the tutorial and hosts the service in a console application.</span></span>  
  
 <span data-ttu-id="9ddad-168">Для компиляции с помощью компилятора командной строки, скомпилируйте IService1.cs и Service1.cs в библиотеке класса ссылки на `System.ServiceModel.dll`.</span><span class="sxs-lookup"><span data-stu-id="9ddad-168">To compile this with a command-line compiler, compile IService1.cs and Service1.cs into a class library referencing `System.ServiceModel.dll`.</span></span> <span data-ttu-id="9ddad-169">Затем скомпилируйте Program.cs в консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="9ddad-169">And compile Program.cs to a console application.</span></span>  
  
```csharp
// IService1.cs  
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
  
```csharp
// Service1.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
  
namespace GettingStartedLib  
{  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            double result = n1 + n2;  
            Console.WriteLine("Received Add({0},{1})", n1, n2);  
            // Code added to write output to the console window.  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Subtract(double n1, double n2)  
        {  
            double result = n1 - n2;  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Multiply(double n1, double n2)  
        {  
            double result = n1 * n2;  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
  
        public double Divide(double n1, double n2)  
        {  
            double result = n1 / n2;  
            Console.WriteLine("Received Divide({0},{1})", n1, n2);  
            Console.WriteLine("Return: {0}", result);  
            return result;  
        }  
    }  
}  
```  
  
```csharp
//Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.ServiceModel;  
using GettingStartedLib;  
using System.ServiceModel.Description;   
  
namespace GettingStartedHost  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Uri baseAddress = new Uri("http://localhost:8000/ServiceModelSamples/Service");  
  
            // Step 2 of the hosting procedure: Create ServiceHost  
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
  
            try  
            {  
                // Step 3 of the hosting procedure: Add a service endpoint.  
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");  
  
                // Step 4 of the hosting procedure: Enable metadata exchange.  
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
                smb.HttpGetEnabled = true;  
                selfHost.Description.Behaviors.Add(smb);  
  
                // Step 5 of the hosting procedure: Start (and then stop) the service.  
                selfHost.Open();  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
  
                // Close the ServiceHostBase to shutdown the service.  
                selfHost.Close();  
            }  
            catch (CommunicationException ce)  
            {  
                Console.WriteLine("An exception occurred: {0}", ce.Message);  
                selfHost.Abort();  
            }  
        }  
    }  
}  
```  
  
```vb
'IService1.vb  
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
  
```vb
'Service1.vb  
Imports System  
Imports System.ServiceModel  
  
Namespace GettingStartedLib  
  
    Public Class CalculatorService  
        Implements ICalculator  
  
        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add  
            Dim result As Double = n1 + n2  
            ' Code added to write output to the console window.  
            Console.WriteLine("Received Add({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
        End Function  
  
        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract  
            Dim result As Double = n1 - n2  
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply  
            Dim result As Double = n1 * n2  
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
  
        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide  
            Dim result As Double = n1 / n2  
            Console.WriteLine("Received Divide({0},{1})", n1, n2)  
            Console.WriteLine("Return: {0}", result)  
            Return result  
  
        End Function  
    End Class  
End Namespace  
```  
  
```vb
'Module1.vb  
Imports System  
Imports System.ServiceModel  
Imports System.ServiceModel.Description  
Imports GettingStartedLibVB.GettingStartedLib  
  
Module Service  
  
    Class Program  
        Shared Sub Main()  
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.  
            Dim baseAddress As New Uri("http://localhost:8000/ServiceModelSamples/Service")  
  
            ' Step 2 of the hosting procedure: Create ServiceHost  
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)  
            Try  
  
                ' Step 3 of the hosting procedure: Add a service endpoint.  
                ' Add a service endpoint  
                selfHost.AddServiceEndpoint( _  
                    GetType(ICalculator), _  
                    New WSHttpBinding(), _  
                    "CalculatorService")  
  
                ' Step 4 of the hosting procedure: Enable metadata exchange.  
                ' Enable metadata exchange  
                Dim smb As New ServiceMetadataBehavior()  
                smb.HttpGetEnabled = True  
                selfHost.Description.Behaviors.Add(smb)  
  
                ' Step 5 of the hosting procedure: Start (and then stop) the service.  
                selfHost.Open()  
                Console.WriteLine("The service is ready.")  
                Console.WriteLine("Press <ENTER> to terminate service.")  
                Console.WriteLine()  
                Console.ReadLine()  
  
                ' Close the ServiceHostBase to shutdown the service.  
                selfHost.Close()  
            Catch ce As CommunicationException  
                Console.WriteLine("An exception occurred: {0}", ce.Message)  
                selfHost.Abort()  
            End Try  
        End Sub  
    End Class  
  
End Module  
```  
  
> [!NOTE]
>  <span data-ttu-id="9ddad-170">Подобные службы требуют разрешения на регистрацию на компьютере HTTP-адресов, на которые будет ожидаться передача данных.</span><span class="sxs-lookup"><span data-stu-id="9ddad-170">Services such as this one require permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="9ddad-171">Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP.</span><span class="sxs-lookup"><span data-stu-id="9ddad-171">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="9ddad-172"> как настроить резервирование пространства имен см. в разделе [Настройка протоколов HTTP и HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-172"> how to configure namespace reservations, see [Configuring HTTP and HTTPS](../../../docs/framework/wcf/feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="9ddad-173">Запуск файла service.exe на [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] возможен только при наличии прав администратора.</span><span class="sxs-lookup"><span data-stu-id="9ddad-173">When running under [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)], the service.exe must be run with administrator privileges.</span></span>  
  
 <span data-ttu-id="9ddad-174">Сейчас служба запущена.</span><span class="sxs-lookup"><span data-stu-id="9ddad-174">Now the service is running.</span></span> <span data-ttu-id="9ddad-175">Перейти к [как: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-175">Proceed to [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="9ddad-176">Сведения об устранении неполадок в разделе [Устранение неполадок учебник по началу работы](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="9ddad-176">For troubleshooting information, see [Troubleshooting the Getting Started Tutorial](../../../docs/framework/wcf/troubleshooting-the-getting-started-tutorial.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ddad-177">См. также</span><span class="sxs-lookup"><span data-stu-id="9ddad-177">See Also</span></span>  
 [<span data-ttu-id="9ddad-178">Начало работы</span><span class="sxs-lookup"><span data-stu-id="9ddad-178">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="9ddad-179">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="9ddad-179">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
