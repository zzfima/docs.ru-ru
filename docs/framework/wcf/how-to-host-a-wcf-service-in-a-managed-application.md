---
title: Практическое руководство. Размещение службы WCF в управляемом приложении
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: e3adcad6ba70aa64b797325cd45a043301d7e680
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320980"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a><span data-ttu-id="0adbf-102">Как разместить службу WCF в управляемом приложении</span><span class="sxs-lookup"><span data-stu-id="0adbf-102">How to: Host a WCF service in a managed app</span></span>

<span data-ttu-id="0adbf-103">Для размещения службы внутри управляемого приложения внедрите код службы внутрь кода управляемого приложения, определите конечную точку для службы императивно в коде, декларативно с помощью конфигурации или посредством конечных точек по умолчанию, а затем создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0adbf-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="0adbf-104">Чтобы начать принимать сообщения, вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0adbf-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="0adbf-105">При этом создается и открывается прослушиватель для этой службы.</span><span class="sxs-lookup"><span data-stu-id="0adbf-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="0adbf-106">Такое размещение службы часто называется "резидентным", так как управляемое приложение самостоятельно выполняет функции ведущего приложения.</span><span class="sxs-lookup"><span data-stu-id="0adbf-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="0adbf-107">Чтобы закрыть службу, вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> для <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0adbf-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>

<span data-ttu-id="0adbf-108">Служба может также размещаться в управляемой службе Windows, в службах IIS или в службе активации процесса Windows (WAS).</span><span class="sxs-lookup"><span data-stu-id="0adbf-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> <span data-ttu-id="0adbf-109">Дополнительные сведения о параметрах размещения для службы см. в разделе [службы хостинга](hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="0adbf-109">For more information about hosting options for a service, see [Hosting Services](hosting-services.md).</span></span>

<span data-ttu-id="0adbf-110">Размещение служб в управляемом приложении - самый гибкий вариант размещения, так как в этом случае требуется минимальное развертывание инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="0adbf-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> <span data-ttu-id="0adbf-111">Дополнительные сведения о размещении служб в управляемых приложениях см. [в разделе Размещение в управляемом приложении](./feature-details/hosting-in-a-managed-application.md).</span><span class="sxs-lookup"><span data-stu-id="0adbf-111">For more information about hosting services in managed applications, see [Hosting in a Managed Application](./feature-details/hosting-in-a-managed-application.md).</span></span>

<span data-ttu-id="0adbf-112">В следующей процедуре показано, как реализовать резидентную службу в консольном приложения.</span><span class="sxs-lookup"><span data-stu-id="0adbf-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>

## <a name="create-a-self-hosted-service"></a><span data-ttu-id="0adbf-113">Создание самостоятельно размещенной службы</span><span class="sxs-lookup"><span data-stu-id="0adbf-113">Create a self-hosted service</span></span>

1. <span data-ttu-id="0adbf-114">Создайте новое консольное приложение:</span><span class="sxs-lookup"><span data-stu-id="0adbf-114">Create a new console application:</span></span>

   1. <span data-ttu-id="0adbf-115">Откройте Visual Studio и выберите в меню **файл** пункт **создать** **проект**  > .</span><span class="sxs-lookup"><span data-stu-id="0adbf-115">Open Visual Studio and select **New** > **Project** from the **File** menu.</span></span>

   2. <span data-ttu-id="0adbf-116">В списке **Установленные шаблоны** выберите элемент **визуальный C#**  или **Visual Basic**, а затем выберите **Рабочий стол Windows**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-116">In the **Installed Templates** list, select **Visual C#** or **Visual Basic**, and then select **Windows Desktop**.</span></span>

   3. <span data-ttu-id="0adbf-117">Выберите шаблон **консольное приложение** .</span><span class="sxs-lookup"><span data-stu-id="0adbf-117">Select the **Console App** template.</span></span> <span data-ttu-id="0adbf-118">Введите `SelfHost` в поле **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-118">Type `SelfHost` in the **Name** box and then choose **OK**.</span></span>

