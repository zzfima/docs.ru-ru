---
title: Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 54d5e1328482fc7d0c1ee33918ffae6bf7195db9
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="138f1-102">Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса</span><span class="sxs-lookup"><span data-stu-id="138f1-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="138f1-103">Контракты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] рекомендуется создавать с помощью интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="138f1-103">The preferred way of creating a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="138f1-104">Дополнительные сведения см. в разделе [как: определение контракта службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="138f1-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="138f1-105">Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.</span><span class="sxs-lookup"><span data-stu-id="138f1-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="138f1-106">`[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое.</span><span class="sxs-lookup"><span data-stu-id="138f1-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="138f1-107">То же верно для `[OperationContract]` и `[OperationContractAttribute]`.</span><span class="sxs-lookup"><span data-stu-id="138f1-107">The same thing it true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="138f1-108">В каждом случае первое является сокращением для обозначения предыдущего контракта.</span><span class="sxs-lookup"><span data-stu-id="138f1-108">In each case the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="138f1-109">Дополнительные сведения о контрактах службы см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="138f1-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="138f1-110">Создание контракта Windows Communication Foundation с помощью класса</span><span class="sxs-lookup"><span data-stu-id="138f1-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1.  <span data-ttu-id="138f1-111">Создайте новый класс с помощью Visual Basic, C# или любые другие языка среды CLR.</span><span class="sxs-lookup"><span data-stu-id="138f1-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="138f1-112">Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.</span><span class="sxs-lookup"><span data-stu-id="138f1-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3.  <span data-ttu-id="138f1-113">Создайте методы класса.</span><span class="sxs-lookup"><span data-stu-id="138f1-113">Create methods in the class.</span></span>  
  
4.  <span data-ttu-id="138f1-114">Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который требуется предоставить в рамках открытого контракта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="138f1-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="138f1-115">Пример</span><span class="sxs-lookup"><span data-stu-id="138f1-115">Example</span></span>  
 <span data-ttu-id="138f1-116">В следующем примере кода показан класс, определяющий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="138f1-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="138f1-117">Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="138f1-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="138f1-118">Дополнительные сведения об этой модели сообщений см. в разделе [как: Создание контракта типа запрос-ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="138f1-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="138f1-119">Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута.</span><span class="sxs-lookup"><span data-stu-id="138f1-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="138f1-120">Дополнительные примеры см. в разделе [как: создать односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="138f1-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="138f1-121">См. также</span><span class="sxs-lookup"><span data-stu-id="138f1-121">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
