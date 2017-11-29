---
title: "Пользовательские учетные данные и проверка учетных данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3ca7726f3a6a0c5faaab1cbbd0b31125ce0c1d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="custom-credential-and-credential-validation"></a>Пользовательские учетные данные и проверка учетных данных
В основе обеспечения безопасности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] лежит обмен учетными данными между службами и клиентами. Большинство сценариев обеспечения безопасности можно реализовать с использованием стандартных типов учетных данных, например Windows (Kerberos), имен пользователей и паролей, а также сертификатов. Если требуются учетные данные новых типов, в приведенных ниже разделах можно найти сведения о том, как обрабатывать и проверять эти типы.  
  
## <a name="in-this-section"></a>Содержание  
 [Как: создание службы, использующей пользовательский сертификат проверяющий элемент управления](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Настройка проверки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] путем наследования от класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
 [Пошаговое руководство: Создание пользовательского клиента и учетные данные службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Демонстрирует расширение <xref:System.ServiceModel.Description.ClientCredentials> и <xref:System.ServiceModel.Description.ServiceCredentials> классы для работы с новыми типами учетных данных. Это первый раздел в серии, посвященной созданию пользовательских типов учетных данных.  
  
 [Как: Создание поставщика пользовательских маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Создание поставщика маркеров безопасности для обработки новых типов учетных данных и возврата новых маркеров для учетных данных. Это второй раздел в данной серии.  
  
 [Как: создать средство проверки подлинности маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
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
 [Проверка подлинности](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a>См. также  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)
