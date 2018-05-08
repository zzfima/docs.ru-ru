---
title: System.ServiceModel.Channels.PeerNodeAuthenticationFailure
ms.date: 03/30/2017
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
ms.openlocfilehash: 633f497950ab14d7715537eed8f5cc80e7a350a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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
