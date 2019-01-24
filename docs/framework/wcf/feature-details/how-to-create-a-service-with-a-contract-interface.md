---
title: Как выполнить Создание службы с помощью интерфейса контракта
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
ms.openlocfilehash: cd0ae76040f235b4573a90764566205a2d5d81e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536728"
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Как выполнить Создание службы с помощью интерфейса контракта
С помощью интерфейса является предпочтительным способом создания контракта Windows Communication Foundation (WCF). Такой контракт определяет набор и структуру сообщений, необходимых для доступа к операциям, предлагаемым службой. Этот интерфейс определяет типы входных и выходных данных путем применения класса <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу и класса <xref:System.ServiceModel.OperationContractAttribute> к методам, которые требуется предоставить.  
  
 Дополнительные сведения о контрактах службы см. в разделе [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Создание контракта WCF с интерфейсом  
  
1.  Создать новый интерфейс с помощью Visual Basic, C#, или любые другие языка среды CLR.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.  
  
3.  Определите методы интерфейса.  
  
4.  Применить <xref:System.ServiceModel.OperationContractAttribute> класса к каждому методу, который должен предоставляться как часть общедоступного контракта WCF.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан интерфейс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». Дополнительные сведения об этой модели сообщений см. в разделе [как: Создание контракта типа запрос ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в статье [Практическое руководство. Создание одностороннего контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: Создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
