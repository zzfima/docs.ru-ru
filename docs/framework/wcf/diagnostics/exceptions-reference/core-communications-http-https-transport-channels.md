---
title: "Основное взаимодействие: Каналы транспорта HTTP-HTTPS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c0a23c9-a663-461c-bdab-58b4d3e23642
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7d67bb810ced381749dca0dc698ca405bb59cfb0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="core-communications-httphttps-transport-channels"></a>Основное взаимодействие: транспортные каналы HTTP/HTTPS
В этом разделе перечислены все исключения, вызываемые транспортными каналами HTTP или HTTPS [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="exception-list"></a>Список исключений  
  
|Код ресурса|Строка ресурса|  
|-------------------|---------------------|  
|DigestExplicitCredsImpersonationLevel|Задан указанный уровень олицетворения. При использовании с явно указанными учетными данными дайджест-проверка подлинности HTTP поддерживает только уровень 'Олицетворение'.|  
|FramingContentTypeMismatch|Указанный тип контента не поддерживается заданной службой. Возможно несоответствие привязок клиента и службы.|  
|Hosting_SslSettingsMisconfigured|Параметры SSL заданной службы не соответствуют одноименным параметрам IIS.|  
|HttpAuthSchemeAndClientCert|Фабрика прослушивателя HTTPS настроена на запрос сертификата клиента и указанной схемы проверки подлинности. Однако единовременно можно запросить только один тип проверки подлинности.|  
|HttpReceiveFailure|При получении HTTP-ответа заданным объектом возникла ошибка. Привязка конечной точки службы, возможно, не использует протокол HTTP. Также возможно, что контекст HTTP-запроса был завершен сервером вследствие завершения работы службы. Дополнительные сведения см. в журналах сервера.|  
|HttpRegistrationAccessDenied|HTTP не удается зарегистрировать указанный URL-адрес. У используемого процесса нет прав доступа к данному пространству имен (дополнительные сведения см. в разделе http://msdn.microsoft.com/library/default.asp?url=/library/http/http/namespace_reservations_registrations_and_routing.asp).|  
|HttpRegistrationAlreadyExists|HTTP не удается зарегистрировать указанный URL-адрес. Другое приложение уже зарегистрировало данный URL-адрес в HTTP.SYS.|  
|HttpRegistrationPortInUse|HTTP не удается зарегистрировать указанный URL-адрес - указанный TCP-порт используется другим приложением.|  
|HttpSendFailure|При выполнении HTTP-запроса для заданного объекта возникла ошибка. Убедитесь, что причиной не является несоответствие привязок безопасности. Также убедитесь, что служба не настроена для SSL.|  
|MessageXmlProtocolError|Возникла ошибка сообщения XML, полученного из сети. Дополнительные сведения см. в описании внутреннего исключения.|  
|MissingContentType|Принимающий объект возвратил ошибку, указывающую, что тип контента отсутствовал в запросе к заданному объекту. Дополнительные сведения см. в описании внутреннего исключения.|  
|ProxyAuthenticationLevelMismatch|Учетные данные проверки подлинности прокси-сервера HTTP определяют требование взаимной проверки подлинности, которое строже требования проверки подлинности целевого сервера.|  
|ProxyImpersonationLevelMismatch|Учетные данные проверки подлинности прокси-сервера HTTP определяют ограничение уровня олицетворения, которое строже ограничения проверки подлинности целевого сервера.|  
|SecureChannelFailure|Не удается установить безопасный канал SSL или TLS с указанным центром.|  
|TrustFailure|Не удается установить отношение доверия для безопасного канала SSL или TLS с указанным центром.|  
|UseDefaultWebProxyCantBeUsedWithExplicitProxyAddress|В элементе HttpTransportBinding нельзя явно задать адрес прокси-сервера, а также нельзя задать для параметра UseDefaultWebProxy значение true.|
