---
title: Учебник. Создание клиента Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: a16a0ccabfd0f9fbe69db1ea88d4613185f3c1da
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62002083"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="99f1e-102">Учебник. Создание клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="99f1e-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="99f1e-103">В данном учебнике четвертый из пяти шагов, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="99f1e-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="99f1e-104">Обзор руководства, см. в разделе [руководства: Начало работы с приложениями Windows Communication Foundation](getting-started-tutorial.md).</span><span class="sxs-lookup"><span data-stu-id="99f1e-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="99f1e-105">Следующая задача по созданию приложения WCF — для создания клиента путем извлечения метаданных из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="99f1e-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="99f1e-106">Используйте Visual Studio для добавления ссылки на службу, которая получает метаданные из конечной точки службы обмена Метаданными.</span><span class="sxs-lookup"><span data-stu-id="99f1e-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="99f1e-107">Затем Visual Studio создает файл управляемого исходного кода для клиентского прокси на языке, который вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="99f1e-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="99f1e-108">Он также создает файл конфигурации клиента (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="99f1e-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="99f1e-109">Этот файл позволяет клиентскому приложению подключаться к службе в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="99f1e-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="99f1e-110">Если вызов службы WCF из проекта библиотеки классов в Visual Studio, используйте **Add Service Reference** компонентов для автоматического создания прокси-сервера и связанный файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99f1e-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="99f1e-111">Тем не менее, так как библиотеки классов не используют этот файл конфигурации, необходимо добавить параметры в созданный файл конфигурации для *App.config* файл для исполняемого файла, который вызывает библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="99f1e-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="99f1e-112">В качестве альтернативы использовать [средство ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) вместо Visual Studio для создания файла класса и конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="99f1e-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="99f1e-113">Клиентское приложение использует созданный прокси-класс для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="99f1e-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="99f1e-114">Эта процедура описана в [руководства: Использование клиента](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="99f1e-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="99f1e-115">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="99f1e-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="99f1e-116">Создание и настройка проекта консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="99f1e-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="99f1e-117">Добавьте ссылку на службу в службу WCF, чтобы создать файлы класса и конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="99f1e-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="99f1e-118">Создание клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="99f1e-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="99f1e-119">Создание проекта консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="99f1e-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="99f1e-120">Из **файл** меню, выберите **откройте** > **решение или проект** и перейдите к **GettingStarted** решения вы ранее созданный (*GettingStarted.sln*).</span><span class="sxs-lookup"><span data-stu-id="99f1e-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="99f1e-121">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-121">Select **Open**.</span></span>

    2. <span data-ttu-id="99f1e-122">Из **представление** меню, выберите **обозревателе решений**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="99f1e-123">В **обозревателе решений** выберите **GettingStarted** решение (верхний узел), а затем выберите **добавить** > **новый проект** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="99f1e-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="99f1e-124">В **Добавление нового проекта** окно, в левой части окна выберите **Windows Desktop** категорию **Visual C#**  или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="99f1e-125">Выберите **консольное приложение (.NET Framework)** шаблона и введите *GettingStartedClient* для **имя**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="99f1e-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-126">Select **OK**.</span></span>

2. <span data-ttu-id="99f1e-127">Добавьте ссылку в **GettingStartedClient** проект <xref:System.ServiceModel> сборки:</span><span class="sxs-lookup"><span data-stu-id="99f1e-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="99f1e-128">В **обозревателе решений** выберите **ссылки** папке **GettingStartedClient** проекта, а затем выберите **добавить ссылку на** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="99f1e-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="99f1e-129">В **добавить ссылку** окна в разделе **сборки** в левой части окна выберите **Framework**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="99f1e-130">Найдите и выберите **System.ServiceModel**, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="99f1e-131">Сохраните решение, выбрав **файл** > **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="99f1e-132">Добавьте ссылку на службу для службы калькулятора:</span><span class="sxs-lookup"><span data-stu-id="99f1e-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="99f1e-133">В **обозревателе решений** выберите **ссылки** папке **GettingStartedClient** проекта, а затем выберите **Add Service Reference**  в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="99f1e-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="99f1e-134">В **Add Service Reference** выберите **Discover**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="99f1e-135">Запускает службу CalculatorService и Visual Studio отображает его в **служб** поле.</span><span class="sxs-lookup"><span data-stu-id="99f1e-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="99f1e-136">Выберите **CalculatorService** чтобы развернуть ее и отобразить контрактов службы, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="99f1e-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="99f1e-137">Оставьте значение по умолчанию **пространства имен** и выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="99f1e-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="99f1e-138">Visual Studio добавляет новый элемент в разделе **подключенных служб** папку в **GettingStartedClient** проекта.</span><span class="sxs-lookup"><span data-stu-id="99f1e-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="99f1e-139">Средство ServiceModel Metadata Utility</span><span class="sxs-lookup"><span data-stu-id="99f1e-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="99f1e-140">Следующие примеры показывают, как при необходимости использовать [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания файла класса прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="99f1e-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="99f1e-141">Это средство создает файл класса прокси-сервера и *App.config* файл.</span><span class="sxs-lookup"><span data-stu-id="99f1e-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="99f1e-142">Следующие примеры показывают, как для создания прокси-сервера в C# и Visual Basic, соответственно:</span><span class="sxs-lookup"><span data-stu-id="99f1e-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="99f1e-143">Файл конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="99f1e-143">Client configuration file</span></span>

<span data-ttu-id="99f1e-144">После создания клиента, Visual Studio создает **App.config** файл конфигурации в **GettingStartedClient** проект, который должен выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99f1e-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

<span data-ttu-id="99f1e-145">В разделе [ \<system.serviceModel >](../configure-apps/file-schema/wcf/system-servicemodel.md) разделе, обратите внимание, что [ \<конечной точки >](../configure-apps/file-schema/wcf/endpoint-element.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="99f1e-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="99f1e-146">**&lt;Конечной точки&gt;** элемент определяет конечную точку, которую клиент использует для доступа к службе, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="99f1e-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>
- <span data-ttu-id="99f1e-147">Адрес: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="99f1e-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="99f1e-148">Адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="99f1e-148">The address of the endpoint.</span></span>
- <span data-ttu-id="99f1e-149">Контракт службы: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="99f1e-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="99f1e-150">Контракт службы обеспечивает взаимодействие между клиентом WCF и службой.</span><span class="sxs-lookup"><span data-stu-id="99f1e-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="99f1e-151">Visual Studio создается этот контракт, когда вы использовали его **Add Service Reference** функции.</span><span class="sxs-lookup"><span data-stu-id="99f1e-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="99f1e-152">Это по сути копию контракта, которое было определено в проекте GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="99f1e-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="99f1e-153">Привязки: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="99f1e-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="99f1e-154">Привязка задает HTTP в качестве транспорта, безопасности с возможностью взаимодействия и другие сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="99f1e-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="99f1e-155">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="99f1e-155">Next steps</span></span>

<span data-ttu-id="99f1e-156">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="99f1e-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="99f1e-157">Создание и настройка проекта консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="99f1e-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="99f1e-158">Добавьте ссылку на службу в службу WCF, чтобы создать файлы класса и конфигурации прокси-сервера для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="99f1e-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="99f1e-159">Перейдите к следующему руководству, чтобы сведения об использовании созданного клиента.</span><span class="sxs-lookup"><span data-stu-id="99f1e-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="99f1e-160">Учебник. Использование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="99f1e-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
