---
title: "Различия проверки сертификатов службы с использованием Internet Explorer и WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b74886f05ca6dc38c724e02cd091c6dd212c554f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Различия проверки сертификатов службы с использованием Internet Explorer и WCF
Ввиду различий между тем, как Internet Explorer и [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] проверяют сертификаты службы при использовании HTTPS, возможно, Internet Explorer не сможет получить доступ к странице справки или языку WSDL службы, даже несмотря на то что клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может успешно отправлять сообщения в конечные точки службы. Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы идентификаторы объекта (OID) `ServerAuthentication` в расширенных флагах использования, тогда как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] такое ограничение не применяет. Если Internet Explorer не удается получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.  
  
## <a name="see-also"></a>См. также  
 [Различия проверки сертификатов HTTPS, SSL по TCP или безопасности SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Как: извлечение данных и реализация совместимой службы](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
