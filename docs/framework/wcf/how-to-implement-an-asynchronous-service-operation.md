---
title: Практическое руководство. Асинхронная реализация операции службы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e5d2ea5-d8f8-4712-bd18-ea3c5461702c
ms.openlocfilehash: fd7a1399dd575ad1a4b6c95e0e0510670eb13b51
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802293"
---
# <a name="how-to-implement-an-asynchronous-service-operation"></a><span data-ttu-id="daaba-102">Практическое руководство. Асинхронная реализация операции службы</span><span class="sxs-lookup"><span data-stu-id="daaba-102">How to: Implement an Asynchronous Service Operation</span></span>
<span data-ttu-id="daaba-103">В приложениях Windows Communication Foundation (WCF) операция службы может быть реализована асинхронно или синхронно без указания клиенту способа его вызова.</span><span class="sxs-lookup"><span data-stu-id="daaba-103">In Windows Communication Foundation (WCF) applications, a service operation can be implemented asynchronously or synchronously without dictating to the client how to call it.</span></span> <span data-ttu-id="daaba-104">Например, асинхронные операции службы могут вызываться синхронно, а синхронные операции службы могут вызываться асинхронно.</span><span class="sxs-lookup"><span data-stu-id="daaba-104">For example, asynchronous service operations can be called synchronously, and synchronous service operations can be called asynchronously.</span></span> <span data-ttu-id="daaba-105">Пример асинхронного вызова операции в клиентском приложении см. [в разделе как вызывать операции службы асинхронно](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span><span class="sxs-lookup"><span data-stu-id="daaba-105">For an example that shows how to call an operation asynchronously in a client application, see [How to: Call Service Operations Asynchronously](./feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span> <span data-ttu-id="daaba-106">Дополнительные сведения о синхронных и асинхронных операциях см. в разделе [Разработка контрактов служб](designing-service-contracts.md) и [синхронных и асинхронных операций](synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="daaba-106">For more information about synchronous and asynchronous operations, see [Designing Service Contracts](designing-service-contracts.md) and [Synchronous and Asynchronous Operations](synchronous-and-asynchronous-operations.md).</span></span> <span data-ttu-id="daaba-107">В этом разделе описывается базовая структура асинхронной операции службы, код не завершен.</span><span class="sxs-lookup"><span data-stu-id="daaba-107">This topic describes the basic structure of an asynchronous service operation, the code is not complete.</span></span> <span data-ttu-id="daaba-108">Полный пример обеих сторон службы и клиента см. в разделе [асинхронный](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="daaba-108">For a complete example of both the service and client sides, see [Asynchronous](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms751505(v=vs.100)).</span></span>  
  
### <a name="implement-a-service-operation-asynchronously"></a><span data-ttu-id="daaba-109">Асинхронная реализация операции службы</span><span class="sxs-lookup"><span data-stu-id="daaba-109">Implement a service operation asynchronously</span></span>  
  
1. <span data-ttu-id="daaba-110">В контракте службы объявите пару асинхронных методов в соответствии с рекомендациями по асинхронной разработке для платформы .NET.</span><span class="sxs-lookup"><span data-stu-id="daaba-110">In your service contract, declare an asynchronous method pair according to the .NET asynchronous design guidelines.</span></span> <span data-ttu-id="daaba-111">Метод `Begin` принимает параметр, объект обратного вызова и объект состояния, а возвращает <xref:System.IAsyncResult?displayProperty=nameWithType>; соответствующий метод `End` принимает <xref:System.IAsyncResult?displayProperty=nameWithType> и возвращает возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="daaba-111">The `Begin` method takes a parameter, a callback object, and a state object, and returns a <xref:System.IAsyncResult?displayProperty=nameWithType> and a matching `End` method that takes a <xref:System.IAsyncResult?displayProperty=nameWithType> and returns the return value.</span></span> <span data-ttu-id="daaba-112">Дополнительные сведения о асинхронных вызовах см. в разделе [шаблоны разработки асинхронного программирования](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span><span class="sxs-lookup"><span data-stu-id="daaba-112">For more information about asynchronous calls, see [Asynchronous Programming Design Patterns](../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md).</span></span>  
  
2. <span data-ttu-id="daaba-113">Пометьте метод `Begin` пары асинхронных методов атрибутом <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> и задайте для свойства <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="daaba-113">Mark the `Begin` method of the asynchronous method pair with the <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType> attribute and set the <xref:System.ServiceModel.OperationContractAttribute.AsyncPattern%2A?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="daaba-114">Например, приведенный ниже код выполняет шаги 1 и 2.</span><span class="sxs-lookup"><span data-stu-id="daaba-114">For example, the following code performs steps 1 and 2.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#6)]
     [!code-vb[C_SyncAsyncClient#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#6)]  
  
3. <span data-ttu-id="daaba-115">Реализуйте пару методов `Begin/End` в классе своей службы в соответствии с рекомендациями по асинхронной разработке.</span><span class="sxs-lookup"><span data-stu-id="daaba-115">Implement the `Begin/End` method pair in your service class according to the asynchronous design guidelines.</span></span> <span data-ttu-id="daaba-116">Например, в следующем примере кода показана реализация, в которой строка записывается в консоль как в части `Begin`, так и в части `End` асинхронной операции службы, и возвращаемое значение операции `End` возвращается клиенту.</span><span class="sxs-lookup"><span data-stu-id="daaba-116">For example, the following code example shows an implementation in which a string is written to the console in both the `Begin` and `End` portions of the asynchronous service operation, and the return value of the `End` operation is returned to the client.</span></span> <span data-ttu-id="daaba-117">Полный пример кода см. в подразделе "Пример".</span><span class="sxs-lookup"><span data-stu-id="daaba-117">For the complete code example, see the Example section.</span></span>  
  
     [!code-csharp[C_SyncAsyncClient#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#3)]
     [!code-vb[C_SyncAsyncClient#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="daaba-118">Пример</span><span class="sxs-lookup"><span data-stu-id="daaba-118">Example</span></span>  
 <span data-ttu-id="daaba-119">В следующих примерах кода показаны:</span><span class="sxs-lookup"><span data-stu-id="daaba-119">The following code examples show:</span></span>  
  
1. <span data-ttu-id="daaba-120">Интерфейс контракта службы с:</span><span class="sxs-lookup"><span data-stu-id="daaba-120">A service contract interface with:</span></span>  
  
    1. <span data-ttu-id="daaba-121">Синхронной операцией `SampleMethod`.</span><span class="sxs-lookup"><span data-stu-id="daaba-121">A synchronous `SampleMethod` operation.</span></span>  
  
    2. <span data-ttu-id="daaba-122">Асинхронной операцией `BeginSampleMethod`.</span><span class="sxs-lookup"><span data-stu-id="daaba-122">An asynchronous `BeginSampleMethod` operation.</span></span>  
  
    3. <span data-ttu-id="daaba-123">Асинхронная `BeginServiceAsyncMethod`/`EndServiceAsyncMethod`ная пара операций.</span><span class="sxs-lookup"><span data-stu-id="daaba-123">An asynchronous `BeginServiceAsyncMethod`/`EndServiceAsyncMethod` operation pair.</span></span>  
  
2. <span data-ttu-id="daaba-124">Реализацией службы с использованием объекта <xref:System.IAsyncResult?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="daaba-124">A service implementation using a <xref:System.IAsyncResult?displayProperty=nameWithType> object.</span></span>  
  
 [!code-csharp[C_SyncAsyncClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_syncasyncclient/cs/services.cs#1)]
 [!code-vb[C_SyncAsyncClient#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_syncasyncclient/vb/services.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="daaba-125">См. также:</span><span class="sxs-lookup"><span data-stu-id="daaba-125">See also</span></span>

- [<span data-ttu-id="daaba-126">Разработка контрактов службы</span><span class="sxs-lookup"><span data-stu-id="daaba-126">Designing Service Contracts</span></span>](designing-service-contracts.md)
- [<span data-ttu-id="daaba-127">Синхронные и асинхронные операции</span><span class="sxs-lookup"><span data-stu-id="daaba-127">Synchronous and Asynchronous Operations</span></span>](synchronous-and-asynchronous-operations.md)
