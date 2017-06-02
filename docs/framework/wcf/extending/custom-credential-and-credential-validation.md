---
title: "Пользовательские учетные данные и проверка учетных данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "проверка учетных данных [WCF]"
  - "учетные данные [WCF]"
  - "учетные данные [WCF], пользовательский"
  - "учетные данные [WCF], проверка"
  - "пользовательские учетные данные [WCF]"
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Пользовательские учетные данные и проверка учетных данных
В основе обеспечения безопасности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] лежит обмен учетными данными между службами и клиентами.  Большинство сценариев обеспечения безопасности можно реализовать с использованием стандартных типов учетных данных, например Windows \(Kerberos\), имен пользователей и паролей, а также сертификатов.  Если требуются учетные данные новых типов, в приведенных ниже разделах можно найти сведения о том, как обрабатывать и проверять эти типы.  
  
## В этом подразделе  
 [Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Настройка проверки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] путем наследования от класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
 [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Пример расширения классов <xref:System.ServiceModel.Description.ClientCredentials> и <xref:System.ServiceModel.Description.ServiceCredentials> для работы с новыми типами учетных данных.  Это первый раздел в серии, посвященной созданию пользовательских типов учетных данных.  
  
 [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Создание поставщика маркеров безопасности для обработки новых типов учетных данных и возврата новых маркеров для учетных данных.  Это второй раздел в данной серии.  
  
 [Как создавать пользовательскую структуру проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Создание пользовательских структур проверки подлинности для проверки подлинности учетных данных новых типов.  Это третий раздел в данной серии.  
  
## Ссылка  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## Связанные подразделы  
 [Аутентификация](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Федерация и выданные маркеры](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Авторизация](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## См. также  
 [Безопасность](../../../../docs/framework/wcf/feature-details/security.md)