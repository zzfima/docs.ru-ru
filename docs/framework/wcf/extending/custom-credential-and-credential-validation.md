---
title: Пользовательские учетные данные и проверка учетных данных
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 1418d4155bc7f2fefc9f3e6caf4d3a264747a667
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795818"
---
# <a name="custom-credential-and-credential-validation"></a>Пользовательские учетные данные и проверка учетных данных
Безопасность в Windows Communication Foundation (WCF) основана на обмене учетными данными между службами и клиентами. Большинство сценариев обеспечения безопасности можно реализовать с использованием стандартных типов учетных данных, например Windows (Kerberos), имен пользователей и паролей, а также сертификатов. Если требуются учетные данные новых типов, в приведенных ниже разделах можно найти сведения о том, как обрабатывать и проверять эти типы.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Объясняется, как настроить проверку WCF путем наследования от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.  
  
 [Пошаговое руководство: Создание настраиваемых учетных данных клиента и службы](walkthrough-creating-custom-client-and-service-credentials.md)  
 Демонстрирует, как расширить <xref:System.ServiceModel.Description.ClientCredentials> классы и <xref:System.ServiceModel.Description.ServiceCredentials> для размещения новых типов учетных данных. Это первый раздел в серии, посвященной созданию пользовательских типов учетных данных.  
  
 [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](how-to-create-a-custom-security-token-provider.md)  
 Создание поставщика маркеров безопасности для обработки новых типов учетных данных и возврата новых маркеров для учетных данных. Это второй раздел в данной серии.  
  
 [Практическое руководство. Создание настраиваемого средства проверки подлинности маркеров безопасности](how-to-create-a-custom-security-token-authenticator.md)  
 Создание пользовательских структур проверки подлинности для проверки подлинности учетных данных новых типов. Это третий раздел в данной серии.  
  
## <a name="reference"></a>Ссылка  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a>Связанные разделы  
 [Authentication](../feature-details/authentication-in-wcf.md)  
  
 [Федерация и выданные маркеры](../feature-details/federation-and-issued-tokens.md)  
  
 [Авторизация](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>См. также

- [Безопасность](../feature-details/security.md)
