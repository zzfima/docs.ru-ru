---
title: Конечные точки WCF и методы gRPC — gRPC для разработчиков WCF
description: Сравнение конечных точек WCF, объявленных с атрибутами ServiceContract и OperationContract, и методами gRPC, объявленными в protobuf
ms.date: 09/02/2019
ms.openlocfilehash: 1bc6ecbc73bfc0a58393e4c28672b897ed6f2f15
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503432"
---
# <a name="wcf-endpoints-and-grpc-methods"></a><span data-ttu-id="e3c86-103">Конечные точки WCF и методы gRPC</span><span class="sxs-lookup"><span data-stu-id="e3c86-103">WCF endpoints and gRPC methods</span></span>

<span data-ttu-id="e3c86-104">В Windows Communication Foundation (WCF) при написании кода приложения используется один из следующих методов.</span><span class="sxs-lookup"><span data-stu-id="e3c86-104">In Windows Communication Foundation (WCF), when you're writing your application code, you use one of the following methods:</span></span>

- <span data-ttu-id="e3c86-105">Код приложения записывается в класс и оформляются методы с помощью атрибута [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e3c86-105">You write the application code in a class and decorate methods with the [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute.</span></span>
- <span data-ttu-id="e3c86-106">Вы объявляете интерфейс для службы и добавляете в интерфейс атрибуты [OperationContract](xref:System.ServiceModel.OperationContractAttribute) .</span><span class="sxs-lookup"><span data-stu-id="e3c86-106">You declare an interface for the service and add [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attributes to the interface.</span></span>

<span data-ttu-id="e3c86-107">Например, WCF, эквивалентная службе `greet.proto` Гритер, может быть написана следующим образом:</span><span class="sxs-lookup"><span data-stu-id="e3c86-107">For example, the WCF equivalent of the `greet.proto` Greeter service might be written as follows:</span></span>

```csharp
[ServiceContract]
public interface IGreeterService
{
    [OperationContract]
    string SayHello(string name);
}
```

<span data-ttu-id="e3c86-108">В главе 3 показано, что определения сообщений protobuf используются для создания классов данных.</span><span class="sxs-lookup"><span data-stu-id="e3c86-108">Chapter 3 showed that Protobuf message definitions are used to generate data classes.</span></span> <span data-ttu-id="e3c86-109">Объявления служб и методов используются для создания базовых классов, наследуемых от, для реализации службы.</span><span class="sxs-lookup"><span data-stu-id="e3c86-109">Service and method declarations are used to generate base classes that you inherit from to implement the service.</span></span> <span data-ttu-id="e3c86-110">Вы просто объявляете методы для реализации в файле `.proto`, и компилятор создает базовый класс с виртуальными методами, которые необходимо переопределить.</span><span class="sxs-lookup"><span data-stu-id="e3c86-110">You just declare the methods to be implemented in the `.proto` file, and the compiler generates a base class with virtual methods that you must override.</span></span>

## <a name="operationcontract-properties"></a><span data-ttu-id="e3c86-111">Свойства OperationContract</span><span class="sxs-lookup"><span data-stu-id="e3c86-111">OperationContract properties</span></span>

<span data-ttu-id="e3c86-112">Атрибут [OperationContract](xref:System.ServiceModel.OperationContractAttribute) имеет свойства для управления и уточнения его работы.</span><span class="sxs-lookup"><span data-stu-id="e3c86-112">The [OperationContract](xref:System.ServiceModel.OperationContractAttribute) attribute has properties to control or refine how it works.</span></span> <span data-ttu-id="e3c86-113">методы gRPC не предлагают этот тип элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e3c86-113">gRPC methods don't offer this type of control.</span></span> <span data-ttu-id="e3c86-114">В следующей таблице перечислены эти `OperationContract` свойства и описано, как заданные ими функции являются (или нет) обработаны с помощью в gRPC:</span><span class="sxs-lookup"><span data-stu-id="e3c86-114">The following table lists those `OperationContract` properties and describes how the functionality that they specify is (or isn't) dealt with in gRPC:</span></span>

| <span data-ttu-id="e3c86-115">Свойство `OperationContract`</span><span class="sxs-lookup"><span data-stu-id="e3c86-115">`OperationContract` property</span></span> | <span data-ttu-id="e3c86-116">gRPC</span><span class="sxs-lookup"><span data-stu-id="e3c86-116">gRPC</span></span>                                             |
| ---------------------------- | ------------------------------------------------ |
| <xref:System.ServiceModel.OperationContractAttribute.Action>             | <span data-ttu-id="e3c86-117">URI идентифицирует операцию.</span><span class="sxs-lookup"><span data-stu-id="e3c86-117">A URI identifies the operation.</span></span> <span data-ttu-id="e3c86-118">gRPC использует имя `package`, `service`и `rpc` из файла `.proto`.</span><span class="sxs-lookup"><span data-stu-id="e3c86-118">gRPC uses the name of `package`, `service`, and `rpc` from the `.proto` file.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern>       | <span data-ttu-id="e3c86-119">Все методы службы gRPC возвращают `Task` объекты.</span><span class="sxs-lookup"><span data-stu-id="e3c86-119">All gRPC service methods return `Task` objects.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsInitiating>       | <span data-ttu-id="e3c86-120">См. абзац после этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e3c86-120">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsOneWay>           | <span data-ttu-id="e3c86-121">Односторонние методы gRPC возвращают `Empty` результаты или используют потоковую передачу клиента.</span><span class="sxs-lookup"><span data-stu-id="e3c86-121">One-way gRPC methods return `Empty` results or use client streaming.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.IsTerminating>      | <span data-ttu-id="e3c86-122">См. абзац после этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="e3c86-122">See the paragraph after this table.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.Name>               | <span data-ttu-id="e3c86-123">Это свойство связано с SOAP и не имеет смысла в gRPC.</span><span class="sxs-lookup"><span data-stu-id="e3c86-123">This property is SOAP related and has no meaning in gRPC.</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ProtectionLevel>    | <span data-ttu-id="e3c86-124">Шифрование сообщений отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e3c86-124">There's no message encryption.</span></span> <span data-ttu-id="e3c86-125">Сетевое шифрование обрабатывается на транспортном уровне (TLS через HTTP/2).</span><span class="sxs-lookup"><span data-stu-id="e3c86-125">Network encryption is handled at the transport layer (TLS over HTTP/2).</span></span> |
| <xref:System.ServiceModel.OperationContractAttribute.ReplyAction>        | <span data-ttu-id="e3c86-126">Это свойство связано с SOAP и не имеет смысла в gRPC.</span><span class="sxs-lookup"><span data-stu-id="e3c86-126">This property is SOAP related and has no meaning in gRPC.</span></span> |

<span data-ttu-id="e3c86-127">Свойство `IsInitiating` позволяет указать, что метод в [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) не может быть первым методом, вызванным как часть сеанса.</span><span class="sxs-lookup"><span data-stu-id="e3c86-127">The `IsInitiating` property lets you indicate that a method within [ServiceContract](xref:System.ServiceModel.ServiceContractAttribute) can't be the first method called as part of a session.</span></span> <span data-ttu-id="e3c86-128">Свойство `IsTerminating` заставляет сервер закрыть сеанс после вызова операции (или клиента, если свойство используется в клиенте обратного вызова).</span><span class="sxs-lookup"><span data-stu-id="e3c86-128">The `IsTerminating` property causes the server to close the session after an operation is called (or the client, if the property is used on a callback client).</span></span> <span data-ttu-id="e3c86-129">В gRPC потоки создаются с помощью отдельных методов и закрываются явным образом.</span><span class="sxs-lookup"><span data-stu-id="e3c86-129">In gRPC, streams are created by single methods and closed explicitly.</span></span> <span data-ttu-id="e3c86-130">См. раздел [потоковая передача gRPC](rpc-types.md#grpc-streaming).</span><span class="sxs-lookup"><span data-stu-id="e3c86-130">See [gRPC streaming](rpc-types.md#grpc-streaming).</span></span>

<span data-ttu-id="e3c86-131">Дополнительные сведения о безопасности и шифровании gRPC см. в [главе 6](security.md).</span><span class="sxs-lookup"><span data-stu-id="e3c86-131">For more information on gRPC security and encryption, see [chapter 6](security.md).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e3c86-132">[Назад](wcf-services-to-grpc-comparison.md)
>[Вперед](wcf-bindings.md)</span><span class="sxs-lookup"><span data-stu-id="e3c86-132">[Previous](wcf-services-to-grpc-comparison.md)
[Next](wcf-bindings.md)</span></span>
