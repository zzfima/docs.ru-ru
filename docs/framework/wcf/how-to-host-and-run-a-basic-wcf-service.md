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
ms.openlocfilehash: 38fd9b89e2719be8ce4d33b1b50f68171d587369
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410099"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="eacd4-102">Учебник. Размещение и запуск базовой службы Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="eacd4-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="eacd4-103">В данном учебнике третий из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="eacd4-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="eacd4-104">Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="eacd4-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="eacd4-105">Следующая задача по созданию приложения WCF является размещение службы WCF в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="eacd4-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="eacd4-106">Служба WCF предоставляет один или несколько *конечные точки*, каждая из которых предоставляет одну или несколько операций службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="eacd4-107">Конечная точка службы задает следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="eacd4-107">A service endpoint specifies the following information:</span></span> 
- <span data-ttu-id="eacd4-108">Адрес, где можно найти службу.</span><span class="sxs-lookup"><span data-stu-id="eacd4-108">An address where you can find the service.</span></span>
- <span data-ttu-id="eacd4-109">Привязка, которая содержит сведения, описывающие, как клиент должен связаться со службой.</span><span class="sxs-lookup"><span data-stu-id="eacd4-109">A binding that contains the information that describes how a client must communicate with the service.</span></span> 
- <span data-ttu-id="eacd4-110">Контракт, который определяет возможности, которые эта служба предоставляет клиентам.</span><span class="sxs-lookup"><span data-stu-id="eacd4-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="eacd4-111">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="eacd4-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="eacd4-112">Создайте и настройте проект консольного приложения для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="eacd4-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="eacd4-113">Добавьте код для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="eacd4-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="eacd4-114">Обновите файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eacd4-114">Update the configuration file.</span></span>
> - <span data-ttu-id="eacd4-115">Запуск службы WCF и для проверки выполняется.</span><span class="sxs-lookup"><span data-stu-id="eacd4-115">Start the WCF service and verify it's running.</span></span>


## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="eacd4-116">Создание и настройка проекта консольного приложения для размещения службы</span><span class="sxs-lookup"><span data-stu-id="eacd4-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="eacd4-117">Создание проекта консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="eacd4-117">Create a console app project in Visual Studio:</span></span> 
 
    1. <span data-ttu-id="eacd4-118">Из **файл** меню, выберите **откройте** > **решение или проект** и перейдите к **GettingStarted** решения вы ранее созданный (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="eacd4-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="eacd4-119">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-119">Select **Open**.</span></span>

    2. <span data-ttu-id="eacd4-120">Из **представление** меню, выберите **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-120">From the **View** menu, select **Solution Explorer**.</span></span>
    
    3. <span data-ttu-id="eacd4-121">В **обозревателе решений** выберите **GettingStarted** решение (верхний узел), а затем выберите **добавить** > **новый проект** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="eacd4-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 

    4. <span data-ttu-id="eacd4-122">В **Добавление нового проекта** окно, в левой части окна выберите **Windows Desktop** категорию **Visual C#**  или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="eacd4-123">Выберите **консольное приложение (.NET Framework)** шаблона и введите *GettingStartedHost* для **имя**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="eacd4-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-124">Select **OK**.</span></span>

2. <span data-ttu-id="eacd4-125">Добавьте ссылку в **GettingStartedHost** проект **GettingStartedLib** проекта:</span><span class="sxs-lookup"><span data-stu-id="eacd4-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span> 

    1. <span data-ttu-id="eacd4-126">В **обозревателе решений** выберите **ссылки** папке **GettingStartedHost** проекта, а затем выберите **добавить ссылку на** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="eacd4-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="eacd4-127">В **добавить ссылку** диалогового окна в разделе **проекты** в левой части окна выберите **решение**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span> 
 
    3. <span data-ttu-id="eacd4-128">Выберите **GettingStartedLib** в центральной части окна, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span> 

       <span data-ttu-id="eacd4-129">В таком случае типов, определенных в **GettingStartedLib** проекта **GettingStartedHost** проекта.</span><span class="sxs-lookup"><span data-stu-id="eacd4-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="eacd4-130">Добавьте ссылку в **GettingStartedHost** проект <xref:System.ServiceModel> сборки:</span><span class="sxs-lookup"><span data-stu-id="eacd4-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="eacd4-131">В **обозревателе решений** выберите **ссылки** папке **GettingStartedHost** проекта, а затем выберите **добавить ссылку на** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="eacd4-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>
    
    2. <span data-ttu-id="eacd4-132">В **добавить ссылку** окна в разделе **сборки** в левой части окна выберите **Framework**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span> 

    3. <span data-ttu-id="eacd4-133">Выберите **System.ServiceModel**, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-133">Select **System.ServiceModel**, and then select **OK**.</span></span> 
    
    4. <span data-ttu-id="eacd4-134">Сохраните решение, выбрав **файл** > **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="eacd4-135">Добавьте код для размещения службы</span><span class="sxs-lookup"><span data-stu-id="eacd4-135">Add code to host the service</span></span>

<span data-ttu-id="eacd4-136">Чтобы разместить службу, добавьте код для выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="eacd4-136">To host the service, you add code to do the following steps:</span></span> 
   1. <span data-ttu-id="eacd4-137">Создайте URI для базового адреса.</span><span class="sxs-lookup"><span data-stu-id="eacd4-137">Create a URI for the base address.</span></span>
   2. <span data-ttu-id="eacd4-138">Создайте экземпляр класса для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-138">Create a class instance for hosting the service.</span></span>
   3. <span data-ttu-id="eacd4-139">Создайте конечную точку службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-139">Create a service endpoint.</span></span>
   4. <span data-ttu-id="eacd4-140">Включите обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="eacd4-140">Enable metadata exchange.</span></span>
   5. <span data-ttu-id="eacd4-141">Откройте узел службы для прослушивания входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="eacd4-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="eacd4-142">Внесите следующие изменения в код:</span><span class="sxs-lookup"><span data-stu-id="eacd4-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="eacd4-143">Откройте **Program.cs** или **Module1.vb** файл **GettingStartedHost** проекта и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="eacd4-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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
    
    <span data-ttu-id="eacd4-144">Сведения о том, как работает этот код, см. в разделе [службы размещения действия программы](#service-hosting-program-steps).</span><span class="sxs-lookup"><span data-stu-id="eacd4-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>


2. <span data-ttu-id="eacd4-145">Обновите свойства проекта:</span><span class="sxs-lookup"><span data-stu-id="eacd4-145">Update the project properties:</span></span>

   1. <span data-ttu-id="eacd4-146">В **обозревателе решений** выберите **GettingStartedHost** папку, а затем выберите **свойства** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="eacd4-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="eacd4-147">На **GettingStartedHost** странице "Свойства" выберите **приложения** вкладке:</span><span class="sxs-lookup"><span data-stu-id="eacd4-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="eacd4-148">Для C# проектов, выберите **GettingStartedHost.Program** из **автоматически запускаемый объект** списка.</span><span class="sxs-lookup"><span data-stu-id="eacd4-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="eacd4-149">Для проектов Visual Basic, выберите **Service.Program** из **автоматически запускаемый объект** списка.</span><span class="sxs-lookup"><span data-stu-id="eacd4-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="eacd4-150">Из **файл** меню, выберите **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-150">From the **File** menu, select **Save All**.</span></span>


## <a name="verify-the-service-is-working"></a><span data-ttu-id="eacd4-151">Убедитесь, что служба работает</span><span class="sxs-lookup"><span data-stu-id="eacd4-151">Verify the service is working</span></span>

1. <span data-ttu-id="eacd4-152">Выполните сборку решения, а затем запустите **GettingStartedHost** консоли приложению из Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="eacd4-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span> 

    <span data-ttu-id="eacd4-153">Служба должна выполняться с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="eacd4-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="eacd4-154">Так как вы открыли Visual Studio с правами администратора, при запуске **GettingStartedHost** в Visual Studio, приложение запускается с правами администратора, а также.</span><span class="sxs-lookup"><span data-stu-id="eacd4-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="eacd4-155">Кроме того, можно открыть новую командную строку с правами администратора (выберите **дополнительные** > **Запуск от имени администратора** в контекстном меню) и запустите **GettingStartedHost.exe**  внутри него.</span><span class="sxs-lookup"><span data-stu-id="eacd4-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="eacd4-156">Откройте веб-браузер и перейдите на страницу службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="eacd4-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>
   
   > [!NOTE]
   > <span data-ttu-id="eacd4-157">Подобные службы требуют необходимое разрешение на регистрацию HTTP-адресов на компьютере для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="eacd4-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="eacd4-158">Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP.</span><span class="sxs-lookup"><span data-stu-id="eacd4-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="eacd4-159">Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="eacd4-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span> 


## <a name="service-hosting-program-steps"></a><span data-ttu-id="eacd4-160">Службы размещения действия программы</span><span class="sxs-lookup"><span data-stu-id="eacd4-160">Service hosting program steps</span></span>

<span data-ttu-id="eacd4-161">Действия, описанные в код, добавленный к узлу службы из них описаны, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="eacd4-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="eacd4-162">**Шаг 1**: Создайте экземпляр `Uri` класса, содержащего базовый адрес службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="eacd4-163">URL-адрес, содержащий базовый адрес имеет дополнительный URI, который идентифицирует службу.</span><span class="sxs-lookup"><span data-stu-id="eacd4-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="eacd4-164">Базовый адрес имеет следующий формат: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span><span class="sxs-lookup"><span data-stu-id="eacd4-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="eacd4-165">Базовый адрес для службы калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI, GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="eacd4-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="eacd4-166">**Шаг 2**: Создайте экземпляр <xref:System.ServiceModel.ServiceHost> класс, который можно использовать для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="eacd4-167">Конструктор принимает два параметра: тип класса, который реализует контракт службы и базовый адрес службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="eacd4-168">**Шаг 3**: Создайте экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint>.</span><span class="sxs-lookup"><span data-stu-id="eacd4-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="eacd4-169">Конечная точка службы состоит из адреса, привязки и контракта службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="eacd4-170"><xref:System.ServiceModel.Description.ServiceEndpoint> Конструктора представляет собой тип интерфейса контракта службы, привязку и адрес.</span><span class="sxs-lookup"><span data-stu-id="eacd4-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="eacd4-171">Контракт службы - `ICalculator`. Он определен и реализуется в типе службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="eacd4-172">Привязка для этого примера является <xref:System.ServiceModel.WSHttpBinding>, который является встроенных привязок и подключается к конечным точкам, соответствующим WS-\* спецификации.</span><span class="sxs-lookup"><span data-stu-id="eacd4-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="eacd4-173">Дополнительные сведения о привязках WCF см. в разделе [Общие сведения о привязках WCF](bindings-overview.md).</span><span class="sxs-lookup"><span data-stu-id="eacd4-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="eacd4-174">Добавить адрес базового адреса для идентификации этой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="eacd4-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="eacd4-175">Код указывает адрес как CalculatorService и полного адреса конечной точки как `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="eacd4-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="eacd4-176">.NET Framework версии 4 и более поздних версий Добавление конечной точки службы является необязательным.</span><span class="sxs-lookup"><span data-stu-id="eacd4-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="eacd4-177">Для этих версий Если вы не добавите кода или конфигурации, WCF добавляет одну конечную точку по умолчанию для каждого сочетания базового адреса и контракта, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="eacd4-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="eacd4-178">Дополнительные сведения о конечных точках по умолчанию, см. в разделе [Задание адреса конечной точки](specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="eacd4-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="eacd4-179">Дополнительные сведения о конечных точках по умолчанию, привязках и поведениях см. в разделе [Упрощенная конфигурация](simplified-configuration.md) и [Упрощенная конфигурация служб WCF](samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="eacd4-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="eacd4-180">**Шаг 4**: Включите обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="eacd4-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="eacd4-181">Клиенты используют обмена метаданными создавать прокси для вызова операций службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="eacd4-182">Чтобы включить обмен метаданными, создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior> экземпляра, установите его <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> свойства `true`и добавьте `ServiceMetadataBehavior` объект <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> коллекцию <xref:System.ServiceModel.ServiceHost> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="eacd4-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="eacd4-183">**Шаг 5**: Откройте <xref:System.ServiceModel.ServiceHost> для прослушивания входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="eacd4-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="eacd4-184">Приложение ожидает нажатия клавиш **ввод**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="eacd4-185">После приложение создает экземпляр <xref:System.ServiceModel.ServiceHost>, он выполняет блок try/catch.</span><span class="sxs-lookup"><span data-stu-id="eacd4-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="eacd4-186">Дополнительные сведения о перехвате исключений, создаваемых <xref:System.ServiceModel.ServiceHost>, см. в разделе [используйте Close и Abort для освобождения ресурсов клиента WCF](samples/use-close-abort-release-wcf-client-resources.md).</span><span class="sxs-lookup"><span data-stu-id="eacd4-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eacd4-187">При добавлении библиотеки службы WCF, Visual Studio размещает ее автоматически при отладке путем запуска узла службы.</span><span class="sxs-lookup"><span data-stu-id="eacd4-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="eacd4-188">Во избежание конфликтов можно запретить Visual Studio, на котором размещается в библиотеке служб WCF.</span><span class="sxs-lookup"><span data-stu-id="eacd4-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span> 
> 1. <span data-ttu-id="eacd4-189">Выберите **GettingStartedLib** в проекте **обозревателе решений** и выберите **свойства** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="eacd4-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="eacd4-190">Выберите **параметры WCF** и снимите флажок **запуск узла службы WCF при отладке другого проекта в одном решении**.</span><span class="sxs-lookup"><span data-stu-id="eacd4-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>


## <a name="next-steps"></a><span data-ttu-id="eacd4-191">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="eacd4-191">Next steps</span></span>

<span data-ttu-id="eacd4-192">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="eacd4-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="eacd4-193">Создайте и настройте проект консольного приложения для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="eacd4-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="eacd4-194">Добавьте код для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="eacd4-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="eacd4-195">Обновите файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eacd4-195">Update the configuration file.</span></span>
> - <span data-ttu-id="eacd4-196">Запуск службы WCF и для проверки выполняется.</span><span class="sxs-lookup"><span data-stu-id="eacd4-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="eacd4-197">Перейдите к следующему руководству, чтобы узнать, как создать клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="eacd4-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="eacd4-198">Учебник. Создание клиента WCF</span><span class="sxs-lookup"><span data-stu-id="eacd4-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
