---
title: Практическое руководство. Защита службы с использованием учетных данных Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, security
ms.assetid: d171b5ca-96ef-47ff-800c-c138023cf76e
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2fa8d753d5fb168c14ee71cbbf6de62e0e4aff9e
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806400"
---
# <a name="how-to-secure-a-service-with-windows-credentials"></a><span data-ttu-id="0df89-102">Практическое руководство. Защита службы с использованием учетных данных Windows</span><span class="sxs-lookup"><span data-stu-id="0df89-102">How to: Secure a Service with Windows Credentials</span></span>
<span data-ttu-id="0df89-103">В этом разделе показано, как включить режим безопасности транспорта для службы Windows Communication Foundation (WCF), которая находится в домене Windows и вызывается клиентами, в том же домене.</span><span class="sxs-lookup"><span data-stu-id="0df89-103">This topic shows how to enable transport security on a Windows Communication Foundation (WCF) service that resides in a Windows domain and is called by clients in the same domain.</span></span> <span data-ttu-id="0df89-104">Дополнительные сведения об этом сценарии см. в разделе [безопасность транспорта с проверкой подлинности Windows](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="0df89-104">For more information about this scenario, see [Transport Security with Windows Authentication](../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md).</span></span> <span data-ttu-id="0df89-105">Пример приложения см. в разделе [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) образца.</span><span class="sxs-lookup"><span data-stu-id="0df89-105">For a sample application, see the [WSHttpBinding](../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>  
  
 <span data-ttu-id="0df89-106">Начинать изучение этого раздела рекомендуется только после определения существующего интерфейса контракта и его реализации.</span><span class="sxs-lookup"><span data-stu-id="0df89-106">This topic assumes you have an existing contract interface and implementation already defined, and adds on to that.</span></span> <span data-ttu-id="0df89-107">Также можно изменять существующие службу и клиент.</span><span class="sxs-lookup"><span data-stu-id="0df89-107">You can also modify an existing service and client.</span></span>  
  
 <span data-ttu-id="0df89-108">Обеспечить безопасность службы с помощью учетных данных Windows можно полностью в коде.</span><span class="sxs-lookup"><span data-stu-id="0df89-108">You can secure a service with Windows credentials completely in code.</span></span> <span data-ttu-id="0df89-109">Кроме того, можно опустить часть кода, воспользовавшись файлом конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0df89-109">Alternatively, you can omit some of the code by using a configuration file.</span></span> <span data-ttu-id="0df89-110">В этом разделе описаны оба метода.</span><span class="sxs-lookup"><span data-stu-id="0df89-110">This topic shows both ways.</span></span> <span data-ttu-id="0df89-111">Тем не менее, оба метода нельзя использовать одновременно, необходимо выбрать один из них.</span><span class="sxs-lookup"><span data-stu-id="0df89-111">Be sure you only use one of the ways, not both.</span></span>  
  
 <span data-ttu-id="0df89-112">Первые три процедуры показывают, как защитить службу с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="0df89-112">The first three procedures show how to secure the service using code.</span></span> <span data-ttu-id="0df89-113">Четвертая и пятая процедуры показывают, как сделать это с помощью файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0df89-113">The fourth and fifth procedure shows how to do it with a configuration file.</span></span>  
  
## <a name="using-code"></a><span data-ttu-id="0df89-114">Использование кода</span><span class="sxs-lookup"><span data-stu-id="0df89-114">Using Code</span></span>  
 <span data-ttu-id="0df89-115">Полный код для службы и клиента приводится в подразделе "Примеры" в конце данного раздела.</span><span class="sxs-lookup"><span data-stu-id="0df89-115">The complete code for the service and the client is in the Example section at the end of this topic.</span></span>  
  
 <span data-ttu-id="0df89-116">В первой процедуре описывается создание и настройка класса <xref:System.ServiceModel.WSHttpBinding> в коде.</span><span class="sxs-lookup"><span data-stu-id="0df89-116">The first procedure walks through creating and configuring a <xref:System.ServiceModel.WSHttpBinding> class in code.</span></span> <span data-ttu-id="0df89-117">Привязка использует транспорт HTTP.</span><span class="sxs-lookup"><span data-stu-id="0df89-117">The binding uses the HTTP transport.</span></span> <span data-ttu-id="0df89-118">Та же привязка используется в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0df89-118">The same binding is used on the client.</span></span>  
  
#### <a name="to-create-a-wshttpbinding-that-uses-windows-credentials-and-message-security"></a><span data-ttu-id="0df89-119">Создание привязки WSHttpBinding, использующей учетные данные Windows и безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="0df89-119">To create a WSHttpBinding that uses Windows credentials and message security</span></span>  
  
1.  <span data-ttu-id="0df89-120">Код этой процедуры вставлен в начало кода метода `Run` класса `Test` в коде службы, приведенном в подразделе "Примеры".</span><span class="sxs-lookup"><span data-stu-id="0df89-120">This procedure's code is inserted at the beginning of the `Run` method of the `Test` class in the service code in the Example section.</span></span>  
  
2.  <span data-ttu-id="0df89-121">Создайте экземпляр класса <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="0df89-121">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>  
  
3.  <span data-ttu-id="0df89-122">Задайте свойству <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> класса <xref:System.ServiceModel.WSHttpSecurity> значение <xref:System.ServiceModel.SecurityMode.Message>.</span><span class="sxs-lookup"><span data-stu-id="0df89-122">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property of the <xref:System.ServiceModel.WSHttpSecurity> class to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
4.  <span data-ttu-id="0df89-123">Задайте свойству <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> класса <xref:System.ServiceModel.MessageSecurityOverHttp> значение <xref:System.ServiceModel.MessageCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="0df89-123">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property of the <xref:System.ServiceModel.MessageSecurityOverHttp> class to <xref:System.ServiceModel.MessageCredentialType.Windows>.</span></span>  
  
5.  <span data-ttu-id="0df89-124">Для данной процедуры используется следующий код.</span><span class="sxs-lookup"><span data-stu-id="0df89-124">The code for this procedure is as follows:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#1)]
     [!code-vb[c_SecureWindowsService#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#1)]  
  
### <a name="using-the-binding-in-a-service"></a><span data-ttu-id="0df89-125">Использование привязки в службе</span><span class="sxs-lookup"><span data-stu-id="0df89-125">Using the Binding in a Service</span></span>  
 <span data-ttu-id="0df89-126">Это вторая процедура, в которой показано, как использовать привязку в резидентной службе.</span><span class="sxs-lookup"><span data-stu-id="0df89-126">This is the second procedure, which shows how to use the binding in a self-hosted service.</span></span> <span data-ttu-id="0df89-127">Дополнительные сведения о размещении служб в разделе [размещение служб](../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="0df89-127">For more information about hosting services see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
##### <a name="to-use-a-binding-in-a-service"></a><span data-ttu-id="0df89-128">Использование привязки в службе</span><span class="sxs-lookup"><span data-stu-id="0df89-128">To use a binding in a service</span></span>  
  
1.  <span data-ttu-id="0df89-129">Вставьте код этой процедуры после кода предыдущей процедуры</span><span class="sxs-lookup"><span data-stu-id="0df89-129">Insert this procedure's code after the code from the preceding procedure.</span></span>  
  
2.  <span data-ttu-id="0df89-130">Создайте переменную <xref:System.Type> с именем `contractType` и присвойте ей тип интерфейса (`ICalculator`).</span><span class="sxs-lookup"><span data-stu-id="0df89-130">Create a <xref:System.Type> variable named `contractType` and assign it the type of the interface (`ICalculator`).</span></span> <span data-ttu-id="0df89-131">При использовании Visual Basic, используйте `GetType` оператора; при использовании C#, используйте `typeof` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="0df89-131">When using Visual Basic, use the `GetType` operator; when using C#, use the `typeof` keyword.</span></span>  
  
3.  <span data-ttu-id="0df89-132">Создайте вторую переменную `Type` с именем `serviceType` и присвойте ей тип реализованного контракта (`Calculator`).</span><span class="sxs-lookup"><span data-stu-id="0df89-132">Create a second `Type` variable named `serviceType` and assign it the type of the implemented contract (`Calculator`).</span></span>  
  
4.  <span data-ttu-id="0df89-133">Создайте экземпляр класса <xref:System.Uri> с именем `baseAddress` с базовым адресом службы.</span><span class="sxs-lookup"><span data-stu-id="0df89-133">Create an instance of the <xref:System.Uri> class named `baseAddress` with the base address of the service.</span></span> <span data-ttu-id="0df89-134">Базовый адрес должен иметь схему, которая сочетается с транспортом.</span><span class="sxs-lookup"><span data-stu-id="0df89-134">The base address must have a scheme that matches the transport.</span></span> <span data-ttu-id="0df89-135">В этом случае схема транспорта-HTTP, и адрес включает специальный универсальный код ресурса (URI) «localhost» и номер порта (8036) и базовый адрес конечной точки ("serviceModelSamples /): http://localhost:8036/serviceModelSamples/.</span><span class="sxs-lookup"><span data-stu-id="0df89-135">In this case, the transport scheme is HTTP, and the address includes the special Uniform Resource Identifier (URI) "localhost" and a port number (8036) as well as a base endpoint address ("serviceModelSamples/): http://localhost:8036/serviceModelSamples/.</span></span>  
  
5.  <span data-ttu-id="0df89-136">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost> с переменными `serviceType` и `baseAddress`.</span><span class="sxs-lookup"><span data-stu-id="0df89-136">Create an instance of the <xref:System.ServiceModel.ServiceHost> class with the `serviceType` and `baseAddress` variables.</span></span>  
  
6.  <span data-ttu-id="0df89-137">Добавьте в службу конечную точку с использованием `contractType`, привязки и имени конечной точки (secureCalculator).</span><span class="sxs-lookup"><span data-stu-id="0df89-137">Add an endpoint to the service using the `contractType`, binding, and an endpoint name (secureCalculator).</span></span> <span data-ttu-id="0df89-138">При инициировании вызова службы клиент должен объединять базовый адрес и имя конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0df89-138">A client must concatenate the base address and the endpoint name when initiating a call to the service.</span></span>  
  
7.  <span data-ttu-id="0df89-139">Чтобы запустить службу, вызовите метод <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="0df89-139">Call the <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> method to start the service.</span></span> <span data-ttu-id="0df89-140">Код для данной процедуры показан далее.</span><span class="sxs-lookup"><span data-stu-id="0df89-140">The code for this procedure is shown here:</span></span>  
  
     [!code-csharp[c_SecureWindowsService#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#2)]
     [!code-vb[c_SecureWindowsService#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsservice/vb/secureservice.vb#2)]  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="0df89-141">Использование привязки в клиенте</span><span class="sxs-lookup"><span data-stu-id="0df89-141">Using the Binding in a Client</span></span>  
 <span data-ttu-id="0df89-142">Эта процедура показывает, как создать прокси, взаимодействующий со службой.</span><span class="sxs-lookup"><span data-stu-id="0df89-142">This procedure shows how to generate a proxy that communicates with the service.</span></span> <span data-ttu-id="0df89-143">Созданный прокси-сервер с [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания прокси-сервера, которая использует метаданные службы.</span><span class="sxs-lookup"><span data-stu-id="0df89-143">The proxy is generated with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) which uses the service metadata to create the proxy.</span></span>  
  
 <span data-ttu-id="0df89-144">Эта процедура также создает экземпляр класса <xref:System.ServiceModel.WSHttpBinding> для взаимодействия со службой, а затем вызывает службу.</span><span class="sxs-lookup"><span data-stu-id="0df89-144">This procedure also creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class to communicate with the service, and then calls the service.</span></span>  
  
 <span data-ttu-id="0df89-145">В этом примере для создания клиента используется только код.</span><span class="sxs-lookup"><span data-stu-id="0df89-145">This example uses only code to create the client.</span></span> <span data-ttu-id="0df89-146">В качестве альтернативы можно использовать файл конфигурации, показанный в следующем после этой процедуры разделе.</span><span class="sxs-lookup"><span data-stu-id="0df89-146">As an alternative, you can use a configuration file, which is shown in the section following this procedure.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-code"></a><span data-ttu-id="0df89-147">Использование привязки в клиенте с кодом</span><span class="sxs-lookup"><span data-stu-id="0df89-147">To use a binding in a client with code</span></span>  
  
1.  <span data-ttu-id="0df89-148">Используйте средство SvcUtil.exe, чтобы создать код прокси из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="0df89-148">Use the SvcUtil.exe tool to generate the proxy code from the service's metadata.</span></span> <span data-ttu-id="0df89-149">Дополнительные сведения см. в разделе [как: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="0df89-149">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="0df89-150">Созданный код прокси наследует от <xref:System.ServiceModel.ClientBase%601> класса, благодаря чему каждый клиент имеет необходимые конструкторы, методы и свойства для взаимодействия со службой WCF.</span><span class="sxs-lookup"><span data-stu-id="0df89-150">The generated proxy code inherits from the <xref:System.ServiceModel.ClientBase%601> class, which ensures that every client has the necessary constructors, methods, and properties to communicate with a WCF service.</span></span> <span data-ttu-id="0df89-151">В данном примере созданный код включает класс `CalculatorClient`, который реализует интерфейс `ICalculator`, тем самым обеспечивая совместимость с кодом службы.</span><span class="sxs-lookup"><span data-stu-id="0df89-151">In this example, the generated code includes the `CalculatorClient` class, which implements the `ICalculator` interface, enabling compatibility with the service code.</span></span>  
  
2.  <span data-ttu-id="0df89-152">Код этой процедуры вставляется в начало метода `Main` программы клиента.</span><span class="sxs-lookup"><span data-stu-id="0df89-152">This procedure's code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
3.  <span data-ttu-id="0df89-153">Создайте экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и задайте его режиму безопасности значение `Message`, а его типу учетных данных клиента - `Windows`.</span><span class="sxs-lookup"><span data-stu-id="0df89-153">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to `Message` and its client credential type to `Windows`.</span></span> <span data-ttu-id="0df89-154">В примере называется переменная `clientBinding`.</span><span class="sxs-lookup"><span data-stu-id="0df89-154">The example names the variable `clientBinding`.</span></span>  
  
4.  <span data-ttu-id="0df89-155">Создайте экземпляр класса <xref:System.ServiceModel.EndpointAddress> с именем `serviceAddress`.</span><span class="sxs-lookup"><span data-stu-id="0df89-155">Create an instance of the <xref:System.ServiceModel.EndpointAddress> class named `serviceAddress`.</span></span> <span data-ttu-id="0df89-156">Инициализируйте экземпляр с базовым адресом, объединенным с именем конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0df89-156">Initialize the instance with the base address concatenated with the endpoint name.</span></span>  
  
5.  <span data-ttu-id="0df89-157">Создайте экземпляр созданного класса клиента с переменными `serviceAddress` и `clientBinding`.</span><span class="sxs-lookup"><span data-stu-id="0df89-157">Create an instance of the generated client class with the `serviceAddress` and the `clientBinding` variables.</span></span>  
  
6.  <span data-ttu-id="0df89-158">Вызовите метод <xref:System.ServiceModel.ClientBase%601.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0df89-158">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
7.  <span data-ttu-id="0df89-159">Вызовите службу и отобразите результаты.</span><span class="sxs-lookup"><span data-stu-id="0df89-159">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#1)]
     [!code-vb[c_secureWindowsClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#1)]  
  
## <a name="using-the-configuration-file"></a><span data-ttu-id="0df89-160">Использование файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0df89-160">Using the Configuration File</span></span>  
 <span data-ttu-id="0df89-161">Вместо создания привязки с процедурным кодом можно использовать следующий код, приведенный для раздела привязок файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0df89-161">Instead of creating the binding with procedural code, you can use the following code shown for the bindings section of the configuration file.</span></span>  
  
 <span data-ttu-id="0df89-162">Если служба определение еще нет в разделе [проектирование и реализация служб](../../../docs/framework/wcf/designing-and-implementing-services.md), и [Настройка службы](../../../docs/framework/wcf/configuring-services.md).</span><span class="sxs-lookup"><span data-stu-id="0df89-162">If you do not already have a service defined, see [Designing and Implementing Services](../../../docs/framework/wcf/designing-and-implementing-services.md), and [Configuring Services](../../../docs/framework/wcf/configuring-services.md).</span></span>  
  
 <span data-ttu-id="0df89-163">**Примечание** данный код конфигурации используется в файлах конфигурации клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="0df89-163">**Note** This configuration code is used in both the service and client configuration files.</span></span>  
  
#### <a name="to-enable-transfer-security-on-a-service-in-a-windows-domain-using-configuration"></a><span data-ttu-id="0df89-164">Включение безопасности передачи в службе в домене Windows с использованием конфигурации</span><span class="sxs-lookup"><span data-stu-id="0df89-164">To enable transfer security on a service in a Windows domain using configuration</span></span>  
  
1.  <span data-ttu-id="0df89-165">Добавить [ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) элемент [ \<привязки >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемент раздела файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0df89-165">Add a [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element to the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section of the configuration file.</span></span>  
  
2.  <span data-ttu-id="0df89-166">Добавьте элемент <`binding`> в элемент <`WSHttpBinding`> и присвойте атрибуту `configurationName` значение, подходящее для используемого приложения.</span><span class="sxs-lookup"><span data-stu-id="0df89-166">Add a <`binding`> element to the <`WSHttpBinding`> element and set the `configurationName` attribute to a value appropriate to your application.</span></span>  
  
3.  <span data-ttu-id="0df89-167">Добавьте элемент <`security`> и присвойте атрибуту `mode` значение Message.</span><span class="sxs-lookup"><span data-stu-id="0df89-167">Add a <`security`> element and set the `mode` attribute to Message.</span></span>  
  
4.  <span data-ttu-id="0df89-168">Добавьте элемент <`message`> и присвойте атрибуту `clientCredentialType` значение Windows.</span><span class="sxs-lookup"><span data-stu-id="0df89-168">Add a <`message`> element and set the `clientCredentialType` attribute to Windows.</span></span>  
  
5.  <span data-ttu-id="0df89-169">В файле конфигурации службы замените раздел `<bindings>` с помощью следующего кода.</span><span class="sxs-lookup"><span data-stu-id="0df89-169">In the service's configuration file, replace the `<bindings>` section with the following code.</span></span> <span data-ttu-id="0df89-170">Если вы еще нет файла конфигурации службы, см. раздел [с помощью привязок для настройки службы и клиенты](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0df89-170">If you do not already have a service configuration file, see [Using Bindings to Configure Services and Clients](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md).</span></span>  
  
    ```xml  
    <bindings>  
      <wsHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
### <a name="using-the-binding-in-a-client"></a><span data-ttu-id="0df89-171">Использование привязки в клиенте</span><span class="sxs-lookup"><span data-stu-id="0df89-171">Using the Binding in a Client</span></span>  
 <span data-ttu-id="0df89-172">Эта процедура показывает, как создать два файла: прокси, взаимодействующий со службой, и файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0df89-172">This procedure shows how to generate two files: a proxy that communicates with the service and a configuration file.</span></span> <span data-ttu-id="0df89-173">В этой процедуре также описаны изменения программы клиента, которая является третьим файлом, используемым в клиенте.</span><span class="sxs-lookup"><span data-stu-id="0df89-173">It also describes changes to the client program, which is the third file used on the client.</span></span>  
  
##### <a name="to-use-a-binding-in-a-client-with-configuration"></a><span data-ttu-id="0df89-174">Использование привязки в клиенте с конфигурацией</span><span class="sxs-lookup"><span data-stu-id="0df89-174">To use a binding in a client with configuration</span></span>  
  
1.  <span data-ttu-id="0df89-175">Используйте средство SvcUtil.exe, чтобы создать код прокси и файл конфигурации из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="0df89-175">Use the SvcUtil.exe tool to generate the proxy code and configuration file from the service's metadata.</span></span> <span data-ttu-id="0df89-176">Дополнительные сведения см. в разделе [как: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="0df89-176">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="0df89-177">Замените [ \<привязки >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) раздел созданный файл конфигурации с кодом конфигурации из предыдущего раздела.</span><span class="sxs-lookup"><span data-stu-id="0df89-177">Replace the [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) section of the generated configuration file with the configuration code from the preceding section.</span></span>  
  
3.  <span data-ttu-id="0df89-178">Процедурный код вставлен в начало метода `Main` программы клиента.</span><span class="sxs-lookup"><span data-stu-id="0df89-178">Procedural code is inserted at the beginning of the `Main` method of the client program.</span></span>  
  
4.  <span data-ttu-id="0df89-179">Создайте экземпляр созданного класса клиента, передав имя привязки в файле конфигурации в качестве входного параметра.</span><span class="sxs-lookup"><span data-stu-id="0df89-179">Create an instance of the generated client class passing the name of the binding in the configuration file as an input parameter.</span></span>  
  
5.  <span data-ttu-id="0df89-180">Вызовите метод <xref:System.ServiceModel.ClientBase%601.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="0df89-180">Call the <xref:System.ServiceModel.ClientBase%601.Open%2A> method, as shown in the following code.</span></span>  
  
6.  <span data-ttu-id="0df89-181">Вызовите службу и отобразите результаты.</span><span class="sxs-lookup"><span data-stu-id="0df89-181">Call the service and display the results.</span></span>  
  
     [!code-csharp[c_secureWindowsClient#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="0df89-182">Пример</span><span class="sxs-lookup"><span data-stu-id="0df89-182">Example</span></span>  
 [!code-csharp[c_SecureWindowsService#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsservice/cs/secureservice.cs#0)]  
  
 [!code-csharp[c_SecureWindowsClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_securewindowsclient/cs/secureclient.cs#0)] 
 [!code-vb[c_SecureWindowsClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securewindowsclient/vb/secureclient.vb#0)]      
  
## <a name="see-also"></a><span data-ttu-id="0df89-183">См. также</span><span class="sxs-lookup"><span data-stu-id="0df89-183">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpBinding>  
 [<span data-ttu-id="0df89-184">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="0df89-184">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="0df89-185">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="0df89-185">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="0df89-186">Защита служб</span><span class="sxs-lookup"><span data-stu-id="0df89-186">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="0df89-187">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="0df89-187">Security Overview</span></span>](../../../docs/framework/wcf/feature-details/security-overview.md)
