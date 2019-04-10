---
title: Практическое руководство. Создание двухстороннего контракта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- duplex contracts [WCF]
ms.assetid: 500a75b6-998a-47d5-8e3b-24e3aba2a434
ms.openlocfilehash: c00e5d8e50de89d3d4d346ccddc50282f24735b2
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332135"
---
# <a name="how-to-create-a-duplex-contract"></a><span data-ttu-id="a9bdc-102">Практическое руководство. Создание двухстороннего контракта</span><span class="sxs-lookup"><span data-stu-id="a9bdc-102">How to: Create a Duplex Contract</span></span>
<span data-ttu-id="a9bdc-103">В этом разделе приведены основные этапы создания методов, использующих дуплексные (двухсторонние) контракты.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-103">This topic shows the basic steps to create methods that use a duplex (two-way) contract.</span></span> <span data-ttu-id="a9bdc-104">Дуплексный контракт позволяет клиентам и серверам взаимодействовать друг с другом независимо (клиент может инициировать вызовы сервера, а сервер - вызовы клиента).</span><span class="sxs-lookup"><span data-stu-id="a9bdc-104">A duplex contract allows clients and servers to communicate with each other independently so that either can initiate calls to the other.</span></span> <span data-ttu-id="a9bdc-105">Дуплексный контракт-это один из трех шаблонов сообщений, доступных для служб Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="a9bdc-105">The duplex contract is one of three message patterns available to Windows Communication Foundation (WCF) services.</span></span> <span data-ttu-id="a9bdc-106">Две другие схемы обмена сообщениями - это односторонний обмен и запрос-ответ.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-106">The other two message patterns are one-way and request-reply.</span></span> <span data-ttu-id="a9bdc-107">Дуплексный контракт состоит из двух односторонних контрактов между клиентом и сервером, при этом не требуется корреляция между вызовами методов.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-107">A duplex contract consists of two one-way contracts between the client and the server and does not require that the method calls be correlated.</span></span> <span data-ttu-id="a9bdc-108">Контракт этого типа следует использовать, если служба должна запрашивать у клиента дополнительную информацию или в явном виде создавать события в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-108">Use this kind of contract when your service must query the client for more information or explicitly raise events on the client.</span></span> <span data-ttu-id="a9bdc-109">Дополнительные сведения о создании клиентского приложения для дуплексного контракта см. в разделе [как: Доступ к службам с дуплексным контрактом](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a9bdc-109">For more information about creating a client application for a duplex contract, see [How to: Access Services with a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md).</span></span> <span data-ttu-id="a9bdc-110">Работающий пример см. в разделе [дуплексного](../../../../docs/framework/wcf/samples/duplex.md) образца.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-110">For a working sample, see the [Duplex](../../../../docs/framework/wcf/samples/duplex.md) sample.</span></span>  
  
### <a name="to-create-a-duplex-contract"></a><span data-ttu-id="a9bdc-111">Создание двухстороннего контракта</span><span class="sxs-lookup"><span data-stu-id="a9bdc-111">To create a duplex contract</span></span>  
  
1. <span data-ttu-id="a9bdc-112">Создайте интерфейс, образующий серверную часть дуплексного контракта.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-112">Create the interface that makes up the server side of the duplex contract.</span></span>  
  
2. <span data-ttu-id="a9bdc-113">Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-113">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#3)]
     [!code-vb[S_WS_DualHttp#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#3)]  
  
3. <span data-ttu-id="a9bdc-114">Объявите в интерфейсе подписи методов.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-114">Declare the method signatures in the interface.</span></span>  
  
4. <span data-ttu-id="a9bdc-115">Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждой подписи метода, которая должна входить в открытый контракт.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-115">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
5. <span data-ttu-id="a9bdc-116">Создайте интерфейс обратного вызова, определяющий набор операций, которые служба может вызывать в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-116">Create the callback interface that defines the set of operations that the service can invoke on the client.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#4)]
     [!code-vb[S_WS_DualHttp#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#4)]  
  
6. <span data-ttu-id="a9bdc-117">Объявите подписи методов в интерфейсе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-117">Declare the method signatures in the callback interface.</span></span>  
  
7. <span data-ttu-id="a9bdc-118">Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждой подписи метода, которая должна входить в открытый контракт.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-118">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method signature that must be part of the public contract.</span></span>  
  
8. <span data-ttu-id="a9bdc-119">Объедините эти два интерфейса в дуплексный контракт, задав для свойства <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> в основном интерфейсе тип интерфейса обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-119">Link the two interfaces into a duplex contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.CallbackContract%2A> property in the primary interface to the type of the callback interface.</span></span>  
  
### <a name="to-call-methods-on-the-client"></a><span data-ttu-id="a9bdc-120">Вызов методов в клиенте</span><span class="sxs-lookup"><span data-stu-id="a9bdc-120">To call methods on the client</span></span>  
  
1. <span data-ttu-id="a9bdc-121">В реализации основного контракта на стороне службы объявите переменную для интерфейса обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-121">In the service's implementation of the primary contract, declare a variable for the callback interface.</span></span>  
  
2. <span data-ttu-id="a9bdc-122">Присвойте переменной ссылку на объект, возвращаемый методом <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> класса <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-122">Set the variable to the object reference returned by the <xref:System.ServiceModel.OperationContext.GetCallbackChannel%2A> method of the <xref:System.ServiceModel.OperationContext> class.</span></span>  
  
     [!code-csharp[S_WS_DualHttp#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#1)]
     [!code-vb[S_WS_DualHttp#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#1)]  
  
     [!code-csharp[S_WS_DualHttp#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#2)]
     [!code-vb[S_WS_DualHttp#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#2)]  
  
3. <span data-ttu-id="a9bdc-123">Вызовите методы, определенные в интерфейсе обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-123">Call the methods defined by the callback interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9bdc-124">Пример</span><span class="sxs-lookup"><span data-stu-id="a9bdc-124">Example</span></span>  
 <span data-ttu-id="a9bdc-125">В следующем примере кода демонстрируется дуплексное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-125">The following code example demonstrates duplex communication.</span></span> <span data-ttu-id="a9bdc-126">Контракт службы содержит операции службы для перемещения вперед или назад.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-126">The service’s contract contains service operations for moving forward and backward.</span></span> <span data-ttu-id="a9bdc-127">Контракт клиента содержит операцию службы для сообщения о положении.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-127">The client’s contract contains a service operation for reporting its position.</span></span>  
  
 [!code-csharp[S_WS_DualHttp#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ws_dualhttp/cs/service.cs#5)]
 [!code-vb[S_WS_DualHttp#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_ws_dualhttp/vb/service.vb#5)]  
  
-   <span data-ttu-id="a9bdc-128">Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> обеспечивает автоматическое создание определения контракта службы в языке описания служб (WSDL).</span><span class="sxs-lookup"><span data-stu-id="a9bdc-128">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes allows the automatic generation of service contract definitions in the Web Services Description Language (WSDL).</span></span>  
  
-   <span data-ttu-id="a9bdc-129">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для извлечения документа WSDL и (необязательно) код и конфигурацию для клиента.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-129">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to retrieve the WSDL document and (optional) code and configuration for a client.</span></span>  
  
-   <span data-ttu-id="a9bdc-130">Конечные точки, предоставляющие дуплексные службы, должны быть безопасными.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-130">Endpoints exposing duplex services must be secured.</span></span> <span data-ttu-id="a9bdc-131">Когда служба получает дуплексное сообщение, она проверяет элемент ReplyTo входящего сообщения, чтобы определить, куда отправлять ответ.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-131">When a service receives a duplex message, it looks at the ReplyTo in that incoming message to determine where to send the reply.</span></span> <span data-ttu-id="a9bdc-132">Если канал не является безопасным, ненадежный клиент может послать вредоносное сообщение с указанием компьютера для атаки в элементе ReplyTo, что приведет к атаке типа "отказ в обслуживании" на этот компьютер.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-132">If the channel is not secured, then an untrusted client could send a malicious message with a target machine's ReplyTo, leading to a denial of service of the target machine.</span></span> <span data-ttu-id="a9bdc-133">В случае обычной передачи сообщений по схеме "запрос-ответ" это не является проблемой, так как элемент ReplyTo игнорируется, а ответное сообщение передается по тому каналу, по которому поступило исходное сообщение.</span><span class="sxs-lookup"><span data-stu-id="a9bdc-133">With regular request-reply messages, this is not an issue, because the ReplyTo is ignored and the response is sent on the channel the original message came in on.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bdc-134">См. также</span><span class="sxs-lookup"><span data-stu-id="a9bdc-134">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="a9bdc-135">Практическое руководство. Доступ к службам с дуплексным контрактом</span><span class="sxs-lookup"><span data-stu-id="a9bdc-135">How to: Access Services with a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [<span data-ttu-id="a9bdc-136">Дуплекс</span><span class="sxs-lookup"><span data-stu-id="a9bdc-136">Duplex</span></span>](../../../../docs/framework/wcf/samples/duplex.md)
- [<span data-ttu-id="a9bdc-137">Проектирование и реализация служб</span><span class="sxs-lookup"><span data-stu-id="a9bdc-137">Designing and Implementing Services</span></span>](../../../../docs/framework/wcf/designing-and-implementing-services.md)
- [<span data-ttu-id="a9bdc-138">Практическое руководство. Определение контракта службы</span><span class="sxs-lookup"><span data-stu-id="a9bdc-138">How to: Define a Service Contract</span></span>](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [<span data-ttu-id="a9bdc-139">Сеанс</span><span class="sxs-lookup"><span data-stu-id="a9bdc-139">Session</span></span>](../../../../docs/framework/wcf/samples/session.md)
