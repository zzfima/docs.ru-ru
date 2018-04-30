---
title: Практическое руководство. Создание службы с помощью интерфейса контракта
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
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b4af593edd355ed89da8c5b2c79a4c029b966fe4
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a><span data-ttu-id="241f5-102">Практическое руководство. Создание службы с помощью интерфейса контракта</span><span class="sxs-lookup"><span data-stu-id="241f5-102">How to: Create a Service with a Contract Interface</span></span>
<span data-ttu-id="241f5-103">Контракты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] рекомендуется создавать с помощью интерфейса.</span><span class="sxs-lookup"><span data-stu-id="241f5-103">The preferred way to create a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] contract is by using an interface.</span></span> <span data-ttu-id="241f5-104">Такой контракт определяет набор и структуру сообщений, необходимых для доступа к операциям, предлагаемым службой.</span><span class="sxs-lookup"><span data-stu-id="241f5-104">This contract specifies the collection and structure of messages required to access the operations the service offers.</span></span> <span data-ttu-id="241f5-105">Этот интерфейс определяет типы входных и выходных данных путем применения класса <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу и класса <xref:System.ServiceModel.OperationContractAttribute> к методам, которые требуется предоставить.</span><span class="sxs-lookup"><span data-stu-id="241f5-105">This interface defines the input and output types by applying the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface and the <xref:System.ServiceModel.OperationContractAttribute> class to the methods that you want to expose.</span></span>  
  
 <span data-ttu-id="241f5-106">Дополнительные сведения о контрактах службы см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="241f5-106">For more information about service contracts, see [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).</span></span>  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a><span data-ttu-id="241f5-107">Создание контракта WCF с интерфейсом</span><span class="sxs-lookup"><span data-stu-id="241f5-107">Creating a WCF contract with an interface</span></span>  
  
1.  <span data-ttu-id="241f5-108">Создайте новый интерфейс с помощью Visual Basic, C# или любые другие языка среды CLR.</span><span class="sxs-lookup"><span data-stu-id="241f5-108">Create a new interface using Visual Basic, C#, or any other common language runtime language.</span></span>  
  
2.  <span data-ttu-id="241f5-109">Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.</span><span class="sxs-lookup"><span data-stu-id="241f5-109">Apply the <xref:System.ServiceModel.ServiceContractAttribute> class to the interface.</span></span>  
  
3.  <span data-ttu-id="241f5-110">Определите методы интерфейса.</span><span class="sxs-lookup"><span data-stu-id="241f5-110">Define the methods in the interface.</span></span>  
  
4.  <span data-ttu-id="241f5-111">Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который требуется предоставить в рамках открытого контракта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="241f5-111">Apply the <xref:System.ServiceModel.OperationContractAttribute> class to each method that must be exposed as part of the public [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] contract.</span></span>  
  
## <a name="example"></a><span data-ttu-id="241f5-112">Пример</span><span class="sxs-lookup"><span data-stu-id="241f5-112">Example</span></span>  
 <span data-ttu-id="241f5-113">В следующем примере кода показан интерфейс, определяющий контракт службы.</span><span class="sxs-lookup"><span data-stu-id="241f5-113">The following code example shows an interface that defines a service contract.</span></span>  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 <span data-ttu-id="241f5-114">Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ».</span><span class="sxs-lookup"><span data-stu-id="241f5-114">The methods that have the <xref:System.ServiceModel.OperationContractAttribute> class applied use a request-reply message pattern by default.</span></span> <span data-ttu-id="241f5-115">Дополнительные сведения об этой модели сообщений см. в разделе [как: Создание контракта типа запрос-ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span><span class="sxs-lookup"><span data-stu-id="241f5-115">For more information about this message pattern, see [How to: Create a Request-Reply Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md).</span></span> <span data-ttu-id="241f5-116">Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута.</span><span class="sxs-lookup"><span data-stu-id="241f5-116">You can also create and use other message patterns by setting properties of the attribute.</span></span> <span data-ttu-id="241f5-117">Дополнительные примеры см. в разделе [как: создать односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span><span class="sxs-lookup"><span data-stu-id="241f5-117">For more examples, see [How to: Create a One-Way Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) and [How to: Create a Duplex Contract](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="241f5-118">См. также</span><span class="sxs-lookup"><span data-stu-id="241f5-118">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
