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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="69987-102">Различия проверки сертификатов службы с использованием Internet Explorer и WCF</span><span class="sxs-lookup"><span data-stu-id="69987-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="69987-103">Из-за различия между тем, как Internet Explorer и Windows Communication Foundation (WCF) проверяют сертификаты службы при использовании HTTPS возможно, Internet Explorer не сможет получить доступ к странице справки или языка описания веб-служб (WSDL) службы несмотря на то, что клиент WCF может успешно отправлять сообщения в конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="69987-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="69987-104">Это так, как Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объекта (OID) в расширенных флагах использования, тогда как WCF не применяет такое ограничение.</span><span class="sxs-lookup"><span data-stu-id="69987-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="69987-105">Если Internet Explorer не удается получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.</span><span class="sxs-lookup"><span data-stu-id="69987-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69987-106">См. также</span><span class="sxs-lookup"><span data-stu-id="69987-106">See Also</span></span>  
 [<span data-ttu-id="69987-107">Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP</span><span class="sxs-lookup"><span data-stu-id="69987-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="69987-108">Практическое руководство. Извлечение данных и реализация совместимой службы</span><span class="sxs-lookup"><span data-stu-id="69987-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
