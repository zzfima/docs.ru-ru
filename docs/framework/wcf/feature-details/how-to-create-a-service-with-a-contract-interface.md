---
title: "Практическое руководство. Создание службы с помощью интерфейса контракта"
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
ms.assetid: 7b6803f6-d6f9-4cc2-9f1b-6f4c920475d5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cf3938f96674b07a7938861e217a93babd83101
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-service-with-a-contract-interface"></a>Практическое руководство. Создание службы с помощью интерфейса контракта
Контракты [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] рекомендуется создавать с помощью интерфейса. Такой контракт определяет набор и структуру сообщений, необходимых для доступа к операциям, предлагаемым службой. Этот интерфейс определяет типы входных и выходных данных путем применения класса <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу и класса <xref:System.ServiceModel.OperationContractAttribute> к методам, которые требуется предоставить.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]контракты службы см. в разделе [проектирование контрактов службы](../../../../docs/framework/wcf/designing-service-contracts.md).  
  
### <a name="creating-a-wcf-contract-with-an-interface"></a>Создание контракта WCF с интерфейсом  
  
1.  Создайте новый интерфейс с использованием языка [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], C# или другого языка среды CLR.  
  
2.  Примените класс <xref:System.ServiceModel.ServiceContractAttribute> к интерфейсу.  
  
3.  Определите методы интерфейса.  
  
4.  Примените класс <xref:System.ServiceModel.OperationContractAttribute> к каждому методу, который требуется предоставить в рамках открытого контракта [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## <a name="example"></a>Пример  
 В следующем примере кода показан интерфейс, определяющий контракт службы.  
  
 [!code-csharp[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithinterface/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithInterface#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithinterface/vb/source.vb#1)]  
  
 Методы, к которым применен класс <xref:System.ServiceModel.OperationContractAttribute>, по умолчанию используют шаблон обмена сообщениями «запрос-ответ». [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Этот шаблон, в разделе [как: Создание контракта типа запрос-ответ](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md). Кроме того, можно создать и использовать другие шаблоны сообщений путем задания свойств атрибута. Дополнительные примеры см. в разделе [как: создать односторонний контракт](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) и [как: создание дуплексного контракта](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
