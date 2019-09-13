---
title: Учебник. Размещение и запуск базовой службы Windows Communication Foundation
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 984c5e73a8efc4e9c2d487485267868ffa2f60f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928716"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="d3670-102">Учебник. Размещение и запуск базовой службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="d3670-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="d3670-103">В этом руководстве описывается третья из пяти задач, необходимых для создания приложения Basic Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="d3670-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d3670-104">Общие сведения о учебниках см. в [разделе Учебник. Приступая к работе с](getting-started-tutorial.md)Windows Communication Foundation приложениями.</span><span class="sxs-lookup"><span data-stu-id="d3670-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="d3670-105">Следующей задачей для создания приложения WCF является размещение службы WCF в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="d3670-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="d3670-106">Служба WCF предоставляет одну или несколько *конечных точек*, каждая из которых предоставляет одну или несколько операций службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="d3670-107">Конечная точка службы задает следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="d3670-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="d3670-108">Адрес, по которому можно найти службу.</span><span class="sxs-lookup"><span data-stu-id="d3670-108">An address where you can find the service.</span></span>
- <span data-ttu-id="d3670-109">Привязка, которая содержит сведения, описывающие, как клиент должен взаимодействовать со службой.</span><span class="sxs-lookup"><span data-stu-id="d3670-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="d3670-110">Контракт, определяющий функциональные возможности, предоставляемые службой своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="d3670-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="d3670-111">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="d3670-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d3670-112">Создание и Настройка проекта консольного приложения для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d3670-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="d3670-113">Добавьте код для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d3670-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="d3670-114">Обновите файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d3670-114">Update the configuration file.</span></span>
> - <span data-ttu-id="d3670-115">Запустите службу WCF и убедитесь, что она запущена.</span><span class="sxs-lookup"><span data-stu-id="d3670-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="d3670-116">Создание и Настройка проекта консольного приложения для размещения службы</span><span class="sxs-lookup"><span data-stu-id="d3670-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="d3670-117">Создание проекта консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="d3670-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="d3670-118">В меню **файл** выберите команду **Открыть** > **проект или решение** и перейдите к созданному ранее решению **GettingStarted** (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="d3670-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="d3670-119">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="d3670-119">Select **Open**.</span></span>

    2. <span data-ttu-id="d3670-120">В меню **вид** выберите **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="d3670-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="d3670-121">В окне **Обозреватель решений** выберите решение **GettingStarted** (верхний узел), а затем в контекстном меню выберите **добавить** > **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="d3670-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="d3670-122">В левой части окна **Добавление нового проекта** выберите категорию **Рабочий стол Windows** в разделе  **C# Visual** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="d3670-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="d3670-123">Выберите шаблон **консольное приложение (.NET Framework)** и введите *GettingStartedHost* в поле **имя**.</span><span class="sxs-lookup"><span data-stu-id="d3670-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="d3670-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3670-124">Select **OK**.</span></span>

2. <span data-ttu-id="d3670-125">Добавьте ссылку в проект **GettingStartedHost** в проект **жеттингстартедлиб** :</span><span class="sxs-lookup"><span data-stu-id="d3670-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="d3670-126">В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedHost** , а затем в контекстном меню выберите пункт **Добавить ссылку** .</span><span class="sxs-lookup"><span data-stu-id="d3670-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="d3670-127">В диалоговом окне **Добавление ссылки** в разделе **проекты** в левой части окна выберите **решение**.</span><span class="sxs-lookup"><span data-stu-id="d3670-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="d3670-128">Выберите **жеттингстартедлиб** в центральном разделе окна, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3670-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="d3670-129">Это действие делает типы, определенные в проекте **жеттингстартедлиб** , доступными для проекта **GettingStartedHost** .</span><span class="sxs-lookup"><span data-stu-id="d3670-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="d3670-130">Добавьте ссылку в проект <xref:System.ServiceModel> **GettingStartedHost** в сборку:</span><span class="sxs-lookup"><span data-stu-id="d3670-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="d3670-131">В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedHost** , а затем в контекстном меню выберите пункт **Добавить ссылку** .</span><span class="sxs-lookup"><span data-stu-id="d3670-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="d3670-132">В окне **Добавление ссылки** в разделе **сборки** в левой части окна выберите **платформа**.</span><span class="sxs-lookup"><span data-stu-id="d3670-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="d3670-133">Выберите **System. ServiceModel**и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d3670-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="d3670-134">Сохраните решение, выбрав **файл** > **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="d3670-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="d3670-135">Добавление кода для размещения службы</span><span class="sxs-lookup"><span data-stu-id="d3670-135">Add code to host the service</span></span>