2. <span data-ttu-id="0adbf-119">Щелкните правой кнопкой мыши **резидент** в **Обозреватель решений** и выберите команду **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference**.</span></span> <span data-ttu-id="0adbf-120">Выберите **System. ServiceModel** на вкладке **.NET** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-120">Select **System.ServiceModel** from the **.NET** tab and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0adbf-121">Если окно **Обозреватель решений** не отображается, выберите **Обозреватель решений** в меню **вид** .</span><span class="sxs-lookup"><span data-stu-id="0adbf-121">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>

3. <span data-ttu-id="0adbf-122">Дважды щелкните **Program.CS** или **Module1. vb** в **Обозреватель решений** , чтобы открыть его в окне кода, если оно еще не открыто.</span><span class="sxs-lookup"><span data-stu-id="0adbf-122">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window, if it's not already open.</span></span> <span data-ttu-id="0adbf-123">Добавьте следующие инструкции в начало файла:</span><span class="sxs-lookup"><span data-stu-id="0adbf-123">Add the following statements at the top of the file:</span></span>

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. <span data-ttu-id="0adbf-124">Определите и реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="0adbf-124">Define and implement a service contract.</span></span> <span data-ttu-id="0adbf-125">В этом примере определяется служба `HelloWorldService`, которая возвращает сообщение на основании входных данных, передаваемых службе.</span><span class="sxs-lookup"><span data-stu-id="0adbf-125">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > <span data-ttu-id="0adbf-126">Дополнительные сведения об определении и реализации интерфейса службы см. [в разделе инструкции. определение контракта службы](how-to-define-a-wcf-service-contract.md) и [инструкции. Реализация контракта службы](how-to-implement-a-wcf-contract.md).</span><span class="sxs-lookup"><span data-stu-id="0adbf-126">For more information about how to define and implement a service interface, see [How to: Define a Service Contract](how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](how-to-implement-a-wcf-contract.md).</span></span>

5. <span data-ttu-id="0adbf-127">В начале метода `Main` создайте экземпляр класса <xref:System.Uri> с базовым адресом для службы.</span><span class="sxs-lookup"><span data-stu-id="0adbf-127">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. <span data-ttu-id="0adbf-128">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>, передав <xref:System.Type>, представляющий тип службы, и универсальный код ресурса (URI) базового адреса в метод <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span><span class="sxs-lookup"><span data-stu-id="0adbf-128">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="0adbf-129">Включите публикацию метаданных и вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> в <xref:System.ServiceModel.ServiceHost>, чтобы инициализировать службу и подготовить ее к приему сообщений.</span><span class="sxs-lookup"><span data-stu-id="0adbf-129">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > <span data-ttu-id="0adbf-130">В этом примере используются конечные точки по умолчанию, и для данной службы не требуется файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0adbf-130">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="0adbf-131">Если конечные точки не настроены, то среда выполнения создает одну конечную точку для каждого базового адреса в каждом контракте службы, реализованном в службе.</span><span class="sxs-lookup"><span data-stu-id="0adbf-131">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> <span data-ttu-id="0adbf-132">Дополнительные сведения о конечных точках по умолчанию см. в разделе [упрощенная конфигурация](simplified-configuration.md) и [упрощенная конфигурация для служб WCF](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="0adbf-132">For more information about default endpoints, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>

7. <span data-ttu-id="0adbf-133">Нажмите клавиши **Ctrl**+**SHIFT**+**B** , чтобы создать решение.</span><span class="sxs-lookup"><span data-stu-id="0adbf-133">Press **Ctrl**+**Shift**+**B** to build the solution.</span></span>

## <a name="test-the-service"></a><span data-ttu-id="0adbf-134">Проверка службы</span><span class="sxs-lookup"><span data-stu-id="0adbf-134">Test the service</span></span>

