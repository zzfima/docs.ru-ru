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
ms.workload: dotnet
ms.openlocfilehash: 12e30d9df9d6bb0a9f8776099951e4354d302ebf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Различия проверки сертификатов службы с использованием Internet Explorer и WCF
Ввиду различий между тем, как Internet Explorer и [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] проверяют сертификаты службы при использовании HTTPS, возможно, Internet Explorer не сможет получить доступ к странице справки или языку WSDL службы, даже несмотря на то что клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может успешно отправлять сообщения в конечные точки службы. Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы идентификаторы объекта (OID) `ServerAuthentication` в расширенных флагах использования, тогда как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] такое ограничение не применяет. Если Internet Explorer не удается получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.  
  
## <a name="see-also"></a>См. также  
 [Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Практическое руководство. Извлечение данных и реализация совместимой службы](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
