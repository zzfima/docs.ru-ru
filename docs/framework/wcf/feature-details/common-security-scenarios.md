---
title: "Типовые сценарии безопасности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9428c5d7c8c6cf0f571b05a8b9c33b96d073d7a5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="common-security-scenarios"></a>Типовые сценарии безопасности
В подразделах этого раздела рассматривается множество возможных конфигураций безопасности клиентов и служб. Конфигурация зависит от ряда факторов: например, находится ли служба или клиент в интрасети, или чем обеспечивается безопасность - Windows или транспортом (таким как HTTPS).  
  
## <a name="in-this-section"></a>Содержание  
 [Незащищенные Интернет-клиент и служба](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 Пример общедоступных, незащищенных клиента и службы.  
  
 [Незащищенные интранет-клиент и служба](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 Простая служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], предназначенная для предоставления информации о защищенной частной сети приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Безопасность транспорта с обычной проверкой подлинности](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 Приложение, позволяющее клиентам входить в систему с использованием пользовательской проверки подлинности.  
  
 [Безопасность транспорта с проверкой подлинности Windows](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Клиент и служба, защищенные механизмом безопасности Windows.  
  
 [Безопасность транспорта с анонимным клиентом](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 Сценарий с использованием механизма безопасности транспорта (такого как HTTPS) для обеспечения конфиденциальности и целостности.  
  
 [Безопасность транспорта с проверкой подлинности сертификата](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 Клиент и служба, защищенные сертификатом.  
  
 [Безопасность сообщений с анонимным клиентом](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 Клиент и служба, защищенные механизмом безопасности сообщения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Безопасность сообщений с клиентом имя пользователя](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 Клиент - приложение Windows Forms, позволяющее клиентам входить в систему с использованием имени пользователя и пароля домена.  
  
 [Безопасность сообщений с клиентом сертификата](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 Серверы имеют сертификаты и каждый клиент имеет сертификат. Контекст безопасности устанавливается посредством согласования по протоколу TLS.  
  
 [Безопасность сообщений с клиентом Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 Разновидность клиента с сертификатом. Серверы имеют сертификаты и каждый клиент имеет сертификат. Контекст безопасности устанавливается посредством согласования TLS.  
  
 [Безопасность сообщений с клиентом Windows без согласования учетных данных](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Клиент и служба, защищенные доменом Kerberos.  
  
 [Безопасность сообщений с использованием взаимных сертификатов](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 Серверы имеют сертификаты и каждый клиент имеет сертификат. Сертификат сервера распространяется вместе с приложением и доступен внештатно.  
  
 [Безопасность сообщений с использованием выданных маркеров](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 Федеративная безопасность, позволяющая установить доверие между независимыми доменами.  
  
 [Доверенная подсистема](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 Клиент обращается к одной или нескольким веб-службам, распределенным по сети. Веб-службы обращаются к дополнительным ресурсам (таким как базы данных или другие веб-службы), которые должны быть защищены.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Защита служб и клиентов](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [Проверка подлинности](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a>См. также  
 [Рекомендации по обеспечению безопасности и рекомендации](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
