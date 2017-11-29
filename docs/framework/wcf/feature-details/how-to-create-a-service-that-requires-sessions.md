---
title: "Практическое руководство. Создание службы, для которой требуются сеансы"
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
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2e238598ccd33d9e6e77a2d09ea3b19fdefcefbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-service-that-requires-sessions"></a>Практическое руководство. Создание службы, для которой требуются сеансы
Сеансы создают общее состояние между двумя и более конечными точками, что обеспечивает полезные возможности, такие как обратные вызовы, безопасность по всем участкам передачи и ассоциации между клиентами и экземплярами служб. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]сеансы в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] приложения, см. [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>Указание требования контракта о необходимости поддержки сеанса его привязкой  
  
1.  Создайте контракт службы как минимум с одной операцией. Пример того, как создать контракт службы см. в разделе [как: определение контракта службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Измените элемент <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>, объявляющий контракт, присвоив свойству <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> одно из следующих значений:  
  
    -   <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>, если требуется, чтобы этот контракт выполнялся в сеансе.  
  
    -   <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType>, если этот контракт может выполняться в сеансе.  
  
    -   <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType>, если требуется, чтобы этот контракт не выполнялся в сеансе.  
  
3.  Настройте конечную точку службы так, чтобы она использовала привязку, поддерживающую сеансы. В следующем примере конфигурации показано использование привязки <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, поддерживающей сеанс WS`-`ReliableMessaging.  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется указание требования сеанса на уровне контракта и использование файла конфигурации для поддержки этого требования с помощью привязки <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>  
 <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
