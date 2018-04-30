---
title: Практическое руководство. Создание контракта типа "запрос-ответ"
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a272eaa88a53814daea9d515550a37f7991ecb8
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-request-reply-contract"></a><span data-ttu-id="5eaec-102">Практическое руководство. Создание контракта типа "запрос-ответ"</span><span class="sxs-lookup"><span data-stu-id="5eaec-102">How to: Create a Request-Reply Contract</span></span>
<span data-ttu-id="5eaec-103">Контракт «запрос-ответ» указывает метод, который возвращает ответ.</span><span class="sxs-lookup"><span data-stu-id="5eaec-103">A request-reply contract specifies a method that returns a reply.</span></span> <span data-ttu-id="5eaec-104">Необходима отправка ответа и его корреляция запросу согласно условиям этого контракта.</span><span class="sxs-lookup"><span data-stu-id="5eaec-104">The reply must be sent and correlated to the request under the terms of this contract.</span></span> <span data-ttu-id="5eaec-105">Даже если метод не возвращает ответ (`void` в C# или `Sub` в Visual Basic), инфраструктура создает и отправляет вызывающему объекту пустое сообщение.</span><span class="sxs-lookup"><span data-stu-id="5eaec-105">Even if the method returns no reply (`void` in C#, or a `Sub` in Visual Basic), the infrastructure creates and sends an empty message to the caller.</span></span> <span data-ttu-id="5eaec-106">Чтобы запретить отправку пустого ответного сообщения, используйте для операции односторонний контракт.</span><span class="sxs-lookup"><span data-stu-id="5eaec-106">To prevent the sending of an empty reply message, use a one-way contract for the operation.</span></span>  
  
### <a name="to-create-a-request-reply-contract"></a><span data-ttu-id="5eaec-107">Создание контракта типа запрос-ответ</span><span class="sxs-lookup"><span data-stu-id="5eaec-107">To create a request-reply contract</span></span>  
  
1.  <span data-ttu-id="5eaec-108">Создайте интерфейс на любом языке программирования.</span><span class="sxs-lookup"><span data-stu-id="5eaec-108">Create an interface in the programming language of your choice.</span></span>  
  
2.  <span data-ttu-id="5eaec-109">Примените атрибут <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="5eaec-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the interface.</span></span>  
  
3.  <span data-ttu-id="5eaec-110">Примените атрибут <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который могут вызывать клиенты.</span><span class="sxs-lookup"><span data-stu-id="5eaec-110">Apply the <xref:System.ServiceModel.OperationContractAttribute> attribute to each method that clients can invoke.</span></span>  
  
4.  <span data-ttu-id="5eaec-111">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="5eaec-111">Optional.</span></span> <span data-ttu-id="5eaec-112">Установите свойство <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> в значение `true`, чтобы избежать отправки пустого ответного сообщения.</span><span class="sxs-lookup"><span data-stu-id="5eaec-112">Set the value of the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `true` to prevent the sending of an empty reply message.</span></span> <span data-ttu-id="5eaec-113">По умолчанию все операции используют контракты «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="5eaec-113">By default, all operations are request-reply contracts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5eaec-114">Пример</span><span class="sxs-lookup"><span data-stu-id="5eaec-114">Example</span></span>  
 <span data-ttu-id="5eaec-115">В следующем примере определяется контракт для службы калькулятора, предоставляющей методы `Add` и `Subtract`.</span><span class="sxs-lookup"><span data-stu-id="5eaec-115">The following sample defines a contract for a calculator service that provides `Add` and `Subtract` methods.</span></span> <span data-ttu-id="5eaec-116">Метод `Multiply` не является частью контракта, поскольку он не отмечен классом <xref:System.ServiceModel.OperationContractAttribute>, а потому недоступен клиентам.</span><span class="sxs-lookup"><span data-stu-id="5eaec-116">The `Multiply` method is not part of the contract because it is not marked by the <xref:System.ServiceModel.OperationContractAttribute> class and so it is not accessible to clients.</span></span>  
  
```
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
-   <span data-ttu-id="5eaec-117">Дополнительные сведения об указании контрактов операции см. в разделе <xref:System.ServiceModel.OperationContractAttribute> класса и <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="5eaec-117">For more information about how to specify operation contracts, see the <xref:System.ServiceModel.OperationContractAttribute> class and the <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property.</span></span>  
  
-   <span data-ttu-id="5eaec-118">Применение атрибутов <xref:System.ServiceModel.ServiceContractAttribute> и <xref:System.ServiceModel.OperationContractAttribute> вызывает автоматическое создание определений контракта службы в документе WSDL после развертывания службы.</span><span class="sxs-lookup"><span data-stu-id="5eaec-118">Applying the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes causes the automatic generation of service contract definitions in a Web Services Description Language (WSDL) document once the service is deployed.</span></span> <span data-ttu-id="5eaec-119">Документ загружается путем добавления `?wsdl` к базовому адресу HTTP для службы,</span><span class="sxs-lookup"><span data-stu-id="5eaec-119">The document is downloaded by appending `?wsdl` to the HTTP base address for the service.</span></span> <span data-ttu-id="5eaec-120">Например `http://microsoft/CalculatorService?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="5eaec-120">For example, `http://microsoft/CalculatorService?wsdl`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5eaec-121">См. также</span><span class="sxs-lookup"><span data-stu-id="5eaec-121">See Also</span></span>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="5eaec-122">Разработка контрактов службы</span><span class="sxs-lookup"><span data-stu-id="5eaec-122">Designing Service Contracts</span></span>](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [<span data-ttu-id="5eaec-123">Практическое руководство. Создание дуплексного контракта</span><span class="sxs-lookup"><span data-stu-id="5eaec-123">How to: Create a Duplex Contract</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
