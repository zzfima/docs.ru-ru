---
title: "System.ServiceModel.Channels.PeerNodeAuthenticationFailure | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b50f782-ca06-4a82-aa7f-71f78ddc5177
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# System.ServiceModel.Channels.PeerNodeAuthenticationFailure
Подтверждение безопасности с потенциальным соседним узлом завершилось неуспешно.  
  
## Описание  
 Эта трассировка возникает при попытке установить безопасное соединение с соседним узлом.Это может произойти из\-за недостаточных или неправильных учетных данных.  
  
 PeerChannel распознает один тип маркеров для строгой идентификации \(сертификаты X.509\), что обеспечивает строгую модель удостоверения, зависящую от типа проверки подлинности и авторизации, который может быть реализован.PeerChannel также обеспечивает поддержку простых приложений посредством использования паролей.Пароли могут использоваться только для разрешения входа в сеанс; их нельзя использовать для проверки подлинности сообщений.Это связано с тем, что симметричный маркер, общий для участников одноранговой группы, сложно \(и не следует\) использовать для проверки подлинности источника.  
  
## Устранение неполадок  
 Обеспечьте, чтобы все соседние узлы имели соответствующие учетные данные безопасности.  
  
## См. также  
 [Безопасность одноранговых каналов](../../../../../docs/framework/wcf/feature-details/peer-channel-security.md)   
 [Трассировка](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Использование трассировки для устранения неполадок приложения](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)   
 [Администрирование и диагностика](../../../../../docs/framework/wcf/diagnostics/index.md)