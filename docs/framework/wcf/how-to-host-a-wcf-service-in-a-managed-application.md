---
title: Практическое руководство. Размещение службы WCF в управляемом приложении
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 131d99457427e0818f78076d987f550a99ad7cf0
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2018
ms.locfileid: "46485695"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="5de5e-102">Практическое: размещение службы WCF в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="5de5e-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="5de5e-103">Для размещения службы внутри управляемого приложения внедрите код службы внутрь кода управляемого приложения, определите конечную точку для службы императивно в коде, декларативно с помощью конфигурации или посредством конечных точек по умолчанию, а затем создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5de5e-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="5de5e-104">Чтобы начать принимать сообщения, вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5de5e-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="5de5e-105">При этом создается и открывается прослушиватель для этой службы.</span><span class="sxs-lookup"><span data-stu-id="5de5e-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="5de5e-106">Такое размещение службы часто называется "резидентным", так как управляемое приложение самостоятельно выполняет функции ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="5de5e-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="5de5e-107">Чтобы закрыть службу, вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> для <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5de5e-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="5de5e-108">Служба может также размещаться в управляемой службе Windows, в службах IIS или в службе активации процесса Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="5de5e-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="5de5e-109">Дополнительные сведения о вариантах службы размещения, см. в разделе [размещение служб](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="5de5e-109">For more information about hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>

<span data-ttu-id="5de5e-110">Размещение служб в управляемом приложении - самый гибкий вариант размещения, так как в этом случае требуется минимальное развертывание инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="5de5e-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="5de5e-111">Дополнительные сведения о размещении службы в управляемых приложениях см. в разделе [размещение в приложении управляемых](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="5de5e-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="5de5e-112">В следующей процедуре показано, как реализовать резидентную службу в консольном приложения.</span><span class="sxs-lookup"><span data-stu-id="5de5e-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="5de5e-113">Создание резидентной службы</span><span class="sxs-lookup"><span data-stu-id="5de5e-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="5de5e-114">Создайте новое консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="5de5e-114">Create a new console application:</span></span>

   1. <span data-ttu-id="5de5e-115">Откройте Visual Studio и выберите **New** > **проекта** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="5de5e-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="5de5e-116">В **установленные шаблоны** выберите **Visual C#** или **Visual Basic**, а затем выберите **Windows Desktop**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="5de5e-117">Выберите **консольное приложение** шаблона.</span><span class="sxs-lookup"><span data-stu-id="5de5e-117">Select the **Console App** template.</span></span> <span data-ttu-id="5de5e-118">Тип `SelfHost` в **имя** поле, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="5de5e-119">Щелкните правой кнопкой мыши **SelfHost** в **обозревателе решений** и выберите **добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="5de5e-120">Выберите **System.ServiceModel** из **.NET** вкладку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="5de5e-121">Если **обозревателе решений** окно не отображается, выберите пункт **обозревателе решений** из **представление** меню.</span><span class="sxs-lookup"><span data-stu-id="5de5e-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="5de5e-122">Дважды щелкните **Program.cs** или **Module1.vb** в **обозревателе решений** чтобы открыть его в окне кода, если он еще не открыт.</span><span class="sxs-lookup"><span data-stu-id="5de5e-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="5de5e-123">Добавьте следующие инструкции в начало файла:</span><span class="sxs-lookup"><span data-stu-id="5de5e-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="5de5e-124">Определите и реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="5de5e-124">Define and implement a service contract.</span></span> <span data-ttu-id="5de5e-125">В этом примере определяется служба `HelloWorldService`, которая возвращает сообщение на основании входных данных, передаваемых службе.</span><span class="sxs-lookup"><span data-stu-id="5de5e-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="5de5e-126">Дополнительные сведения о том, как определить и реализовать интерфейс службы см. в разделе [как: определение контракта службы](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) и [как: реализация контракта службы](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="5de5e-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="5de5e-127">В начале метода `Main` создайте экземпляр класса <xref:System.Uri> с базовым адресом для службы.</span><span class="sxs-lookup"><span data-stu-id="5de5e-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="5de5e-128">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>, передав <xref:System.Type>, представляющий тип службы, и универсальный код ресурса (URI) базового адреса в метод <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="5de5e-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="5de5e-129">Включите публикацию метаданных и вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> в <xref:System.ServiceModel.ServiceHost>, чтобы инициализировать службу и подготовить ее к приему сообщений.</span><span class="sxs-lookup"><span data-stu-id="5de5e-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="5de5e-130">В этом примере используются конечные точки по умолчанию, и для данной службы не требуется файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5de5e-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="5de5e-131">Если конечные точки не настроены, то среда выполнения создает одну конечную точку для каждого базового адреса в каждом контракте службы, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="5de5e-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="5de5e-132">Дополнительные сведения о конечных точках по умолчанию, см. в разделе [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="5de5e-132">For more information about default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="5de5e-133">Нажмите клавишу **Ctrl**+**Shift**+**B** для сборки решения.</span><span class="sxs-lookup"><span data-stu-id="5de5e-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="5de5e-134">Тестирование службы</span><span class="sxs-lookup"><span data-stu-id="5de5e-134">Test the service</span></span>

1. <span data-ttu-id="5de5e-135">Нажмите клавишу **Ctrl**+**F5** для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="5de5e-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="5de5e-136">Откройте **тестовый клиент WCF**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="5de5e-137">Чтобы открыть **тестовый клиент WCF**, откройте командную строку разработчика для Visual Studio и выполнение **WcfTestClient.exe**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="5de5e-138">Выберите **добавить службу** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="5de5e-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="5de5e-139">Тип `http://localhost:8080/hello` в поле "адрес" и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="5de5e-140">Убедитесь, что служба запущена. В противном случае проверка дает отрицательный результат на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="5de5e-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="5de5e-141">Если базовый адрес в коде был изменен, используйте на этом этапе измененный базовый адрес.</span><span class="sxs-lookup"><span data-stu-id="5de5e-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="5de5e-142">Дважды щелкните **SayHello** под **Мои проекты служб** узла.</span><span class="sxs-lookup"><span data-stu-id="5de5e-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="5de5e-143">Введите имя в **значение** столбца в **запроса** списке и нажмите кнопку **Invoke**.</span><span class="sxs-lookup"><span data-stu-id="5de5e-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="5de5e-144">Появится ответное сообщение в **ответа** списка.</span><span class="sxs-lookup"><span data-stu-id="5de5e-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="5de5e-145">Пример</span><span class="sxs-lookup"><span data-stu-id="5de5e-145">Example</span></span>

<span data-ttu-id="5de5e-146">В следующем примере создается объект <xref:System.ServiceModel.ServiceHost> для размещения службы типа `HelloWorldService`, затем вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="5de5e-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="5de5e-147">Базовый адрес предоставляется в коде, включена публикация метаданных и используются конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5de5e-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="5de5e-148">См. также</span><span class="sxs-lookup"><span data-stu-id="5de5e-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="5de5e-149">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="5de5e-149">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="5de5e-150">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="5de5e-150">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="5de5e-151">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="5de5e-151">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)
- [<span data-ttu-id="5de5e-152">Практическое руководство. Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="5de5e-152">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="5de5e-153">Практическое руководство. Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="5de5e-153">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="5de5e-154">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="5de5e-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="5de5e-155">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5de5e-155">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="5de5e-156">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="5de5e-156">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)