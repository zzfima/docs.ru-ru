---
title: Различия проверки сертификатов службы с использованием Internet Explorer и WCF
ms.date: 03/30/2017
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
ms.openlocfilehash: 0bced548cdc9423d1907de09e8b52ebe078d7c19
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61857705"
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="5830c-102">Различия проверки сертификатов службы с использованием Internet Explorer и WCF</span><span class="sxs-lookup"><span data-stu-id="5830c-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="5830c-103">Из-за различия между тем, как Internet Explorer и Windows Communication Foundation (WCF) проверяют сертификаты службы, когда используется протокол HTTPS это возможно, что Internet Explorer не сможете получить доступ к странице справки или Web Services Description Language (WSDL) службы, несмотря на то, что клиент WCF способен успешно отправлять сообщения в конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="5830c-103">Because of difference between the way Internet Explorer and Windows Communication Foundation (WCF) validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a WCF client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="5830c-104">Это обусловлено Internet Explorer проверяет, имеет ли сертификат службы `ServerAuthentication` идентификаторы объекта (OID) в расширенных флагах использования, в то время как WCF не обеспечивает такое ограничение.</span><span class="sxs-lookup"><span data-stu-id="5830c-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas WCF does not enforce such a constraint.</span></span> <span data-ttu-id="5830c-105">Если Internet Explorer не сможет получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="5830c-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5830c-106">См. также</span><span class="sxs-lookup"><span data-stu-id="5830c-106">See also</span></span>

- [<span data-ttu-id="5830c-107">Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP</span><span class="sxs-lookup"><span data-stu-id="5830c-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)
- [<span data-ttu-id="5830c-108">Практическое руководство. Извлечение данных и реализация совместимой службы</span><span class="sxs-lookup"><span data-stu-id="5830c-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
