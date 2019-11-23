---
title: Конечные точки WCF и методы gRPC — gRPC для разработчиков WCF
description: Сравнение конечных точек WCF, объявленных с атрибутами ServiceContract и OperationContract, и методами gRPC, объявленными в protobuf
ms.date: 09/02/2019
ms.openlocfilehash: 763862a363afc6aab72335050cf4822754816c7a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966926"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="a6e4d-103">Конечные точки WCF и методы gRPC</span><span class="sxs-lookup"><span data-stu-id="a6e4d-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="a6e4d-104">В WCF при написании кода приложения используется один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-104">In WCF, when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="a6e4d-105">Код приложения записывается в класс и оформляются методы с помощью атрибута [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .</span><span class="sxs-lookup"><span data-stu-id="a6e4d-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="a6e4d-106">Вы объявляете интерфейс для службы и добавляете в интерфейс атрибуты [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .</span><span class="sxs-lookup"><span data-stu-id="a6e4d-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="a6e4d-107">Например, WCF, эквивалентная службе `greet.proto` Гритер, может быть написана следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a6e4d-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="a6e4d-108">В главе 3 показано, что определения сообщений protobuf используются для создания классов данных.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="a6e4d-109">Объявления служб и методов используются для создания базовых классов, наследуемых от, для реализации службы.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="a6e4d-110">Вы просто объявляете методы для реализации в файле `.proto`, и компилятор создает базовый класс с виртуальными методами, которые необходимо переопределить.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="a6e4d-111">Свойства OperationContract</span><span class="sxs-lookup"><span data-stu-id="a6e4d-111">OperationContract properties</span></span>

<span data-ttu-id="a6e4d-112">Атрибут [OperationContract](xref:System.ServiceModel.OperationContractAttribute) имеет свойства для управления и уточнения его работы.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="a6e4d-113">методы gRPC не предлагают этот тип элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-113">gRPC methods don’t offer this type of control.</span></span> <span data-ttu-id="a6e4d-114">В следующей таблице задаются эти `OperationContract` свойства и то, как заданные ими функции имеют (или не) обрабатываются в gRPC:</span><span class="sxs-lookup"><span data-stu-id="a6e4d-114">The following table sets out those `OperationContract` properties and how the functionality they specify is (or isn’t) dealt with in gRPC:</span></span>

| <span data-ttu-id="a6e4d-115">Свойство`OperationContract`</span><span class="sxs-lookup"><span data-stu-id="a6e4d-115">`OperationContract` property</span></span> | <span data-ttu-id="a6e4d-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="a6e4d-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="a6e4d-117">URI, идентифицирующий операцию.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-117">URI identifying the operation.</span></span> <span data-ttu-id="a6e4d-118">gRPC использует имя `package`, `service` и `rpc` из файла `.proto`.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-118">gRPC uses the name of the `package`, `service` and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="a6e4d-119">Все методы службы gRPC возвращают `Task` объекты.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="a6e4d-120">См. примечание ниже.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-120">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="a6e4d-121">Односторонние методы gRPC возвращают `Empty` результаты или используют потоковую передачу клиента.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="a6e4d-122">См. примечание ниже.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-122">See note below.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="a6e4d-123">Связанные с SOAP, без смысла в gRPC.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-123">SOAP-related, no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="a6e4d-124">Без шифрования сообщений; Сетевое шифрование, обрабатываемое на транспортном уровне (TLS по HTTP/2).</span><span class="sxs-lookup"><span data-stu-id="a6e4d-124">No message encryption; network encryption handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="a6e4d-125">Связанные с SOAP, без смысла в gRPC.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-125">SOAP-related, no meaning in gRPC.</span></span> |

<span data-ttu-id="a6e4d-126">Свойство `IsInitiating` позволяет указать, что метод в [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) не может быть первым методом, вызванным как часть сеанса.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-126">The `IsInitiating` property lets you indicate that a method within a [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="a6e4d-127">Свойство `IsTerminating` заставляет сервер закрыть сеанс после вызова операции (или клиента, если он используется в клиенте обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="a6e4d-127">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if used on a callback client).</span></span> <span data-ttu-id="a6e4d-128">В gRPC потоки создаются с помощью отдельных методов и закрываются явным образом.</span><span class="sxs-lookup"><span data-stu-id="a6e4d-128">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="a6e4d-129">См. раздел [потоковая передача gRPC](rpc-types.md#grpc-streaming).</span><span class="sxs-lookup"><span data-stu-id="a6e4d-129">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="a6e4d-130">Дополнительные сведения о безопасности и шифровании gRPC см. в [главе 6](security.md).</span><span class="sxs-lookup"><span data-stu-id="a6e4d-130">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a6e4d-131">[Назад](wcf-services-to-grpc-comparison.md)
>[Вперед](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="a6e4d-131">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