1. <span data-ttu-id="0adbf-135">Нажмите клавиши **Ctrl**+**F5** , чтобы запустить службу.</span><span class="sxs-lookup"><span data-stu-id="0adbf-135">Press **Ctrl**+**F5** to run the service.</span></span>

2. <span data-ttu-id="0adbf-136">Откройте **тестовый клиент WCF**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-136">Open **WCF Test Client**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0adbf-137">Чтобы открыть **тестовый клиент WCF**, откройте Командная строка разработчика для Visual Studio и выполните **клиент WcfTestClient. exe**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-137">To open **WCF Test Client**, open Developer Command Prompt for Visual Studio and execute **WcfTestClient.exe**.</span></span>

3. <span data-ttu-id="0adbf-138">Выберите **Добавить службу** в меню **файл** .</span><span class="sxs-lookup"><span data-stu-id="0adbf-138">Select **Add Service** from the **File** menu.</span></span>

4. <span data-ttu-id="0adbf-139">Введите `http://localhost:8080/hello` в поле адрес и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-139">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0adbf-140">Убедитесь, что служба запущена. В противном случае проверка дает отрицательный результат на этом этапе.</span><span class="sxs-lookup"><span data-stu-id="0adbf-140">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="0adbf-141">Если базовый адрес в коде был изменен, используйте на этом этапе измененный базовый адрес.</span><span class="sxs-lookup"><span data-stu-id="0adbf-141">If you have changed the base address in the code, then use the modified base address in this step.</span></span>

5. <span data-ttu-id="0adbf-142">Дважды щелкните элемент **sayHello** в узле **Мои проекты "Мои службы** ".</span><span class="sxs-lookup"><span data-stu-id="0adbf-142">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="0adbf-143">Введите свое имя в столбец **значение** в списке **запрос** и нажмите кнопку **вызвать**.</span><span class="sxs-lookup"><span data-stu-id="0adbf-143">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span>

   <span data-ttu-id="0adbf-144">В списке **ответов** появится ответное сообщение.</span><span class="sxs-lookup"><span data-stu-id="0adbf-144">A reply message appears in the **Response** list.</span></span>

## <a name="example"></a><span data-ttu-id="0adbf-145">Пример</span><span class="sxs-lookup"><span data-stu-id="0adbf-145">Example</span></span>

<span data-ttu-id="0adbf-146">В следующем примере создается объект <xref:System.ServiceModel.ServiceHost> для размещения службы типа `HelloWorldService`, затем вызывается метод <xref:System.ServiceModel.ICommunicationObject.Open%2A> для <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="0adbf-146">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="0adbf-147">Базовый адрес предоставляется в коде, включена публикация метаданных и используются конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0adbf-147">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a><span data-ttu-id="0adbf-148">См. также</span><span class="sxs-lookup"><span data-stu-id="0adbf-148">See also</span></span>

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [<span data-ttu-id="0adbf-149">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="0adbf-149">How to: Host a WCF Service in IIS</span></span>](./feature-details/how-to-host-a-wcf-service-in-iis.md)
- [<span data-ttu-id="0adbf-150">Резидентное размещение</span><span class="sxs-lookup"><span data-stu-id="0adbf-150">Self-Host</span></span>](./samples/self-host.md)
- [<span data-ttu-id="0adbf-151">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="0adbf-151">Hosting Services</span></span>](hosting-services.md)
- [<span data-ttu-id="0adbf-152">Практическое руководство. Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="0adbf-152">How to: Define a Service Contract</span></span>](how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="0adbf-153">Практическое руководство. Реализация контракта службы</span><span class="sxs-lookup"><span data-stu-id="0adbf-153">How to: Implement a Service Contract</span></span>](how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="0adbf-154">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0adbf-154">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="0adbf-155">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="0adbf-155">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0adbf-156">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="0adbf-156">System-Provided Bindings</span></span>](system-provided-bindings.md)
