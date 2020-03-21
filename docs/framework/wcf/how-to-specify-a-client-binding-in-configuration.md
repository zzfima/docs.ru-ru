---
title: Практическое руководство. Указание привязки клиента в конфигурации
ms.date: 03/30/2017
ms.assetid: 4a7c79aa-50ee-4991-891e-adc0599323a7
ms.openlocfilehash: 574f56173c2acfcf41a5e9a9e99abe45281e3636
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184035"
---
# <a name="how-to-specify-a-client-binding-in-configuration"></a><span data-ttu-id="46d24-102">Практическое руководство. Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="46d24-102">How to: Specify a Client Binding in Configuration</span></span>
<span data-ttu-id="46d24-103">В этом примере создается клиентское консольное приложение, предназначенное для использования службы калькулятора, и привязка этого клиента задается декларативно в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="46d24-103">In this example, a client console application is created to use a calculator service, and the binding for that client is specified declaratively in configuration.</span></span> <span data-ttu-id="46d24-104">Клиент обращается к службе `CalculatorService`, которая реализует интерфейс `ICalculator`; как служба, так и клиент используют класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="46d24-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="46d24-105">В приведенной процедуре предполагается, что служба калькулятора работает.</span><span class="sxs-lookup"><span data-stu-id="46d24-105">The procedure outlined assumes that the calculator service is running.</span></span> <span data-ttu-id="46d24-106">Для получения информации о том, как создать [службу, см.](how-to-specify-a-service-binding-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="46d24-106">For information about how to build the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="46d24-107">Он также использует [Сервисмодель Метаданные Утилита инструмент (Svcutil.exe),](servicemodel-metadata-utility-tool-svcutil-exe.md) что Windows Communication Foundation (WCF) предоставляет для автоматического создания компонентов клиента.</span><span class="sxs-lookup"><span data-stu-id="46d24-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) that Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="46d24-108">Инструмент создает код и конфигурацию клиента для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="46d24-108">The tool generates the client code and configuration for accessing the service.</span></span>  
  
 <span data-ttu-id="46d24-109">Клиент создается в два этапа.</span><span class="sxs-lookup"><span data-stu-id="46d24-109">The client is built in two parts.</span></span> <span data-ttu-id="46d24-110">Программа Svcutil.exe генерирует класс `ClientCalculator`, реализующий интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="46d24-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="46d24-111">Затем данное клиентское приложение создается путем конструирования экземпляра класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="46d24-111">This client application is then constructed by constructing an instance of `ClientCalculator`.</span></span>  
  
 <span data-ttu-id="46d24-112">В большинстве случаев рекомендуется указывать привязку и адрес декларативно в конфигурации, а не принудительно в коде.</span><span class="sxs-lookup"><span data-stu-id="46d24-112">It is usually the best practice to specify the binding and address information declaratively in configuration rather than imperatively in code.</span></span> <span data-ttu-id="46d24-113">Как правило, определять конечные точки в коде непрактично, поскольку привязки и адреса для развернутой службы чаще всего отличаются от привязок и адресов, используемых в процессе разработки службы.</span><span class="sxs-lookup"><span data-stu-id="46d24-113">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="46d24-114">В общем случае, если не указывать привязку и адрес в коде, их можно изменять без повторной компиляции или повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="46d24-114">More generally, keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
 <span data-ttu-id="46d24-115">Вы можете выполнить все следующие шаги конфигурации с помощью [инструмента редактора конфигурации (SvcConfigEditor.exe).](configuration-editor-tool-svcconfigeditor-exe.md)</span><span class="sxs-lookup"><span data-stu-id="46d24-115">You can perform all of the following configuration steps by using the [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="46d24-116">В исходной копии этого [BasicBinding](./samples/basicbinding.md) примера см.</span><span class="sxs-lookup"><span data-stu-id="46d24-116">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="specifying-a-client-binding-in-configuration"></a><span data-ttu-id="46d24-117">Указание привязки клиента в конфигурации</span><span class="sxs-lookup"><span data-stu-id="46d24-117">Specifying a client binding in configuration</span></span>  
  
1. <span data-ttu-id="46d24-118">Из командной строки запустите программу Svcutil.exe, чтобы создать код из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="46d24-118">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="46d24-119">Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="46d24-119">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#1)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#1)]  
  
3. <span data-ttu-id="46d24-120">Создаваемый клиент также содержит реализацию класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="46d24-120">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/generatedclient.cs#2)]
     [!code-csharp[C_HowTo_ConfigureClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/source.cs#2)]  
  
4. <span data-ttu-id="46d24-121">Программа Svcutil.exe также создает конфигурацию для клиента, использующего класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="46d24-121">Svcutil.exe also generates the configuration for the client that uses the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span> <span data-ttu-id="46d24-122">При использовании Visual Studio назовите этот файл App.config. Обратите внимание, что адрес и обязательная информация нигде не указаны внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="46d24-122">When using Visual Studio, name this file App.config. Note that the address and binding information are not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="46d24-123">Кроме того, для извлечения этих сведений из файла конфигурации не требуется писать код.</span><span class="sxs-lookup"><span data-stu-id="46d24-123">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-xml[C_HowTo_ConfigureClientBinding#100](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/common/client.exe.config#100)]

5. <span data-ttu-id="46d24-124">Создайте экземпляр класса `ClientCalculator` в приложении, затем вызовите операции службы.</span><span class="sxs-lookup"><span data-stu-id="46d24-124">Create an instance of the `ClientCalculator` in an application, and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_ConfigureClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureclientbinding/cs/client.cs#3)]  
  
6. <span data-ttu-id="46d24-125">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="46d24-125">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d24-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="46d24-126">See also</span></span>

- [<span data-ttu-id="46d24-127">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="46d24-127">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
