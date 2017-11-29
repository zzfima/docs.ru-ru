---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b09d7fc476d5eed7f7c534fdde46cb18eeac30d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelchannelspeernodeauthenticationfailure"></a>System.ServiceModel.Channels.PeerNodeAuthenticationFailure
Подтверждение безопасности с потенциальным соседним узлом завершилось неуспешно.  
  
## <a name="description"></a>Описание  
 Эта трассировка возникает при попытке установить безопасное соединение с соседним узлом. Это может произойти из-за недостаточных или неправильных учетных данных.  
  
 PeerChannel распознает один тип маркеров для строгой идентификации (сертификаты X.509), что обеспечивает строгую модель удостоверения, зависящую от типа проверки подлинности и авторизации, который может быть реализован. PeerChannel также обеспечивает поддержку простых приложений посредством использования паролей. Пароли могут использоваться только для разрешения входа в сеанс; их нельзя использовать для проверки подлинности сообщений. Это связано с тем, что симметричный маркер, общий для участников одноранговой группы, сложно (и не следует) использовать для проверки подлинности источника.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 Обеспечьте, чтобы все соседние узлы имели соответствующие учетные данные безопасности.  
  
## <a name="see-also"></a>См. также  
 [Безопасность одноранговых каналов](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)  
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)
