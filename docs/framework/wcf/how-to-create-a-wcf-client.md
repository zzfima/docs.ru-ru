---
title: Учебник. Создание клиента Windows Communication Foundation
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: ddb5167c7f71a263377fb465ec44ee21057fbf4a
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928904"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a><span data-ttu-id="b7127-102">Учебник. Создание клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b7127-102">Tutorial: Create a Windows Communication Foundation client</span></span>

<span data-ttu-id="b7127-103">В этом руководстве описываются четвертые из пяти задач, необходимых для создания базового приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="b7127-103">This tutorial describes the fourth of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b7127-104">Общие сведения о учебниках см. в [разделе Учебник. Приступая к работе с](getting-started-tutorial.md)Windows Communication Foundation приложениями.</span><span class="sxs-lookup"><span data-stu-id="b7127-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="b7127-105">Следующей задачей для создания приложения WCF является создание клиента путем извлечения метаданных из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="b7127-105">The next task for creating a WCF application is to create a client by retrieving metadata from a WCF service.</span></span> <span data-ttu-id="b7127-106">Для добавления ссылки на службу, которая получает метаданные из конечной точки обмена метаданными службы, используется Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b7127-106">You use Visual Studio to add a service reference, which gets the metadata from the service’s MEX endpoint.</span></span> <span data-ttu-id="b7127-107">Затем Visual Studio создает управляемый файл исходного кода для прокси клиента на выбранном языке.</span><span class="sxs-lookup"><span data-stu-id="b7127-107">Visual Studio then generates a managed source code file for a client proxy in the language you've chosen.</span></span> <span data-ttu-id="b7127-108">Он также создает файл конфигурации клиента (*app. config*).</span><span class="sxs-lookup"><span data-stu-id="b7127-108">It also creates a client configuration file (*App.config*).</span></span> <span data-ttu-id="b7127-109">Этот файл позволяет клиентскому приложению подключаться к службе в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="b7127-109">This file enables the client application to connect to the service at an endpoint.</span></span> 

> [!NOTE]
> <span data-ttu-id="b7127-110">При вызове службы WCF из проекта библиотеки классов в Visual Studio используйте функцию **Добавление ссылки на службу** для автоматического создания прокси-сервера и связанного файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b7127-110">If you call a WCF service from a class library project in Visual Studio, use the **Add Service Reference** feature to automatically generate a proxy and associated configuration file.</span></span> <span data-ttu-id="b7127-111">Однако, поскольку проекты библиотеки классов не используют этот файл конфигурации, необходимо добавить параметры в созданный файл конфигурации в файл *app. config* для исполняемого файла, который вызывает библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="b7127-111">However, because class library projects don't use this configuration file, you need to add the settings in the generated configuration file to the *App.config* file for the executable that calls the class library.</span></span>

