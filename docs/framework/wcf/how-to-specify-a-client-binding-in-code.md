---
title: Практическое руководство. Задание привязки клиента в коде
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: ec5db7a305a63ac7ae9c2e2a7bb1c9c7691b8daa
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320889"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="cc04c-102">Практическое руководство. Задание привязки клиента в коде</span><span class="sxs-lookup"><span data-stu-id="cc04c-102">How to: Specify a Client Binding in Code</span></span>
<span data-ttu-id="cc04c-103">В этом примере создается клиент, предназначенный для использования службы калькулятора, и привязка этого клиента задается императивно в коде.</span><span class="sxs-lookup"><span data-stu-id="cc04c-103">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="cc04c-104">Клиент обращается к службе `CalculatorService`, которая реализует интерфейс `ICalculator`; как служба, так и клиент используют класс <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="cc04c-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="cc04c-105">В приведенной процедуре предполагается, что служба калькулятора выполняется.</span><span class="sxs-lookup"><span data-stu-id="cc04c-105">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="cc04c-106">Сведения о создании службы см. в разделе [как указать привязку службы в конфигурации](how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="cc04c-106">For information about building the service, see [How to: Specify a Service Binding in Configuration](how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="cc04c-107">Он также использует [средство служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF), которое позволяет автоматически создавать клиентские компоненты.</span><span class="sxs-lookup"><span data-stu-id="cc04c-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="cc04c-108">Этот инструмент создает код клиента для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="cc04c-108">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="cc04c-109">Клиент создается в два этапа.</span><span class="sxs-lookup"><span data-stu-id="cc04c-109">The client is built in two parts.</span></span> <span data-ttu-id="cc04c-110">Программа Svcutil.exe генерирует класс `ClientCalculator`, реализующий интерфейс `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="cc04c-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="cc04c-111">Затем данное клиентское приложение создается путем создания экземпляра класса `ClientCalculator` и задания привязки и адреса для службы в коде.</span><span class="sxs-lookup"><span data-stu-id="cc04c-111">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="cc04c-112">Исходный экземпляр этого примера см. в примере [басикбиндинг](./samples/basicbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="cc04c-112">For the source copy of this example, see the [BasicBinding](./samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="cc04c-113">Задание пользовательской привязки в коде</span><span class="sxs-lookup"><span data-stu-id="cc04c-113">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="cc04c-114">Из командной строки запустите программу Svcutil.exe, чтобы создать код из метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="cc04c-114">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```console  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2. <span data-ttu-id="cc04c-115">Создаваемый клиент содержит интерфейс `ICalculator`, определяющий контракт службы, которому должна удовлетворять реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="cc04c-115">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="cc04c-116">Создаваемый клиент также содержит реализацию класса `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="cc04c-116">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="cc04c-117">Создайте экземпляр класса `ClientCalculator`, использующего класс <xref:System.ServiceModel.BasicHttpBinding> в клиентском приложении, и вызовите операции службы по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="cc04c-117">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="cc04c-118">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="cc04c-118">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc04c-119">См. также</span><span class="sxs-lookup"><span data-stu-id="cc04c-119">See also</span></span>

- [<span data-ttu-id="cc04c-120">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="cc04c-120">Using Bindings to Configure Services and Clients</span></span>](using-bindings-to-configure-services-and-clients.md)
