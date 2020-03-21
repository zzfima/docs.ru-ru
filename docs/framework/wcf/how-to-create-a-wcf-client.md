---
title: 'Учебник: Создание клиента Фонда коммуникации Windows'
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184101"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="bca9d-102">Учебник: Создание клиента Фонда коммуникации Windows</span><span class="sxs-lookup"><span data-stu-id="bca9d-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="bca9d-103">В этом уроке описаны четвертая из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bca9d-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="bca9d-104">Для обзора учебников [см.](getting-started-tutorial.md)</span><span class="sxs-lookup"><span data-stu-id="bca9d-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="bca9d-105">Следующей задачей для создания приложения WCF является создание клиента путем извлечения метаданных из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="bca9d-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="bca9d-106">Вы используете Visual Studio для добавления справочника по обслуживанию, который получает метаданные из конечных точек службы MEX.</span><span class="sxs-lookup"><span data-stu-id="bca9d-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="bca9d-107">Visual Studio затем генерирует управляемый файл исходного кода для клиентского прокси на выбранном языке.</span><span class="sxs-lookup"><span data-stu-id="bca9d-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="bca9d-108">Он также создает файл конфигурации клиента (*App.config*).</span><span class="sxs-lookup"><span data-stu-id="bca9d-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="bca9d-109">Этот файл позволяет клиенту приложение подключиться к службе в конечном пункте.</span><span class="sxs-lookup"><span data-stu-id="bca9d-109">This file enables the client application to connect to the service at an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="bca9d-110">Если вы вызываете службу WCF из проекта библиотеки класса в Visual Studio, используйте функцию **справки об обслуживании Add** для автоматического создания прокси-файла и связанного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bca9d-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="bca9d-111">Однако, поскольку проекты библиотеки классов не используют этот файл конфигурации, необходимо добавить настройки в файл сгенерированной конфигурации в файл *App.config* для исполняемой библиотеки класса.</span><span class="sxs-lookup"><span data-stu-id="bca9d-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="bca9d-112">В качестве альтернативы используйте [инструмент ServiceModel Metadata Utility](#servicemodel-metadata-utility-tool) вместо Visual Studio для генерации файла прокси-класса и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bca9d-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="bca9d-113">Клиентское приложение использует созданный прокси-класс для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="bca9d-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="bca9d-114">Эта процедура описана в [учебнике: Используйте клиента.](how-to-use-a-wcf-client.md)</span><span class="sxs-lookup"><span data-stu-id="bca9d-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="bca9d-115">В этом руководстве описано следующее:</span><span class="sxs-lookup"><span data-stu-id="bca9d-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bca9d-116">Создайте и назначайте проект консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="bca9d-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="bca9d-117">Добавьте ссылку на службу WCF для генерации файлов прокси-класса и конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bca9d-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="bca9d-118">Создание клиента Фонда коммуникаций Windows</span><span class="sxs-lookup"><span data-stu-id="bca9d-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="bca9d-119">Создайте проект консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="bca9d-119">Create a console app project in Visual Studio:</span></span>

    1. <span data-ttu-id="bca9d-120">Из меню **файла** выберите **Open** > **Project/Solution** и просмотрите ранее созданное решение **GettingStarted** *(GettingStarted.sln).*</span><span class="sxs-lookup"><span data-stu-id="bca9d-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="bca9d-121">Выберите **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-121">Select **Open**.</span></span>

    2. <span data-ttu-id="bca9d-122">Из меню **View** выберите **Solution Explorer**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="bca9d-123">В окне **Solution Explorer** выберите решение **GettingStarted** (верхний узло), а затем выберите **Добавить** > **новый проект** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="bca9d-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span>

    4. <span data-ttu-id="bca9d-124">В окне **Добавить новый проект,** на левой стороне, выберите категорию **Windows Desktop** под **Visual C или** Visual **Basic**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span>

    5. <span data-ttu-id="bca9d-125">Выберите шаблон **Console App (.NET Framework)** и введите *GettingStartedClient* для **name**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="bca9d-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-126">Select **OK**.</span></span>

2. <span data-ttu-id="bca9d-127">Добавьте ссылку в проект **gettingStartedClient** к сборке: <xref:System.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bca9d-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span>

    1. <span data-ttu-id="bca9d-128">В окне **Solution Explorer** выберите папку **«Ссылки»** в проекте **GettingStartedClient,** а затем выберите **«Добавить ссылку»** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="bca9d-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span>

    2. <span data-ttu-id="bca9d-129">В окне **справки Добавить** под **сборками** на левой стороне окна выберите **Framework**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>

    3. <span data-ttu-id="bca9d-130">Найти и выбрать **System.ServiceModel**, а затем выбрать **OK**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span>

    4. <span data-ttu-id="bca9d-131">Сохранить решение, выбрав **файл** > **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="bca9d-132">Добавьте ссылку на услугу в службу калькулятора:</span><span class="sxs-lookup"><span data-stu-id="bca9d-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="bca9d-133">В окне **Solution Explorer** выберите папку **«Ссылки»** в проекте **GettingStartedClient,** а затем выберите Ссылку на **службу** из меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="bca9d-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="bca9d-134">В окне **справки об услугах Добавить** выберите **Discover**.</span><span class="sxs-lookup"><span data-stu-id="bca9d-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="bca9d-135">Запускается сервис CalculatorService, и Visual Studio отображает его в окне **Услуг.**</span><span class="sxs-lookup"><span data-stu-id="bca9d-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="bca9d-136">Выберите **CalculatorService,** чтобы расширить его и отобразить сервисные контракты, реализованные службой.</span><span class="sxs-lookup"><span data-stu-id="bca9d-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="bca9d-137">Оставьте **пространство имен** по умолчанию и выберите **OK.**</span><span class="sxs-lookup"><span data-stu-id="bca9d-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="bca9d-138">Visual Studio добавляет новый элемент в папку **«Подключенные услуги»** в проекте **GettingStartedClient.**</span><span class="sxs-lookup"><span data-stu-id="bca9d-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span>

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="bca9d-139">СервисМодель Метаданные Утилита инструмент</span><span class="sxs-lookup"><span data-stu-id="bca9d-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="bca9d-140">Ниже приведены следующие примеры, как дополнительно использовать [инструмент ServiceModel Metadata Utility (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для генерации файла класса прокси.</span><span class="sxs-lookup"><span data-stu-id="bca9d-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="bca9d-141">Этот инструмент генерирует файл класса прокси и файл *App.config.*</span><span class="sxs-lookup"><span data-stu-id="bca9d-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="bca9d-142">Следующие примеры показывают, как создать прокси в C и Visual Basic, соответственно:</span><span class="sxs-lookup"><span data-stu-id="bca9d-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="bca9d-143">Файл конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="bca9d-143">Client configuration file</span></span>

<span data-ttu-id="bca9d-144">После создания клиента Visual Studio создает файл конфигурации **App.config** в проекте **GettingStartedClient,** который должен быть похож на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="bca9d-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="bca9d-145">В разделе [ \<system.serviceModel>,](../configure-apps/file-schema/wcf/system-servicemodel.md) обратите внимание на [ \<элемент endpoint>.](../configure-apps/file-schema/wcf/endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="bca9d-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="bca9d-146">Элемент \*\* &lt;конечных точек&gt; \*\* определяет конечную точку, которую клиент использует для доступа к службе следующим образом:</span><span class="sxs-lookup"><span data-stu-id="bca9d-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="bca9d-147">Адрес: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="bca9d-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="bca9d-148">Адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bca9d-148">The address of the endpoint.</span></span>
- <span data-ttu-id="bca9d-149">Сервисный `ServiceReference1.ICalculator`контракт: .</span><span class="sxs-lookup"><span data-stu-id="bca9d-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="bca9d-150">Контракт на обслуживание обрабатывает связь между клиентом WCF и службой.</span><span class="sxs-lookup"><span data-stu-id="bca9d-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="bca9d-151">Visual Studio генерировал этот контракт, когда вы использовали функцию **справки add Service.**</span><span class="sxs-lookup"><span data-stu-id="bca9d-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="bca9d-152">По сути, это копия контракта, который вы определили в проекте GettingStartedLib.</span><span class="sxs-lookup"><span data-stu-id="bca9d-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span>
- <span data-ttu-id="bca9d-153">Связывание: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="bca9d-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="bca9d-154">Привязка определяет HTTP как транспорт, совместимую безопасность и другие детали конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bca9d-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bca9d-155">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="bca9d-155">Next steps</span></span>

<span data-ttu-id="bca9d-156">В этом руководстве вы узнали, как выполнять следующие задачи:</span><span class="sxs-lookup"><span data-stu-id="bca9d-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="bca9d-157">Создайте и назначайте проект консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="bca9d-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="bca9d-158">Добавьте ссылку на службу WCF для создания прокси-класса и файлов конфигурации для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="bca9d-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="bca9d-159">Перейти к следующему учебнику, чтобы узнать, как использовать генерируемый клиент.</span><span class="sxs-lookup"><span data-stu-id="bca9d-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bca9d-160">Учебник: Используйте клиент WCF</span><span class="sxs-lookup"><span data-stu-id="bca9d-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