> [!NOTE]
> <span data-ttu-id="b7127-112">В качестве альтернативы для создания прокси-класса и файла конфигурации вместо Visual Studio следует использовать [средство служебной программы для метаданных ServiceModel](#servicemodel-metadata-utility-tool) .</span><span class="sxs-lookup"><span data-stu-id="b7127-112">As an alternative, use the [ServiceModel Metadata Utility tool](#servicemodel-metadata-utility-tool) instead of Visual Studio to generate the proxy class and configuration file.</span></span>

<span data-ttu-id="b7127-113">Клиентское приложение использует созданный прокси-класс для взаимодействия со службой.</span><span class="sxs-lookup"><span data-stu-id="b7127-113">The client application uses the generated proxy class to communicate with the service.</span></span> <span data-ttu-id="b7127-114">Эта процедура описана в [руководстве. Используйте клиент](how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="b7127-114">This procedure is described in [Tutorial: Use a client](how-to-use-a-wcf-client.md).</span></span>

<span data-ttu-id="b7127-115">В этом руководстве вы узнаете, как:</span><span class="sxs-lookup"><span data-stu-id="b7127-115">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="b7127-116">Создание и Настройка проекта консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="b7127-116">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="b7127-117">Добавьте ссылку на службу WCF для создания прокси-класса и файлов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b7127-117">Add a service reference to the WCF service to generate the proxy class and configuration files.</span></span>

## <a name="create-a-windows-communication-foundation-client"></a><span data-ttu-id="b7127-118">Создание клиента Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="b7127-118">Create a Windows Communication Foundation client</span></span>

1. <span data-ttu-id="b7127-119">Создание проекта консольного приложения в Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b7127-119">Create a console app project in Visual Studio:</span></span> 

    1. <span data-ttu-id="b7127-120">В меню **файл** выберите команду **Открыть** > **проект или решение** и перейдите к созданному ранее решению **GettingStarted** (*GettingStarted. sln*).</span><span class="sxs-lookup"><span data-stu-id="b7127-120">From the **File** menu, select **Open** > **Project/Solution** and browse to the **GettingStarted** solution you previously created (*GettingStarted.sln*).</span></span> <span data-ttu-id="b7127-121">Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="b7127-121">Select **Open**.</span></span>

    2. <span data-ttu-id="b7127-122">В меню **вид** выберите **Обозреватель решений**.</span><span class="sxs-lookup"><span data-stu-id="b7127-122">From the **View** menu, select **Solution Explorer**.</span></span>

    3. <span data-ttu-id="b7127-123">В окне **Обозреватель решений** выберите решение **GettingStarted** (верхний узел), а затем в контекстном меню выберите **добавить** > **Новый проект** .</span><span class="sxs-lookup"><span data-stu-id="b7127-123">In the **Solution Explorer** window, select the **GettingStarted** solution (top node), and then select **Add** > **New Project** from the shortcut menu.</span></span> 
    
    4. <span data-ttu-id="b7127-124">В левой части окна **Добавление нового проекта** выберите категорию **Рабочий стол Windows** в разделе  **C# Visual** или **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="b7127-124">In the **Add New Project** window, on the left side, select the **Windows Desktop** category under **Visual C#** or **Visual Basic**.</span></span> 

    5. <span data-ttu-id="b7127-125">Выберите шаблон **консольное приложение (.NET Framework)** и введите *GettingStartedClient* в поле **имя**.</span><span class="sxs-lookup"><span data-stu-id="b7127-125">Select the **Console App (.NET Framework)** template, and enter *GettingStartedClient* for the **Name**.</span></span> <span data-ttu-id="b7127-126">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7127-126">Select **OK**.</span></span>

2. <span data-ttu-id="b7127-127">Добавьте ссылку в проект <xref:System.ServiceModel> **GettingStartedClient** в сборку:</span><span class="sxs-lookup"><span data-stu-id="b7127-127">Add a reference in the **GettingStartedClient** project to the <xref:System.ServiceModel> assembly:</span></span> 

    1. <span data-ttu-id="b7127-128">В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedClient** , а затем в контекстном меню выберите пункт **Добавить ссылку** .</span><span class="sxs-lookup"><span data-stu-id="b7127-128">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Reference** from the shortcut menu.</span></span> 

    2. <span data-ttu-id="b7127-129">В окне **Добавление ссылки** в разделе **сборки** в левой части окна выберите **платформа**.</span><span class="sxs-lookup"><span data-stu-id="b7127-129">In the **Add Reference** window, under **Assemblies** on the left side of the window, select **Framework**.</span></span>
    
    3. <span data-ttu-id="b7127-130">Найдите и выберите **System. ServiceModel**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7127-130">Find and select **System.ServiceModel**, and then choose **OK**.</span></span> 

    4. <span data-ttu-id="b7127-131">Сохраните решение, выбрав **файл** > **сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="b7127-131">Save the solution by selecting **File** > **Save All**.</span></span>

3. <span data-ttu-id="b7127-132">Добавьте ссылку на службу в службу калькулятора:</span><span class="sxs-lookup"><span data-stu-id="b7127-132">Add a service reference to the calculator service:</span></span>

   1. <span data-ttu-id="b7127-133">В окне **Обозреватель решений** выберите папку **References** в проекте **GettingStartedClient** , а затем в контекстном меню выберите **Добавление ссылки на службу** .</span><span class="sxs-lookup"><span data-stu-id="b7127-133">In the **Solution Explorer** window, select the **References** folder under the **GettingStartedClient** project, and then select **Add Service Reference** from the shortcut menu.</span></span>

   2. <span data-ttu-id="b7127-134">В окне **Добавление ссылки на службу** выберите **Обнаружение**.</span><span class="sxs-lookup"><span data-stu-id="b7127-134">In the **Add Service Reference** window, select **Discover**.</span></span>

      <span data-ttu-id="b7127-135">Служба CalculatorService запускается, и Visual Studio отображает ее в окне **службы** .</span><span class="sxs-lookup"><span data-stu-id="b7127-135">The CalculatorService service starts and Visual Studio displays it in the **Services** box.</span></span>

   3. <span data-ttu-id="b7127-136">Выберите **CalculatorService** , чтобы развернуть его и отобразить контракты службы, реализованные службой.</span><span class="sxs-lookup"><span data-stu-id="b7127-136">Select **CalculatorService** to expand it and display the service contracts implemented by the service.</span></span> <span data-ttu-id="b7127-137">Оставьте **пространство имен** по умолчанию и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="b7127-137">Leave the default **Namespace** and choose **OK**.</span></span>

      <span data-ttu-id="b7127-138">Visual Studio добавит новый элемент в папку **подключенные службы** проекта **GettingStartedClient** .</span><span class="sxs-lookup"><span data-stu-id="b7127-138">Visual Studio adds a new item under the **Connected Services** folder in the **GettingStartedClient** project.</span></span> 

### <a name="servicemodel-metadata-utility-tool"></a><span data-ttu-id="b7127-139">Средство служебной программы метаданных ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b7127-139">ServiceModel Metadata Utility tool</span></span>

<span data-ttu-id="b7127-140">В следующих примерах показано, как при необходимости использовать [средство служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания файла прокси-класса.</span><span class="sxs-lookup"><span data-stu-id="b7127-140">The following examples show how to optionally use the [ServiceModel Metadata Utility tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the proxy class file.</span></span> <span data-ttu-id="b7127-141">Это средство создает файл прокси-класса и файл *app. config* .</span><span class="sxs-lookup"><span data-stu-id="b7127-141">This tool generates the proxy class file and the *App.config* file.</span></span> <span data-ttu-id="b7127-142">В следующих примерах показано, как создать прокси в C# и Visual Basic соответственно.</span><span class="sxs-lookup"><span data-stu-id="b7127-142">The following examples show how to generate the proxy in C# and Visual Basic, respectively:</span></span>

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a><span data-ttu-id="b7127-143">Файл конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="b7127-143">Client configuration file</span></span>

<span data-ttu-id="b7127-144">После создания клиента Visual Studio создаст файл конфигурации **app. config** в проекте **GettingStartedClient** , который должен быть похож на следующий пример:</span><span class="sxs-lookup"><span data-stu-id="b7127-144">After you've created the client, Visual Studio creates the **App.config** configuration file in the **GettingStartedClient** project, which should be similar to the following example:</span></span>

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

<span data-ttu-id="b7127-145">В разделе [> System.ServiceModelОбратитевниманиенаэлемент>конечнойточки.\<](../configure-apps/file-schema/wcf/system-servicemodel.md) [ \<](../configure-apps/file-schema/wcf/endpoint-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7127-145">Under the [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) section, notice the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="b7127-146">Элемент **Endpoint&gt;определяет конечную точку, которую клиент использует для доступа к службе следующим образом: &lt;**</span><span class="sxs-lookup"><span data-stu-id="b7127-146">The **&lt;endpoint&gt;** element defines the endpoint that the client uses to access the service as follows:</span></span>

- <span data-ttu-id="b7127-147">Адрес: `http://localhost:8000/GettingStarted/CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="b7127-147">Address: `http://localhost:8000/GettingStarted/CalculatorService`.</span></span> <span data-ttu-id="b7127-148">Адрес конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b7127-148">The address of the endpoint.</span></span>
- <span data-ttu-id="b7127-149">Контракт службы: `ServiceReference1.ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="b7127-149">Service contract: `ServiceReference1.ICalculator`.</span></span> <span data-ttu-id="b7127-150">Контракт службы обрабатывает взаимодействие между клиентом WCF и службой.</span><span class="sxs-lookup"><span data-stu-id="b7127-150">The service contract handles communication between the WCF client and the service.</span></span> <span data-ttu-id="b7127-151">Visual Studio создала этот контракт при использовании функции **Добавление ссылки на службу** .</span><span class="sxs-lookup"><span data-stu-id="b7127-151">Visual Studio generated this contract when you used its **Add Service Reference** function.</span></span> <span data-ttu-id="b7127-152">По сути, это копия контракта, определенного в проекте Жеттингстартедлиб.</span><span class="sxs-lookup"><span data-stu-id="b7127-152">It's essentially a copy of the contract that you defined in the GettingStartedLib project.</span></span> 
- <span data-ttu-id="b7127-153">Привязка: <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="b7127-153">Binding: <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="b7127-154">Привязка указывает HTTP как транспорт, взаимодействующую безопасность и другие сведения о конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b7127-154">The binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7127-155">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="b7127-155">Next steps</span></span>

<span data-ttu-id="b7127-156">В этом руководстве вы узнали, как:</span><span class="sxs-lookup"><span data-stu-id="b7127-156">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="b7127-157">Создание и Настройка проекта консольного приложения для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="b7127-157">Create and configure a console app project for the WCF client.</span></span>
> - <span data-ttu-id="b7127-158">Добавьте ссылку на службу WCF, чтобы создать класс прокси и файлы конфигурации для клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="b7127-158">Add a service reference to the WCF service to generate the proxy class and configuration files for the client application.</span></span>

<span data-ttu-id="b7127-159">Перейдите к следующему руководству, чтобы узнать, как использовать созданный клиент.</span><span class="sxs-lookup"><span data-stu-id="b7127-159">Advance to the next tutorial to learn how to use the generated client.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b7127-160">Учебник. Использование клиента WCF</span><span class="sxs-lookup"><span data-stu-id="b7127-160">Tutorial: Use a WCF client</span></span>](how-to-use-a-wcf-client.md)
