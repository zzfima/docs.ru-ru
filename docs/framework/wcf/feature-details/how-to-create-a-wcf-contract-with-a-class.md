---
title: Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 296f500532040aaebf0f6d7d37a7a9aae99a3451
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Практическое руководство. Создание контракта Windows Communication Foundation с помощью класса
С помощью интерфейса является предпочтительным способом создания контракта Windows Communication Foundation (WCF). Дополнительные сведения см. в разделе [как: определение контракта службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.  
  
> [!WARNING]
>  `[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое. То же верно для `[OperationContract]` и `[OperationContractAttribute]`. В каждом случае первое является сокращением для обозначения предыдущего контракта.  
  
 Дополнительные сведения о контрактах службы см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Создание контракта Windows Communication Foundation с помощью класса  
  
1.  Создайте новый класс с помощью Visual Basic, C# или любые другие языка среды CLR.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.  
  
3.  Создайте методы класса.  
  
4.  Применить <xref:System.ServiceModel.OperationContractAttribute> класса для каждого метода, который должен предоставляться как часть открытого контракта WCF.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан класс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». Дополнительные сведения об этой модели сообщений см. в разделе [как: Создание контракта типа запрос-ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в разделе [как: создать односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
