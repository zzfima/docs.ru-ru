---
title: Безопасные сеансы
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 068615510d7e1d73ae260441ccef6536ee6ff317
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="secure-sessions"></a>Безопасные сеансы
Безопасные сеансы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] обеспечивают получение сообщений в порядке их отправки. В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса. Дополнительные сведения о надежных сеансов см. в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния (SCT). При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>. Дополнительные сведения см. в разделе [неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>В этом разделе  
  
|||  
|-|-|  
|[Безопасные диалоги и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Безопасные диалоги и безопасные сеансы - это синонимы. В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.|  
|[Практическое руководство. Создание сеанса безопасности](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Пошаговое руководство по основным этапам создания безопасного сеанса.|  
|[Практическое руководство. Создание маркера контекста безопасности с отслеживанием состояния для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Пошаговое руководство по созданию веб-фермы, которая будет поддерживать состояние и сеансы с клиентами.|  
|[Соображения о защите безопасных сеансов](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Описание некоторых особенностей безопасных сеансов.|  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство. Включение обнаружения повтора сообщений](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [Атаки с повторением](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [Практическое руководство. Создание службы, для которой требуются сеансы](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
