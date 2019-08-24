---
title: Практическое руководство. Создание Windows Communication Foundation контракта с помощью класса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 2cd757107d9f62ce749d98db1d4968c02a09c5d2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988744"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="489d9-102">Практическое руководство. Создание Windows Communication Foundation контракта с помощью класса</span><span class="sxs-lookup"><span data-stu-id="489d9-102">How to: Create a Windows Communication Foundation Contract with a Class</span></span>
<span data-ttu-id="489d9-103">Предпочтительный способ создания контракта Windows Communication Foundation (WCF) — использование интерфейса.</span><span class="sxs-lookup"><span data-stu-id="489d9-103">The preferred way of creating a Windows Communication Foundation (WCF) contract is by using an interface.</span></span> <span data-ttu-id="489d9-104">Дополнительные сведения см. в разделе [Практическое руководство. Определите контракт](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)службы.</span><span class="sxs-lookup"><span data-stu-id="489d9-104">For more information, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span> <span data-ttu-id="489d9-105">Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.</span><span class="sxs-lookup"><span data-stu-id="489d9-105">An alternative, outlined here, is to create a class and then apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute to the class directly and the <xref:System.ServiceModel.OperationContractAttribute> attribute to each of the methods in the class that are part of the contract.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="489d9-106">`[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое.</span><span class="sxs-lookup"><span data-stu-id="489d9-106">`[ServiceContract]` and `[ServiceContractAttribute]` do the same thing.</span></span> <span data-ttu-id="489d9-107">То же самое касается `[OperationContract]` и. `[OperationContractAttribute]`</span><span class="sxs-lookup"><span data-stu-id="489d9-107">The same thing is true for `[OperationContract]` and `[OperationContractAttribute]`.</span></span> <span data-ttu-id="489d9-108">В каждом случае первый из них является сокращением для второго.</span><span class="sxs-lookup"><span data-stu-id="489d9-108">In each case, the former is shorthand for the latter.</span></span>  
  
 <span data-ttu-id="489d9-109">Дополнительные сведения о контрактах служб см. в разделе [Разработка контрактов служб](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="489d9-109">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a><span data-ttu-id="489d9-110">Создание контракта Windows Communication Foundation с помощью класса</span><span class="sxs-lookup"><span data-stu-id="489d9-110">Creating a Windows Communication Foundation contract with a class</span></span>  
  
1. <span data-ttu-id="489d9-111">Создайте новый класс, используя Visual Basic, C#или любой другой язык среды CLR.</span><span class="sxs-lookup"><span data-stu-id="489d9-111">Create a new class using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2. <span data-ttu-id="489d9-112">Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.</span><span class="sxs-lookup"><span data-stu-id="489d9-112">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the class.</span></span>  
  
3. <span data-ttu-id="489d9-113">Создайте методы класса.</span><span class="sxs-lookup"><span data-stu-id="489d9-113">Create methods in the class.</span></span>  
  
4. <span data-ttu-id="489d9-114">Примените <xref:System.ServiceModel.OperationContractAttribute> класс к каждому методу, который должен быть предоставлен как часть общедоступного контракта WCF.</span><span class="sxs-lookup"><span data-stu-id="489d9-114">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public WCF contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="489d9-115">Пример</span><span class="sxs-lookup"><span data-stu-id="489d9-115">Example</span></span>  
 <span data-ttu-id="489d9-116">В следующем примере кода показан класс, определяющий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="489d9-116">The following code example shows a class that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <span data-ttu-id="489d9-117">Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="489d9-117">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="489d9-118">Дополнительные сведения об этом шаблоне сообщений см. [в разделе как Создайте контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)«запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="489d9-118">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="489d9-119">Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута.</span><span class="sxs-lookup"><span data-stu-id="489d9-119">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="489d9-120">Дополнительные примеры см. в статье [Практическое руководство. Создайте односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [поочередно: Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="489d9-120">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="489d9-121">См. также</span><span class="sxs-lookup"><span data-stu-id="489d9-121">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
