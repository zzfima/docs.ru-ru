---
title: "Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44418d9d7ec88ea5cd340312fd1ebe42ef8d20a5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса
Контракты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] рекомендуется создавать с помощью интерфейсов. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как: определение контракта службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.  
  
> [!WARNING]
>  `[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое. То же верно для `[OperationContract]` и `[OperationContractAttribute]`. В каждом случае первое является сокращением для обозначения предыдущего контракта.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]контракты службы см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Создание контракта Windows Communication Foundation с помощью класса  
  
1.  Создайте новый класс с использованием языка [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# или другого языка среды CLR.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.  
  
3.  Создайте методы класса.  
  
4.  Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который требуется предоставить в рамках открытого контракта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан класс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Этот шаблон, в разделе [как: Создание контракта типа запрос-ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в разделе [как: создать односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
