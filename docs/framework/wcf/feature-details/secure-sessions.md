---
title: "Безопасные сеансы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: 14
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 14
---
# Безопасные сеансы
Безопасные сеансы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] обеспечивают получение сообщений в порядке их отправки.В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] надежных сеансах см. в разделе [Использование сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния \(SCT\).При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## В этом подразделе  
  
|||  
|-|-|  
|[Безопасные диалоги и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Безопасные диалоги и безопасные сеансы — это синонимы.В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.|  
|[Практическое руководство. Создание сеанса безопасности](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Пошаговое руководство по основным этапам создания безопасного сеанса.|  
|[Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Пошаговое руководство по созданию веб\-фермы, которая будет поддерживать состояние и сеансы с клиентами.|  
|[Соображения о защите безопасных сеансов](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Описание некоторых особенностей безопасных сеансов.|  
  
## Ссылка  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## Связанные подразделы  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## См. также  
 [Как включить обнаружение повтора сообщений](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)   
 [Атаки с повторением](../../../../docs/framework/wcf/feature-details/replay-attacks.md)   
 [Как создать службу, для которой требуются сеансы](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)