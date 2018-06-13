---
title: Аутентификация в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: a4f9b719024db1334b599f0f02fe01bc083bf3c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489115"
---
# <a name="authentication-in-wcf"></a>Аутентификация в WCF
В следующих разделах содержатся несколько различных механизмов Windows Communication Foundation (WCF), проверки подлинности, например, проверку подлинности Windows, сертификаты X.509, имя пользователя и пароли.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации. В этом разделе объясняется, как службы WCF можно использовать ту же базу данных для проверки подлинности и авторизации пользователей.  
  
 [Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.  
  
 [Идентификация и проверка подлинности службы](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 В качестве дополнительного средства защиты, клиент может проверить подлинность службы, задавая ожидаемое *удостоверение* службы. Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.  
  
 [Согласование безопасности и время ожидания](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.  
  
 [Отладка ошибок проверки подлинности Windows](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Модель безопасности для Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
