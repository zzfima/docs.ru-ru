---
title: "Безопасные сеансы"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b50602f-d7b5-42e9-8e92-1f0413df0d8b
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 724ea72c52296c448ead80a8f357235d625f5842
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="secure-sessions"></a>Безопасные сеансы
Безопасные сеансы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] обеспечивают получение сообщений в порядке их отправки. В этом разделе рассматриваются проблемы безопасности, которые необходимо учитывать при создании надежного сеанса. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]надежные сеансы, в разделе [с использованием сеансов](../../../../docs/framework/wcf/using-sessions.md).  
  
> [!NOTE]
>  Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера контекста безопасности с отслеживанием состояния (SCT). При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Неподдерживаемые сценарии](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).  
  
## <a name="in-this-section"></a>Содержание  
  
|||  
|-|-|  
|[Безопасные диалоги и безопасные сеансы](../../../../docs/framework/wcf/feature-details/secure-conversations-and-secure-sessions.md)|Безопасные диалоги и безопасные сеансы - это синонимы. В этом разделе рассматривается, как работает безопасный диалог, а также когда и почему следует использовать шаблон.|  
|[Как: Создание безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-secure-session.md)|Пошаговое руководство по основным этапам создания безопасного сеанса.|  
|[Как: создать контекст безопасности маркера для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)|Пошаговое руководство по созданию веб-фермы, которая будет поддерживать состояние и сеансы с клиентами.|  
|[Рекомендации по безопасности для безопасных сеансов](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)|Описание некоторых особенностей безопасных сеансов.|  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Сеансы, экземпляры и параллелизм](../../../../docs/framework/wcf/feature-details/sessions-instancing-and-concurrency.md)  
  
 [Проектирование и реализация служб](../../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
## <a name="see-also"></a>См. также  
 [Как: Включение обнаружения повтора сообщений](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 [Атаки с повторением пакетов](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 [Как: создать службу, которой требуются сеансы](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
