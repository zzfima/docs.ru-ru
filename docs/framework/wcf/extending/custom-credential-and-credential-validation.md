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
ms.openlocfilehash: 3b1ff700010f471a4d9be117f363083b6cbed493
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696448"
---
# <a name="custom-credential-and-credential-validation"></a>Пользовательские учетные данные и проверка учетных данных
Безопасность в Windows Communication Foundation (WCF) основана на обменом учетными данными между службами и клиентами. Большинство сценариев обеспечения безопасности можно реализовать с использованием стандартных типов учетных данных, например Windows (Kerberos), имен пользователей и паролей, а также сертификатов. Если требуются учетные данные новых типов, в приведенных ниже разделах можно найти сведения о том, как обрабатывать и проверять эти типы.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Практическое руководство. Создание службы, использующей пользовательское средство проверки сертификатов](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Объясняется, как настроить проверку WCF путем наследования от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.  
  
 [Пошаговое руководство: Создание пользовательских клиента и учетные данные службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Демонстрирует расширение <xref:System.ServiceModel.Description.ClientCredentials> и <xref:System.ServiceModel.Description.ServiceCredentials> классы для работы с новыми типы учетных данных. Это первый раздел в серии, посвященной созданию пользовательских типов учетных данных.  
  
 [Практическое руководство. Создание поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Создание поставщика маркеров безопасности для обработки новых типов учетных данных и возврата новых маркеров для учетных данных. Это второй раздел в данной серии.  
  
 [Практическое руководство. Создать структуру проверки подлинности маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
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
 [Authentication](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>См. также

- [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)
