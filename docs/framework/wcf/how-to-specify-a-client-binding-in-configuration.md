---
title: Практическое руководство. Указание привязки клиента в конфигурации
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2441fd7507c5bb368405685598480650114b76a9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="e773c-102">Практическое руководство. Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="e773c-102">How to: Specify a Client Binding in Configuration</span></span>
<span data-ttu-id="e773c-103">В этом примере создается клиентское консольное приложение, предназначенное для использования службы калькулятора, и привязка этого клиента задается декларативно в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e773c-103">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="e773c-104">Клиент обращается к службе `CalculatorService`, которая реализует интерфейс `ICalculator`; как служба, так и клиент используют класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e773c-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="e773c-105">В приведенной процедуре предполагается, что служба калькулятора работает.</span><span class="sxs-lookup"><span data-stu-id="e773c-105">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="e773c-106">Сведения о создании службы см. в разделе [как: Укажите привязку службы в конфигурации](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="e773c-106">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="e773c-107">Она также использует [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) , [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] предоставляет для автоматического создания клиентских компонентов.</span><span class="sxs-lookup"><span data-stu-id="e773c-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) that [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] provides to automatically generate the client components.</span></span> <span data-ttu-id="e773c-108">Инструмент создает код и конфигурацию клиента для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="e773c-108">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="e773c-109">Клиент создается в два этапа.</span><span class="sxs-lookup"><span data-stu-id="e773c-109">The client is built in two parts.</span></span> <span data-ttu-id="e773c-110">Программа Svcutil.exe генерирует класс `ClientCalculator`, реализующий интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="e773c-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="e773c-111">Затем данное клиентское приложение создается путем конструирования экземпляра класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="e773c-111">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="e773c-112">В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.</span><span class="sxs-lookup"><span data-stu-id="e773c-112">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="e773c-113">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="e773c-113">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="e773c-114">В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="e773c-114">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="e773c-115">Можно выполнять все следующие действия по настройке с помощью [средство редактирования конфигурации (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e773c-115">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="e773c-116">Исходная копия в этом примере в разделе [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) образца.</span><span class="sxs-lookup"><span data-stu-id="e773c-116">For the source copy of this example, see the [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="e773c-117">Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="e773c-117">Specifying a client binding in configuration</span></span>  
  
1.  <span data-ttu-id="e773c-118">Из командной строки запустите программу Svcutil.exe, чтобы создать код из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="e773c-118">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2.  <span data-ttu-id="e773c-119">Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="e773c-119">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3.  <span data-ttu-id="e773c-120">Создаваемый клиент также содержит реализацию класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="e773c-120">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4.  <span data-ttu-id="e773c-121">Программа Svcutil.exe также создает конфигурацию для клиента, использующего класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e773c-121">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="e773c-122">При использовании Visual Studio, назовите этот файл App.config. Обратите внимание, что информация об адресе и привязке нигде внутри реализации службы не указывается.</span><span class="sxs-lookup"><span data-stu-id="e773c-122">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="e773c-123">Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.</span><span class="sxs-lookup"><span data-stu-id="e773c-123">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]   
            
5.  <span data-ttu-id="e773c-124">Создайте экземпляр класса `ClientCalculator` в приложении, затем вызовите операции службы.</span><span class="sxs-lookup"><span data-stu-id="e773c-124">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6.  <span data-ttu-id="e773c-125">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="e773c-125">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e773c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e773c-126">See Also</span></span>  
 [<span data-ttu-id="e773c-127">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e773c-127">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
