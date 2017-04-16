---
title: "Практическое руководство. Создание службы, для которой требуются сеансы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Практическое руководство. Создание службы, для которой требуются сеансы
Сеансы создают общее состояние между двумя и более конечными точками, что обеспечивает полезные возможности, такие как обратные вызовы, безопасность по всем участкам передачи и ассоциации между клиентами и экземплярами служб. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]сеансы в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] приложений, в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a>Указание требования контракта о необходимости поддержки сеанса его привязкой  
  
1.  Создайте контракт службы как минимум с одной операцией. Пример создания контракта службы см. в разделе [Практическое руководство: определение контракта службы](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).  
  
2.  Изменить <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName> , объявляющий контракт, присвоив <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName> значение:  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> , если этот контракт выполнялся в сеансе.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> , если этот контракт может выполняться в рамках сеанса.  
  
    -   <xref:System.ServiceModel.SessionMode?displayProperty=fullName> , если этот контракт не должен выполняться в рамках сеанса.  
  
3.  Настройте конечную точку службы так, чтобы она использовала привязку, поддерживающую сеансы. В следующем примере показано использование <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName>, который поддерживает WS`-`ReliableMessaging сеанса.  
  
     [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]
     [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
     [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  
  
## <a name="example"></a>Пример  
 В следующем примере кода демонстрируется указание требования сеанса на уровне контракта и использовать файл конфигурации для поддержки этого требования с <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=fullName> привязки.  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)]
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]  
  
 [!code[SCA.Session#2](../../../../samples/snippets/common/VS_Snippets_CFX/sca.session/common/hostapplication.exe.config#2)]
 [!code-csharp[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]
 [!code-vb[SCA.Session#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/hostapplication.exe.config#2)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=fullName>   
 <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=fullName>   
 <xref:System.ServiceModel.SessionMode?displayProperty=fullName>