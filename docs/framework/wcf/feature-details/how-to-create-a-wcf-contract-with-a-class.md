---
title: Как выполнить Создание контракта Windows Communication Foundation с помощью класса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: b32d4feb03daac33af8b7ca3b533a0b7013bb090
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658930"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Как выполнить Создание контракта Windows Communication Foundation с помощью класса
С помощью интерфейса является предпочтительным способом Создание контракта Windows Communication Foundation (WCF). Дополнительные сведения см. в разделе [Как Определите контракт службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md). Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.  
  
> [!WARNING]
>  `[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое. То же самое справедливо для `[OperationContract]` и `[OperationContractAttribute]`. В каждом случае первое является сокращением для второго.  
  
 Дополнительные сведения о контрактах службы см. в разделе [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Создание контракта Windows Communication Foundation с помощью класса  
  
1.  Создайте новый класс с помощью Visual Basic, C#, или любые другие языка среды CLR.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.  
  
3.  Создайте методы класса.  
  
4.  Применить <xref:System.ServiceModel.OperationContractAttribute> класса к каждому методу, который должен предоставляться как часть общедоступного контракта WCF.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан класс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». Дополнительные сведения об этой модели сообщений см. в разделе [как: Создание контракта типа запрос ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в статье [Практическое руководство. Создание одностороннего контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
