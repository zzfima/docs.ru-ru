---
title: Расширение безопасности
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 95dacf3ef975be1ddd56db747936cca35db50625
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099642"
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
  
 [Практическое руководство. Создание пользовательского средства проверки идентификации клиентов](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
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
  
 [Базовое программирование WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a>См. также

- [Общие сведения о безопасности](../../../../docs/framework/wcf/feature-details/security-overview.md)
