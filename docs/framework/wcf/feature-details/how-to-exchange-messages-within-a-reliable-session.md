---
title: "Практическое руководство. Обмен сообщениями в рамках надежного сеанса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ba3948ef52e6ce527b0bdba77652949e43d05eb2
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="3cd1c-102">Практическое руководство. Обмен сообщениями в рамках надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="3cd1c-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="3cd1c-103">В этом разделе описываются действия, необходимые, чтобы разрешить надежные сеансы с помощью одной из привязок, предоставляемых системой, которая поддерживает такие сеансы, но не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="3cd1c-104">Включение надежного сеанса императивно с помощью кода или декларативно в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="3cd1c-105">Эта процедура использует файлы конфигурации клиента и службы для включения надежного сеанса и обеспечивается доставка сообщений в том же порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="3cd1c-106">Ключевой момент данной процедуры заключается в том, что элемент конфигурации конечной точки содержат `bindingConfiguration` атрибут, ссылающийся на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="3cd1c-107">[  **\<Привязки >** ](../../../../docs/framework/misc/binding.md) элемент конфигурации ссылается на это имя, чтобы разрешить надежные сеансы, задав `enabled` атрибут [  **\<reliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) элемент `true`.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="3cd1c-108">Можно обеспечить доставку сообщений в порядке их отправки для надежного сеанса, присвоив атрибуту `ordered` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="3cd1c-109">Исходная копия в этом примере в разделе [надежный сеанс WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="3cd1c-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="3cd1c-110">Настройка службы с привязкой WSHttpBinding использования надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="3cd1c-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="3cd1c-111">Определите контракт службы для данного типа службы.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="3cd1c-112">Реализуйте контракт службы в классе службы.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="3cd1c-113">Обратите внимание, что информация об адресе или привязке не указывается внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="3cd1c-114">Не требуется писать код, чтобы получить сведения о адресе или привязке сведения из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-114">You aren't required to write code to retrieve the address or binding information information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="3cd1c-115">Создать *Web.config* файл, чтобы настроить конечную точку для `CalculatorService` , использующий <xref:System.ServiceModel.WSHttpBinding> с включен и упорядоченную доставку сообщений, необходимых для надежного сеанса.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="3cd1c-116">Создание *Service.svc* файл, содержащий строку:</span><span class="sxs-lookup"><span data-stu-id="3cd1c-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  <span data-ttu-id="3cd1c-117">Место *Service.svc* файл в виртуальный каталог Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="3cd1c-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="3cd1c-118">Настройка клиента с привязкой WSHttpBinding использования надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="3cd1c-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="3cd1c-119">Используйте [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки для создания кода из метаданных службы:</span><span class="sxs-lookup"><span data-stu-id="3cd1c-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="3cd1c-120">Создаваемый клиент содержит `ICalculator` интерфейс, определяющий контракт службы, которому должна удовлетворять реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="3cd1c-121">Созданное клиентское приложение также содержит реализацию `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="3cd1c-122">Обратите внимание, что информация об адресе и привязке не указан в любом месте внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="3cd1c-123">Не требуется писать код, чтобы получить сведения о адресе или привязке сведения из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-123">You aren't required to write code to retrieve the address or binding information information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="3cd1c-124">*Svcutil.exe* также создает конфигурацию для клиента, использующего <xref:System.ServiceModel.WSHttpBinding> класса.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="3cd1c-125">Имя файла конфигурации *App.config* при использовании [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cd1c-125">Name the configuration file *App.config* when using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="3cd1c-126">Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="3cd1c-127">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="3cd1c-128">Пример</span><span class="sxs-lookup"><span data-stu-id="3cd1c-128">Example</span></span>

<span data-ttu-id="3cd1c-129">Некоторые привязки, предоставляемые системой, по умолчанию поддерживают надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="3cd1c-130">Сюда входит следующее.</span><span class="sxs-lookup"><span data-stu-id="3cd1c-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="3cd1c-131">Пример того, как создать пользовательскую привязку, которая поддерживает надежные сеансы см. в разделе [как: Создание пользовательской привязки надежного сеанса с использованием HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="3cd1c-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cd1c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="3cd1c-132">See also</span></span>

[<span data-ttu-id="3cd1c-133">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="3cd1c-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