<span data-ttu-id="d3670-136">Чтобы разместить службу, добавьте код для выполнения следующих действий.</span><span class="sxs-lookup"><span data-stu-id="d3670-136">To host the service, you add code to do the following steps:</span></span> 

1. <span data-ttu-id="d3670-137">Создайте универсальный код ресурса (URI) для базового адреса.</span><span class="sxs-lookup"><span data-stu-id="d3670-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="d3670-138">Создайте экземпляр класса для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="d3670-139">Создайте конечную точку службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="d3670-140">Включите обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="d3670-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="d3670-141">Откройте узел службы, чтобы прослушивать входящие сообщения.</span><span class="sxs-lookup"><span data-stu-id="d3670-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="d3670-142">Внесите в код следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="d3670-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="d3670-143">Откройте файл **Program.CS** или **Module1. vb** в проекте **GettingStartedHost** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="d3670-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
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
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```
    
    <span data-ttu-id="d3670-144">Сведения о том, как работает этот код, см. в [статье этапы программы размещения службы](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="d3670-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="d3670-145">Обновите свойства проекта:</span><span class="sxs-lookup"><span data-stu-id="d3670-145">Update the project properties:</span></span>

   1. <span data-ttu-id="d3670-146">В окне **Обозреватель решений** выберите папку **GettingStartedHost** , а затем в контекстном меню выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="d3670-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="d3670-147">На странице свойства **GettingStartedHost** выберите вкладку **приложение** :</span><span class="sxs-lookup"><span data-stu-id="d3670-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="d3670-148">Для C# проектов выберите **GettingStartedHost. Program** из списка **автоматически запускаемых объектов** .</span><span class="sxs-lookup"><span data-stu-id="d3670-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="d3670-149">Для Visual Basic проектов выберите **Service. Program** из списка **автоматически запускаемых объектов** .</span><span class="sxs-lookup"><span data-stu-id="d3670-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="d3670-150">В меню **файл** выберите **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="d3670-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="d3670-151">Проверка работоспособности службы</span><span class="sxs-lookup"><span data-stu-id="d3670-151">Verify the service is working</span></span>

1. <span data-ttu-id="d3670-152">Выполните сборку решения, а затем запустите консольное приложение **GettingStartedHost** в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d3670-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="d3670-153">Служба должна запускаться с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="d3670-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="d3670-154">Так как вы открыли Visual Studio с правами администратора, при запуске **GettingStartedHost** в Visual Studio приложение также запускается с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="d3670-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="d3670-155">В качестве альтернативы можно открыть новую командную строку от имени администратора (в контекстном меню выберите **больше** > **запуска от имени администратора** ) и запустить в ней **GettingStartedHost. exe** .</span><span class="sxs-lookup"><span data-stu-id="d3670-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="d3670-156">Откройте веб-браузер и перейдите на страницу службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="d3670-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="d3670-157">Для таких служб требуется разрешение на регистрацию HTTP-адресов на компьютере для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="d3670-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="d3670-158">Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP.</span><span class="sxs-lookup"><span data-stu-id="d3670-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="d3670-159">Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="d3670-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 

## <a name="service-hosting-program-steps"></a><span data-ttu-id="d3670-160">Шаги программы размещения службы</span><span class="sxs-lookup"><span data-stu-id="d3670-160">Service hosting program steps</span></span>

<span data-ttu-id="d3670-161">Шаги в коде, добавленном для размещения службы, описаны ниже.</span><span class="sxs-lookup"><span data-stu-id="d3670-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="d3670-162">**Шаг 1**. Создайте экземпляр `Uri` класса для хранения базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="d3670-163">URL-адрес, содержащий базовый адрес, имеет необязательный URI, идентифицирующий службу.</span><span class="sxs-lookup"><span data-stu-id="d3670-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="d3670-164">Базовый адрес форматируется следующим образом: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span><span class="sxs-lookup"><span data-stu-id="d3670-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="d3670-165">Базовый адрес службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="d3670-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="d3670-166">**Шаг 2**. Создайте экземпляр <xref:System.ServiceModel.ServiceHost> класса, который используется для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="d3670-167">Конструктор принимает два параметра: тип класса, который реализует контракт службы, и базовый адрес службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="d3670-168">**Шаг 3**. Создайте экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="d3670-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="d3670-169">Конечная точка службы состоит из адреса, привязки и контракта службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="d3670-170"><xref:System.ServiceModel.Description.ServiceEndpoint> Конструктор состоит из типа интерфейса контракта службы, привязки и адреса.</span><span class="sxs-lookup"><span data-stu-id="d3670-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="d3670-171">Контракт службы - `ICalculator`. Он определен и реализуется в типе службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="d3670-172">Привязка для этого образца — <xref:System.ServiceModel.WSHttpBinding>это встроенная привязка, которая подключается к конечным точкам, которые соответствуют спецификациям WS-\*.</span><span class="sxs-lookup"><span data-stu-id="d3670-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="d3670-173">Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d3670-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="d3670-174">Добавьте адрес к базовому адресу, чтобы обозначить конечную точку.</span><span class="sxs-lookup"><span data-stu-id="d3670-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="d3670-175">Код определяет адрес как CalculatorService и полный адрес конечной точки как `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="d3670-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d3670-176">Для .NET Framework версии 4 и более поздних версий Добавление конечной точки службы является необязательным.</span><span class="sxs-lookup"><span data-stu-id="d3670-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="d3670-177">В этих версиях, если не добавить код или конфигурацию, WCF добавляет одну конечную точку по умолчанию для каждого сочетания базового адреса и контракта, реализуемого службой.</span><span class="sxs-lookup"><span data-stu-id="d3670-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="d3670-178">Дополнительные сведения о конечных точках по умолчанию см. [в разделе Указание адреса конечной точки](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="d3670-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="d3670-179">Дополнительные сведения о конечных точках, привязках и поведении по умолчанию см. в разделе [упрощенная конфигурация](simplified-configuration.md) и [упрощенная конфигурация для служб WCF](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="d3670-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="d3670-180">**Шаг 4**. Включите обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="d3670-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="d3670-181">Клиенты используют обмен метаданными для создания учетных записей-посредников для вызова операций службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="d3670-182">Чтобы включить обмен метаданными, создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior> экземпляр, присвойте <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> его свойству `true`значение, а `ServiceMetadataBehavior` затем <xref:System.ServiceModel.ServiceHost> добавьте объект <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> в коллекцию экземпляра.</span><span class="sxs-lookup"><span data-stu-id="d3670-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="d3670-183">**Шаг 5**. Откройте <xref:System.ServiceModel.ServiceHost> для прослушивания входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="d3670-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="d3670-184">Приложение ожидает нажатия клавиши **Ввод**.</span><span class="sxs-lookup"><span data-stu-id="d3670-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="d3670-185">После создания экземпляра <xref:System.ServiceModel.ServiceHost>приложения он выполняет блок try/catch.</span><span class="sxs-lookup"><span data-stu-id="d3670-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="d3670-186">Дополнительные сведения о безопасном перехвате исключений <xref:System.ServiceModel.ServiceHost>, создаваемых, см. в разделе [Использование закрытия и прерывания для освобождения ресурсов клиента WCF](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="d3670-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d3670-187">При добавлении библиотеки службы WCF Visual Studio размещает ее для вас при его отладке, запуская узел службы.</span><span class="sxs-lookup"><span data-stu-id="d3670-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="d3670-188">Чтобы избежать конфликтов, можно запретить Visual Studio размещать библиотеку службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d3670-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
>
> 1. <span data-ttu-id="d3670-189">Выберите проект **жеттингстартедлиб** в **Обозреватель решений** и в контекстном меню выберите пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="d3670-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="d3670-190">Выберите **параметры WCF** и снимите флажок **запустить узел службы WCF при отладке другого проекта в том же решении**.</span><span class="sxs-lookup"><span data-stu-id="d3670-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3670-191">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="d3670-191">Next steps</span></span>

<span data-ttu-id="d3670-192">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="d3670-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d3670-193">Создание и Настройка проекта консольного приложения для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d3670-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="d3670-194">Добавьте код для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="d3670-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="d3670-195">Обновите файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d3670-195">Update the configuration file.</span></span>
> - <span data-ttu-id="d3670-196">Запустите службу WCF и убедитесь, что она запущена.</span><span class="sxs-lookup"><span data-stu-id="d3670-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="d3670-197">Перейдите к следующему руководству, чтобы научиться создавать клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="d3670-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d3670-198">Учебник. Создание клиента WCF</span><span class="sxs-lookup"><span data-stu-id="d3670-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
