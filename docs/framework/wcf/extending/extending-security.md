---
title: Расширение безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 698d65d951ed7adad5aa32e874befb15a3b24d12
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2019
ms.locfileid: "56261431"
---
# <a name="extending-security"></a>Расширение безопасности
Чтобы адаптировать новые типы утверждений и пользовательские маркеры, можно расширить инфраструктуру безопасности Windows Communication Foundation (WCF). Это подробно описывается в следующих подразделах.  
  
## <a name="in-this-section"></a>В этом разделе  
  
 [Пользовательские учетные данные и проверка учетных данных](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 Рассматривается, как модель удостоверения используется при проверке пользовательских учетных данных.  
  
 [Пользовательские маркеры](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 Маркеры, выдаваемые службой маркеров безопасности (STS), - обычно маркеры SAML. В этом разделе описывается, как создать тип пользовательского маркера.  
  
 [Пользовательская авторизация](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 Объясняется, как реализовать пользовательскую авторизацию.  
  
 [Переопределение идентификатора службы для проверки подлинности](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 Описывается, как переопределить идентификацию службы для проверки подлинности.  
  
 [Практическое руководство. Создание средства проверки идентификации настраиваемого клиента](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 Демонстрирует, как проверить идентификацию пользовательской конечной точки.  
  
 [Практическое руководство. Использование отдельных сертификатов X.509 для подписывания и шифрования](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Обычно сообщения подписываются и шифруются одним сертификатом. В этом разделе объясняется, как при необходимости использовать два сертификата.  
  
 [Практическое руководство. Изменение поставщика служб шифрования для закрытого ключа сертификата X.509](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 Объясняет, как изменить поставщика служб шифрования, используемый для предоставления закрытый ключ сертификата X.509 и как интегрировать поставщика в платформу Windows Communication Foundation (WCF).  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Базовое программирование для WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a>См. также
- [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
