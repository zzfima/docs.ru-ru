---
title: Типовые сценарии безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: 578ec2d7d5abe1285007ad22d8bacd69e695b1d3
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964283"
---
# <a name="common-security-scenarios"></a>Типовые сценарии безопасности
В подразделах этого раздела рассматривается множество возможных конфигураций безопасности клиентов и служб. Конфигурация зависит от ряда факторов: например, находится ли служба или клиент в интрасети, или чем обеспечивается безопасность - Windows или транспортом (таким как HTTPS).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Незащищенные интернет-клиент и служба](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 Пример общедоступных, незащищенных клиента и службы.  
  
 [Незащищенные интранет-клиент и служба](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 Служба Basic Windows Communication Foundation (WCF), разработанная для предоставления информации о защищенной частной сети приложению WCF.  
  
 [Безопасность транспорта с обычной проверкой подлинности](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 Приложение, позволяющее клиентам входить в систему с использованием пользовательской проверки подлинности.  
  
 [Безопасность транспорта с проверкой подлинности Windows](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Клиент и служба, защищенные механизмом безопасности Windows.  
  
 [Безопасность транспорта с анонимным клиентом](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 Сценарий с использованием механизма безопасности транспорта (такого как HTTPS) для обеспечения конфиденциальности и целостности.  
  
 [Безопасность транспорта с проверкой подлинности с использованием сертификатов](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 Клиент и служба, защищенные сертификатом.  
  
 [Безопасность сообщений с анонимным клиентом](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 Показывает клиент и службу, защищенные с помощью безопасности сообщений WCF.  
  
 [Безопасность сообщений при использовании клиентом учетных данных пользователя](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 Клиент - приложение Windows Forms, позволяющее клиентам входить в систему с использованием имени пользователя и пароля домена.  
  
 [Безопасность сообщений при использовании клиентом сертификата](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 Серверы имеют сертификаты и каждый клиент имеет сертификат. Контекст безопасности устанавливается посредством согласования по протоколу TLS.  
  
 [Безопасность сообщений с клиентом Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 Разновидность клиента с сертификатом. Серверы имеют сертификаты и каждый клиент имеет сертификат. Контекст безопасности устанавливается посредством согласования TLS.  
  
 [Безопасность сообщений с использованием клиента Windows без согласования учетных данных](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Клиент и служба, защищенные доменом Kerberos.  
  
 [Безопасность сообщений с взаимными сертификатами](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 Серверы имеют сертификаты и каждый клиент имеет сертификат. Сертификат сервера распространяется вместе с приложением и доступен внештатно.  
  
 [Безопасность сообщений с использованием выданных маркеров](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 Федеративная безопасность, позволяющая установить доверие между независимыми доменами.  
  
 [Доверенная подсистема](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 Клиент обращается к одной или нескольким веб-службам, распределенным по сети. Веб-службы обращаются к дополнительным ресурсам (таким как базы данных или другие веб-службы), которые должны быть защищены.  
  
## <a name="reference"></a>Справочные сведения  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [Security](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Привязки и безопасность](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [Проверка подлинности](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Аудит](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a>См. также:

- [Руководство и рекомендации по безопасности](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
