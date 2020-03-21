---
title: 'Учебник: Хост и запуск базового сервиса Windows Communication Foundation'
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184081"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a><span data-ttu-id="744b5-102">Учебник: Хост и запуск базового сервиса Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="744b5-102">Tutorial: Host and run a basic Windows Communication Foundation service</span></span>

<span data-ttu-id="744b5-103">В этом уроке описаны третья из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="744b5-103">This tutorial describes the third of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="744b5-104">Для обзора учебников [см.](getting-started-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="744b5-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="744b5-105">Следующей задачей для создания приложения WCF является размещение wCF-сервиса в консольном приложении.</span><span class="sxs-lookup"><span data-stu-id="744b5-105">The next task for creating a WCF application is to host a WCF service in a console application.</span></span> <span data-ttu-id="744b5-106">Служба WCF предоставляет одну или несколько *конечных точек,* каждая из которых предоставляет одну или несколько операций службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-106">A WCF service exposes one or more *endpoints*, each of which exposes one or more service operations.</span></span> <span data-ttu-id="744b5-107">Конечная точка службы определяет следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="744b5-107">A service endpoint specifies the following information:</span></span>

- <span data-ttu-id="744b5-108">Адрес, по которому можно найти услугу.</span><span class="sxs-lookup"><span data-stu-id="744b5-108">An address where you can find the service.</span></span>
- <span data-ttu-id="744b5-109">Привязка, содержащая информацию, описывающую, как клиент должен общаться с службой.</span><span class="sxs-lookup"><span data-stu-id="744b5-109">A binding that contains the information that describes how a client must communicate with the service.</span></span>
- <span data-ttu-id="744b5-110">Контракт, определяющий функциональность, которую служба предоставляет своим клиентам.</span><span class="sxs-lookup"><span data-stu-id="744b5-110">A contract that defines the functionality that the service provides to its clients.</span></span>

<span data-ttu-id="744b5-111">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="744b5-111">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="744b5-112">Создайте и настройте проект консольного приложения для размещения сервиса WCF.</span><span class="sxs-lookup"><span data-stu-id="744b5-112">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="744b5-113">Добавьте код для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="744b5-113">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="744b5-114">Обновление файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="744b5-114">Update the configuration file.</span></span>
> - <span data-ttu-id="744b5-115">Запустите службу WCF и проверьте, что она работает.</span><span class="sxs-lookup"><span data-stu-id="744b5-115">Start the WCF service and verify it's running.</span></span>

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a><span data-ttu-id="744b5-116">Создание и настройка проекта консольного приложения для хостинга сервиса</span><span class="sxs-lookup"><span data-stu-id="744b5-116">Create and configure a console app project for hosting the service</span></span>

1. <span data-ttu-id="744b5-117">Создайте проект консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="744b5-117">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="744b5-118">Из меню **файла** выберите **Open** > **Project/Solution** и просмотрите ранее созданное решение **GettingStarted** *(GettingStarted.sln).*</span><span class="sxs-lookup"><span data-stu-id="744b5-118">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="744b5-119">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="744b5-119">Select **Open**.</span></span>

    2. <span data-ttu-id="744b5-120">Из меню **View** выберите **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="744b5-120">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="744b5-121">В окне **Solution Explorer** выберите решение **GettingStarted** (верхний узло), а затем выберите **Добавить** > **новый проект** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="744b5-121">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="744b5-122">В окне **Добавить новый проект,** на левой стороне, выберите категорию **Windows Desktop** под **Visual C или** Visual **Basic**.</span><span class="sxs-lookup"><span data-stu-id="744b5-122">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="744b5-123">Выберите шаблон **Console App (.NET Framework)** и введите *GettingStartedHost* для **name.**</span><span class="sxs-lookup"><span data-stu-id="744b5-123">Select the **Console App (.NET Framework)** template, and enter *GettingStartedHost* for the **Name**.</span></span> <span data-ttu-id="744b5-124">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="744b5-124">Select **OK**.</span></span>

2. <span data-ttu-id="744b5-125">Добавьте ссылку в проект **gettingStartedHost** в проект **GettingStartedLib:**</span><span class="sxs-lookup"><span data-stu-id="744b5-125">Add a reference in the **GettingStartedHost** project to the **GettingStartedLib** project:</span></span>

    1. <span data-ttu-id="744b5-126">В окне **Solution Explorer** выберите папку **«Ссылки»** в рамках проекта **GettingStartedHost,** а затем выберите **«Добавить ссылку»** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="744b5-126">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="744b5-127">В диалоге **Add Reference** под **проектами** на левой стороне окна выберите **решение.**</span><span class="sxs-lookup"><span data-stu-id="744b5-127">In the **Add Reference** dialog, under **Projects** on the left side of the window, select **Solution**.</span></span>

    3. <span data-ttu-id="744b5-128">Выберите **GettingStartedLib** в центральной части окна, а затем выберите **OK.**</span><span class="sxs-lookup"><span data-stu-id="744b5-128">Select **GettingStartedLib** in the center section of the window, and then select **OK**.</span></span>

       <span data-ttu-id="744b5-129">Это действие делает типы, определенные в проекте **GettingStartedLib,** доступными для проекта **GettingStartedHost.**</span><span class="sxs-lookup"><span data-stu-id="744b5-129">This action makes the types defined in the **GettingStartedLib** project available to the **GettingStartedHost** project.</span></span>

3. <span data-ttu-id="744b5-130">Добавьте ссылку в проект **gettingStartedHost** в сборку: <xref:System.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="744b5-130">Add a reference in the **GettingStartedHost** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="744b5-131">В окне **Solution Explorer** выберите папку **«Ссылки»** в рамках проекта **GettingStartedHost,** а затем выберите **«Добавить ссылку»** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="744b5-131">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedHost** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="744b5-132">В окне **справки Добавить** под **сборками** на левой стороне окна выберите **Framework**.</span><span class="sxs-lookup"><span data-stu-id="744b5-132">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="744b5-133">Выберите **System.ServiceModel**, а затем выберите **OK**.</span><span class="sxs-lookup"><span data-stu-id="744b5-133">Select **System.ServiceModel**, and then select **OK**.</span></span>

    4. <span data-ttu-id="744b5-134">Сохранить решение, выбрав **файл** > **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="744b5-134">Save the solution by selecting **File** > **Save All**.</span></span>

## <a name="add-code-to-host-the-service"></a><span data-ttu-id="744b5-135">Добавление кода для размещения службы</span><span class="sxs-lookup"><span data-stu-id="744b5-135">Add code to host the service</span></span>

<span data-ttu-id="744b5-136">Чтобы разместить службу, вы добавляете код для следующих шагов:</span><span class="sxs-lookup"><span data-stu-id="744b5-136">To host the service, you add code to do the following steps:</span></span>

1. <span data-ttu-id="744b5-137">Создайте URI для базового адреса.</span><span class="sxs-lookup"><span data-stu-id="744b5-137">Create a URI for the base address.</span></span>
2. <span data-ttu-id="744b5-138">Создайте экземпляр класса для хостинга службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-138">Create a class instance for hosting the service.</span></span>
3. <span data-ttu-id="744b5-139">Создайте конечную точку обслуживания.</span><span class="sxs-lookup"><span data-stu-id="744b5-139">Create a service endpoint.</span></span>
4. <span data-ttu-id="744b5-140">Включите обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="744b5-140">Enable metadata exchange.</span></span>
5. <span data-ttu-id="744b5-141">Откройте услик службы для прослушивания входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="744b5-141">Open the service host to listen for incoming messages.</span></span>
  
<span data-ttu-id="744b5-142">Внесите следующие изменения в код:</span><span class="sxs-lookup"><span data-stu-id="744b5-142">Make the following changes to the code:</span></span>

1. <span data-ttu-id="744b5-143">Откройте файл **Program.cs** или **Module1.vb** в проекте **GettingStartedHost** и замените его код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="744b5-143">Open the **Program.cs** or **Module1.vb** file in the **GettingStartedHost** project and replace its code with the following code:</span></span>

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

    <span data-ttu-id="744b5-144">Для получения информации о [Service hosting program steps](#service-hosting-program-steps)том, как работает этот код, см.</span><span class="sxs-lookup"><span data-stu-id="744b5-144">For information about how this code works, see [Service hosting program steps](#service-hosting-program-steps).</span></span>

2. <span data-ttu-id="744b5-145">Обновление свойств проекта:</span><span class="sxs-lookup"><span data-stu-id="744b5-145">Update the project properties:</span></span>

   1. <span data-ttu-id="744b5-146">В окне **Solution Explorer** выберите папку **GettingStartedHost,** а затем выберите **свойства** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="744b5-146">In the **Solution Explorer** window, select the **GettingStartedHost** folder, and then select **Properties** from the shortcut menu.</span></span>

   2. <span data-ttu-id="744b5-147">На странице свойств **GettingStartedHost** выберите вкладку **Приложения:**</span><span class="sxs-lookup"><span data-stu-id="744b5-147">On the **GettingStartedHost** properties page, select the **Application** tab:</span></span>

      - <span data-ttu-id="744b5-148">Для проектов с c, выберите **GettingStartedHost.Program** из списка **объектов запуска.**</span><span class="sxs-lookup"><span data-stu-id="744b5-148">For C# projects, select **GettingStartedHost.Program** from the **Startup object** list.</span></span>

      - <span data-ttu-id="744b5-149">Для проектов Visual Basic выберите **Service.Program** из списка **объектов запуска.**</span><span class="sxs-lookup"><span data-stu-id="744b5-149">For Visual Basic projects, select **Service.Program** from the **Startup object** list.</span></span>

   3. <span data-ttu-id="744b5-150">Из меню **файла** выберите **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="744b5-150">From the **File** menu, select **Save All**.</span></span>

## <a name="verify-the-service-is-working"></a><span data-ttu-id="744b5-151">Проверка работы службы</span><span class="sxs-lookup"><span data-stu-id="744b5-151">Verify the service is working</span></span>

1. <span data-ttu-id="744b5-152">Создайте решение, а затем запустите консольное приложение **GettingStartedHost** из нутри Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="744b5-152">Build the solution, and then run the **GettingStartedHost** console application from inside Visual Studio.</span></span>

    <span data-ttu-id="744b5-153">Служба должна работать с привилегиями администратора.</span><span class="sxs-lookup"><span data-stu-id="744b5-153">The service must be run with administrator privileges.</span></span> <span data-ttu-id="744b5-154">Поскольку вы открыли Visual Studio с привилегиями администратора, при запуске **GettingStartedHost** в Visual Studio приложение также работает с привилегиями администратора.</span><span class="sxs-lookup"><span data-stu-id="744b5-154">Because you opened Visual Studio with administrator privileges, when you run **GettingStartedHost** in Visual Studio, the application is run with administrator privileges as well.</span></span> <span data-ttu-id="744b5-155">В качестве альтернативы можно открыть новую запросную команду в качестве администратора (выберите **More** > Run в**качестве администратора** из меню ярлыка) и запустить **GettingStartedHost.exe** в нем.</span><span class="sxs-lookup"><span data-stu-id="744b5-155">As an alternative, you can open a new command prompt as an administrator (select **More** > **Run as administrator** from the shortcut menu) and run **GettingStartedHost.exe** within it.</span></span>

2. <span data-ttu-id="744b5-156">Откройте веб-браузер и просмотрите страницу службы по адресу `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="744b5-156">Open a web browser and browse to the service's page at `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="744b5-157">Службы, подобные этой, требуют надлежащего разрешения на регистрацию адресов HTTP на машине для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="744b5-157">Services such as this one require the proper permission to register HTTP addresses on the machine for listening.</span></span> <span data-ttu-id="744b5-158">Учетные записи с уровнем доступа администратора имеют данное разрешение, а остальным учетным записям должно быть предоставлено разрешение на использование пространства имен HTTP.</span><span class="sxs-lookup"><span data-stu-id="744b5-158">Administrator accounts have this permission, but non-administrator accounts must be granted permission for HTTP namespaces.</span></span> <span data-ttu-id="744b5-159">Дополнительные сведения о настройке резервирования пространств имен см. в разделе [Настройка протоколов HTTP и HTTPS](feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="744b5-159">For more information about how to configure namespace reservations, see [Configuring HTTP and HTTPS](feature-details/configuring-http-and-https.md).</span></span>

## <a name="service-hosting-program-steps"></a><span data-ttu-id="744b5-160">Шаги программы хостинга сервиса</span><span class="sxs-lookup"><span data-stu-id="744b5-160">Service hosting program steps</span></span>

<span data-ttu-id="744b5-161">Шаги в коде, добавленном для размещения службы, описаны следующим образом:</span><span class="sxs-lookup"><span data-stu-id="744b5-161">The steps in the code you added to host the service are described as follows:</span></span>

- <span data-ttu-id="744b5-162">**Шаг 1**: Создайте `Uri` экземпляр класса для удержания базового адреса службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-162">**Step 1**: Create an instance of the `Uri` class to hold the base address of the service.</span></span> <span data-ttu-id="744b5-163">URL-адрес, содержащий базовый адрес, имеет дополнительный URI, который идентифицирует службу.</span><span class="sxs-lookup"><span data-stu-id="744b5-163">A URL that contains a base address has an optional URI that identifies a service.</span></span> <span data-ttu-id="744b5-164">Базовый адрес отформатирован `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`следующим образом: .</span><span class="sxs-lookup"><span data-stu-id="744b5-164">The base address is formatted as follows: `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`.</span></span> <span data-ttu-id="744b5-165">Базовый адрес услуги калькулятора использует транспорт HTTP, localhost, порт 8000 и сегмент URI, GettingStarted.</span><span class="sxs-lookup"><span data-stu-id="744b5-165">The base address for the calculator service uses the HTTP transport, localhost, port 8000, and the URI segment, GettingStarted.</span></span>

- <span data-ttu-id="744b5-166">**Шаг 2**: Создайте <xref:System.ServiceModel.ServiceHost> экземпляр класса, который используется для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-166">**Step 2**: Create an instance of the <xref:System.ServiceModel.ServiceHost> class, which you use to host the service.</span></span> <span data-ttu-id="744b5-167">Конструктор принимает два параметра: тип класса, который реализует контракт на обслуживание, и базовый адрес службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-167">The constructor takes two parameters: the type of the class that implements the service contract and the base address of the service.</span></span>

- <span data-ttu-id="744b5-168">**Шаг 3**: <xref:System.ServiceModel.Description.ServiceEndpoint> Создайте экземпляр.</span><span class="sxs-lookup"><span data-stu-id="744b5-168">**Step 3**: Create a <xref:System.ServiceModel.Description.ServiceEndpoint> instance.</span></span> <span data-ttu-id="744b5-169">Конечная точка службы состоит из адреса, привязки и контракта службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-169">A service endpoint is composed of an address, a binding, and a service contract.</span></span> <span data-ttu-id="744b5-170">Конструктор <xref:System.ServiceModel.Description.ServiceEndpoint> состоит из типа интерфейса контракта службы, привязки и адреса.</span><span class="sxs-lookup"><span data-stu-id="744b5-170">The <xref:System.ServiceModel.Description.ServiceEndpoint> constructor is composed of the service contract interface type, a binding, and an address.</span></span> <span data-ttu-id="744b5-171">Контракт службы - `ICalculator`. Он определен и реализуется в типе службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-171">The service contract is `ICalculator`, which you defined and implement in the service type.</span></span> <span data-ttu-id="744b5-172">Привязка для <xref:System.ServiceModel.WSHttpBinding>этого образца, которая является встроенной привязкой и подключается к конечным точкам, которые соответствуют спецификациям WS-'.</span><span class="sxs-lookup"><span data-stu-id="744b5-172">The binding for this sample is <xref:System.ServiceModel.WSHttpBinding>, which is a built-in binding and connects to endpoints that conform to the WS-\* specifications.</span></span> <span data-ttu-id="744b5-173">Для получения дополнительной информации о привязки WCF, [см.](bindings-overview.md)</span><span class="sxs-lookup"><span data-stu-id="744b5-173">For more information about WCF bindings, see [WCF bindings overview](bindings-overview.md).</span></span> <span data-ttu-id="744b5-174">Вы приговыте адрес к базовому адресу, чтобы определить конечную точку.</span><span class="sxs-lookup"><span data-stu-id="744b5-174">You append the address to the base address to identify the endpoint.</span></span> <span data-ttu-id="744b5-175">Код определяет адрес как CalculatorService и полностью квалифицированный адрес `http://localhost:8000/GettingStarted/CalculatorService`для конечных точек как.</span><span class="sxs-lookup"><span data-stu-id="744b5-175">The code specifies the address as CalculatorService and the fully qualified address for the endpoint as `http://localhost:8000/GettingStarted/CalculatorService`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="744b5-176">Для .NET Framework Version 4 и позже добавление конечная точка обслуживания не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="744b5-176">For .NET Framework Version 4 and later, adding a service endpoint is optional.</span></span> <span data-ttu-id="744b5-177">Для этих версий, если вы не добавляете свой код или конфигурацию, WCF добавляет одну конечную точку по умолчанию для каждой комбинации базового адреса и контракта, реализованного службой.</span><span class="sxs-lookup"><span data-stu-id="744b5-177">For these versions, if you don't add your code or configuration, WCF adds one default endpoint for each combination of base address and contract implemented by the service.</span></span> <span data-ttu-id="744b5-178">Для получения дополнительной информации о конечных точках по умолчанию [см.](specifying-an-endpoint-address.md)</span><span class="sxs-lookup"><span data-stu-id="744b5-178">For more information about default endpoints, see [Specifying an endpoint address](specifying-an-endpoint-address.md).</span></span> <span data-ttu-id="744b5-179">Для получения дополнительной информации о конечных точках по умолчанию, привязки и поведении [см. Упрощенная конфигурация](simplified-configuration.md) и [упрощенная конфигурация для служб WCF.](samples/simplified-configuration-for-wcf-services.md)</span><span class="sxs-lookup"><span data-stu-id="744b5-179">For more information about default endpoints, bindings, and behaviors, see [Simplified configuration](simplified-configuration.md) and [Simplified configuration for WCF services](samples/simplified-configuration-for-wcf-services.md).</span></span>

- <span data-ttu-id="744b5-180">**Шаг 4**: Включить обмен метаданными.</span><span class="sxs-lookup"><span data-stu-id="744b5-180">**Step 4**: Enable metadata exchange.</span></span> <span data-ttu-id="744b5-181">Клиенты используют обмен метаданными для генерации прокси-сервисов для вызова службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-181">Clients use metadata exchange to generate proxies for calling the service operations.</span></span> <span data-ttu-id="744b5-182">Для обеспечения обмена метаданными <xref:System.ServiceModel.Description.ServiceMetadataBehavior> создайте <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> экземпляр, установите `ServiceMetadataBehavior` его <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> свойство `true` <xref:System.ServiceModel.ServiceHost> и добавьте объект в сбор экземпляра.</span><span class="sxs-lookup"><span data-stu-id="744b5-182">To enable metadata exchange, create a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance, set its <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled> property to `true`, and add the `ServiceMetadataBehavior` object to the <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> collection of the <xref:System.ServiceModel.ServiceHost> instance.</span></span>

- <span data-ttu-id="744b5-183">**Шаг 5** <xref:System.ServiceModel.ServiceHost> : Открыть для прослушивания входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="744b5-183">**Step 5**: Open <xref:System.ServiceModel.ServiceHost> to listen for incoming messages.</span></span> <span data-ttu-id="744b5-184">Приложение ждет вас, чтобы нажать **Enter**.</span><span class="sxs-lookup"><span data-stu-id="744b5-184">The application waits for you to press **Enter**.</span></span> <span data-ttu-id="744b5-185">После мгновенного <xref:System.ServiceModel.ServiceHost>приложения, он выполняет попробовать / поймать блок.</span><span class="sxs-lookup"><span data-stu-id="744b5-185">After the application instantiates <xref:System.ServiceModel.ServiceHost>, it executes a try/catch block.</span></span> <span data-ttu-id="744b5-186">Для получения дополнительной информации о <xref:System.ServiceModel.ServiceHost>безопасной ловле исключений, брошенных, см. [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md)</span><span class="sxs-lookup"><span data-stu-id="744b5-186">For more information about safely catching exceptions thrown by <xref:System.ServiceModel.ServiceHost>, see [Use Close and Abort to release WCF client resources](samples/use-close-abort-release-wcf-client-resources.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="744b5-187">При добавлении библиотеки обслуживания WCF Visual Studio принимает ее для вас, если вы отладите ее, забрав усваиватель службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-187">When you add a WCF service library, Visual Studio hosts it for you if you debug it by starting a service host.</span></span> <span data-ttu-id="744b5-188">Чтобы избежать конфликтов, вы можете предотвратить Visual Studio от размещения библиотеки wCF службы.</span><span class="sxs-lookup"><span data-stu-id="744b5-188">To avoid conflicts, you can prevent Visual Studio from hosting the WCF service library.</span></span>
>
> 1. <span data-ttu-id="744b5-189">Выберите проект **GettingStartedLib** в **Solution Explorer** и выберите **свойства** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="744b5-189">Select the **GettingStartedLib** project in **Solution Explorer** and choose **Properties** from the shortcut menu.</span></span>
> 2. <span data-ttu-id="744b5-190">Выберите **параметры WCF** и отрежь **от запуска wCF Service Host при отладке другого проекта в том же решении.**</span><span class="sxs-lookup"><span data-stu-id="744b5-190">Select **WCF Options** and uncheck **Start WCF Service Host when debugging another project in the same solution**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="744b5-191">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="744b5-191">Next steps</span></span>

<span data-ttu-id="744b5-192">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="744b5-192">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="744b5-193">Создайте и настройте проект консольного приложения для размещения сервиса WCF.</span><span class="sxs-lookup"><span data-stu-id="744b5-193">Create and configure a console app project for hosting a WCF service.</span></span>
> - <span data-ttu-id="744b5-194">Добавьте код для размещения службы WCF.</span><span class="sxs-lookup"><span data-stu-id="744b5-194">Add code to host the WCF service.</span></span>
> - <span data-ttu-id="744b5-195">Обновление файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="744b5-195">Update the configuration file.</span></span>
> - <span data-ttu-id="744b5-196">Запустите службу WCF и проверьте, что она работает.</span><span class="sxs-lookup"><span data-stu-id="744b5-196">Start the WCF service and verify it's running.</span></span>

<span data-ttu-id="744b5-197">Перейти к следующему учебнику, чтобы узнать, как создать клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="744b5-197">Advance to the next tutorial to learn how to create a WCF client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="744b5-198">Учебник: Создание клиента WCF</span><span class="sxs-lookup"><span data-stu-id="744b5-198">Tutorial: Create a WCF client</span></span>](how-to-create-a-wcf-client.md)
