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
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a><span data-ttu-id="758cd-102">Различия проверки сертификатов службы с использованием Internet Explorer и WCF</span><span class="sxs-lookup"><span data-stu-id="758cd-102">Differences Between Service Certificate Validation Done by Internet Explorer and WCF</span></span>
<span data-ttu-id="758cd-103">Ввиду различий между тем, как Internet Explorer и [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] проверяют сертификаты службы при использовании HTTPS, возможно, Internet Explorer не сможет получить доступ к странице справки или языку WSDL службы, даже несмотря на то что клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может успешно отправлять сообщения в конечные точки службы.</span><span class="sxs-lookup"><span data-stu-id="758cd-103">Because of difference between the way Internet Explorer and [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validate service certificates when HTTPS is used, it is possible that Internet Explorer will not be able to access the Help page or Web Services Description Language (WSDL) of a service even though a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client is able to successfully send messages to the service endpoints.</span></span> <span data-ttu-id="758cd-104">Это происходит потому, что Internet Explorer проверяет, имеет ли сертификат службы идентификаторы объекта (OID) `ServerAuthentication` в расширенных флагах использования, тогда как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] такое ограничение не применяет.</span><span class="sxs-lookup"><span data-stu-id="758cd-104">This is because Internet Explorer checks whether the service certificate has the `ServerAuthentication` object identifiers (OID) in the enhanced usage flags, whereas [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not enforce such a constraint.</span></span> <span data-ttu-id="758cd-105">Если Internet Explorer не удается получить доступ к странице справки службы или WSDL для службы, используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для доступа к метаданным службы.</span><span class="sxs-lookup"><span data-stu-id="758cd-105">If Internet Explorer is unable to access the service Help page or the WSDL for the service, use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to access the service metadata.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="758cd-106">См. также</span><span class="sxs-lookup"><span data-stu-id="758cd-106">See Also</span></span>  
 [<span data-ttu-id="758cd-107">Различия проверки сертификатов HTTPS, SSL по TCP или безопасности SOAP</span><span class="sxs-lookup"><span data-stu-id="758cd-107">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [<span data-ttu-id="758cd-108">Как: извлечение данных и реализация совместимой службы</span><span class="sxs-lookup"><span data-stu-id="758cd-108">How to: Retrieve Metadata and Implement a Compliant Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
