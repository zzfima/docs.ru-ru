---
title: "Различия проверки сертификатов службы с использованием Internet Explorer и WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "сертификаты [WCF], проверка сертификата службы"
  - "проверка сертификата службы [WCF]"
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Различия проверки сертификатов службы с использованием Internet Explorer и WCF
Ввиду различий между тем, как Internet Explorer и [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] проверяют сертификаты службы при использовании HTTPS, возможно, Internet Explorer не сможет получить доступ к странице справки или языку WSDL службы, даже несмотря на то что клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может успешно отправлять сообщения в конечные точки службы.Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы идентификаторы объекта \(OID\) `ServerAuthentication` в расширенных флагах использования, тогда как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] такое ограничение не применяет.Если Internet Explorer не может получить доступ к странице справки службы или WSDL для службы, для доступа к метаданным службы нужно использовать [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
## См. также  
 [Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)   
 [Практическое руководство. Извлечение данных и реализация совместимой службы](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)