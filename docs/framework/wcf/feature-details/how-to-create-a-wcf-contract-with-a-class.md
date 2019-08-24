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
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>Практическое руководство. Создание Windows Communication Foundation контракта с помощью класса
Предпочтительный способ создания контракта Windows Communication Foundation (WCF) — использование интерфейса. Дополнительные сведения см. в разделе [Практическое руководство. Определите контракт](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)службы. Описанный здесь альтернативный способ предполагает создание класса и последующее применение атрибута <xref:System.ServiceModel.ServiceContractAttribute> непосредственно к классу, а атрибута <xref:System.ServiceModel.OperationContractAttribute> к каждому из методов класса, являющихся частью контракта.  
  
> [!WARNING]
> `[ServiceContract]` и `[ServiceContractAttribute]` выполняют то же самое. То же самое касается `[OperationContract]` и. `[OperationContractAttribute]` В каждом случае первый из них является сокращением для второго.  
  
 Дополнительные сведения о контрактах служб см. в разделе [Разработка контрактов служб](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>Создание контракта Windows Communication Foundation с помощью класса  
  
1. Создайте новый класс, используя Visual Basic, C#или любой другой язык среды CLR.  
  
2. Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к созданному классу.  
  
3. Создайте методы класса.  
  
4. Примените <xref:System.ServiceModel.OperationContractAttribute> класс к каждому методу, который должен быть предоставлен как часть общедоступного контракта WCF.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан класс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». Дополнительные сведения об этом шаблоне сообщений см. [в разделе как Создайте контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)«запрос-ответ». Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в статье [Практическое руководство. Создайте односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [поочередно: Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
