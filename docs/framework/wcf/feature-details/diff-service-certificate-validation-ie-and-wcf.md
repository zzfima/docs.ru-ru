---
title: Различия проверки сертификатов службы с использованием Internet Explorer и WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: ecc2b16eae5428e305f5f6096d6d7994256d86c2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488690"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Различия проверки сертификатов службы с использованием Internet Explorer и WCF
Из-за различия между тем, как Internet Explorer и Windows Communication Foundation (WCF) проверяют сертификаты службы при использовании HTTPS возможно, Internet Explorer не сможет получить доступ к странице справки или языка описания веб-служб (WSDL) службы несмотря на то, что клиент WCF может успешно отправлять сообщения в конечные точки службы. Это так, как Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объекта (OID) в расширенных флагах использования, тогда как WCF не применяет такое ограничение. Если Internet Explorer не удается получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.  
  
## <a name="see-also"></a>См. также  
 [Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Практическое руководство. Извлечение данных и реализация совместимой службы](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
