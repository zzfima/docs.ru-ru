---
title: Различия проверки сертификатов службы с использованием Internet Explorer и WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 08a790dbbc8bc51a1e47bbcbcf90ec7c035bf3df
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549789"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Различия проверки сертификатов службы с использованием Internet Explorer и WCF
Из-за различия между тем, как Internet Explorer и Windows Communication Foundation (WCF) проверяют сертификаты службы, когда используется протокол HTTPS это возможно, что Internet Explorer не сможете получить доступ к странице справки или Web Services Description Language (WSDL) службы, несмотря на то, что клиент WCF способен успешно отправлять сообщения в конечные точки службы. Это обусловлено Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объекта (OID) в расширенных флагах использования, в то время как WCF не обеспечивает такое ограничение. Если Internet Explorer не сможет получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданных службы.  
  
## <a name="see-also"></a>См. также
- [Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [Практическое руководство. Извлечение данных и реализация совместимой службы](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
