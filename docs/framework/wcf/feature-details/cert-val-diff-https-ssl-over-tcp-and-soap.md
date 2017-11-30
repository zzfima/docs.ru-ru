---
title: "Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: certificates [WCF], validation differences
ms.assetid: 953a219f-4745-4019-9894-c70704f352e6
caps.latest.revision: "14"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: b0a29b59b6b2f7b8dd3a430b2395b18c1e4f83fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="certificate-validation-differences-between-https-ssl-over-tcp-and-soap-security"></a><span data-ttu-id="e6cf7-102">Различия проверки сертификатов с использованием средств обеспечения безопасности HTTPS, SSL по TCP и SOAP</span><span class="sxs-lookup"><span data-stu-id="e6cf7-102">Certificate Validation Differences Between HTTPS, SSL over TCP, and SOAP Security</span></span>
<span data-ttu-id="e6cf7-103">В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в дополнение к протоколам TLS по HTTP (HTTPS) или TCP можно использовать сертификаты с протоколом MLS (SOAP).</span><span class="sxs-lookup"><span data-stu-id="e6cf7-103">You can use certificates in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with message-layer (SOAP) security in addition to transport-layer security (TLS) over HTTP (HTTPS) or TCP.</span></span> <span data-ttu-id="e6cf7-104">В данном разделе описываются различия в способе, который используется для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-104">This topic describes differences in the way such certificates are validated.</span></span>  
  
## <a name="validation-of-https-client-certificates"></a><span data-ttu-id="e6cf7-105">Проверка сертификатов клиента HTTPS</span><span class="sxs-lookup"><span data-stu-id="e6cf7-105">Validation of HTTPS Client Certificates</span></span>  
 <span data-ttu-id="e6cf7-106">При использовании HTTPS для связи клиента и службы сертификат, который клиент использует для проверки подлинности службы, должен поддерживать цепь доверия.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-106">When using HTTPS to communicate between a client and a service, the certificate that the client uses to authenticate to the service must support chain trust.</span></span> <span data-ttu-id="e6cf7-107">То есть, сертификат должен связываться по цепочке с доверенным корневым центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-107">That is, it must chain to a trusted root certificate authority.</span></span> <span data-ttu-id="e6cf7-108">Если нет, уровень HTTP вызывает исключение <xref:System.Net.WebException> с сообщением «удаленный сервер вернул ошибку: (403) запрещено.»</span><span class="sxs-lookup"><span data-stu-id="e6cf7-108">If not, the HTTP layer raises a <xref:System.Net.WebException> with the message "The remote server returned an error: (403) Forbidden."</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="e6cf7-109">обрабатывает данное исключение как <xref:System.ServiceModel.Security.MessageSecurityException>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-109"> surfaces this exception as a <xref:System.ServiceModel.Security.MessageSecurityException>.</span></span>  
  
## <a name="validation-of-https-service-certificates"></a><span data-ttu-id="e6cf7-110">Проверка сертификатов службы HTTPS</span><span class="sxs-lookup"><span data-stu-id="e6cf7-110">Validation of HTTPS Service Certificates</span></span>  
 <span data-ttu-id="e6cf7-111">При использовании HTTPS для связи клиента и службы сертификат, используемый сервером для проверки подлинности службы, должен поддерживать цепь доверия.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-111">When using HTTPS to communicate between a client and a service, the certificate that the server authenticates with must support chain trust by default.</span></span> <span data-ttu-id="e6cf7-112">То есть, сертификат должен связываться по цепочке с доверенным корневым центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-112">That is, it must chain to a trusted root certificate authority.</span></span> <span data-ttu-id="e6cf7-113">Для проверки отмены сертификата проверка в сети не выполняется.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-113">No online check is performed to see whether the certificate has been revoked.</span></span> <span data-ttu-id="e6cf7-114">Данное поведение можно переопределить, зарегистрировав обратный звонок <xref:System.Net.Security.RemoteCertificateValidationCallback>, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-114">You can override this behavior by registering a <xref:System.Net.Security.RemoteCertificateValidationCallback> callback, as shown in the following code.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#1)] 
 [!code-vb[c_CertificateValidationDifferences#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#1)]  
  
 <span data-ttu-id="e6cf7-115">где подписывание `ValidateServerCertificate` показано ниже:</span><span class="sxs-lookup"><span data-stu-id="e6cf7-115">where the signature for `ValidateServerCertificate` is as follows:</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#2)]
 [!code-vb[c_CertificateValidationDifferences#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#2)]  
  
 <span data-ttu-id="e6cf7-116">Реализация `ValidateServerCertificate` может выполнить любые проверки, которые разработчик приложения-клиента сочтет необходимыми для проверки сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-116">Implementing `ValidateServerCertificate` can perform any checks that the client application developer deems necessary to validate the service certificate.</span></span>  
  
## <a name="validation-of-client-certificates-in-ssl-over-tcp-or-soap-security"></a><span data-ttu-id="e6cf7-117">Проверка сертификатов клиента в SSL по TCP или механизме безопасности SOAP</span><span class="sxs-lookup"><span data-stu-id="e6cf7-117">Validation of Client Certificates in SSL over TCP or SOAP Security</span></span>  
 <span data-ttu-id="e6cf7-118">При использовании протокола SSL по TCP или безопасности SOAP сертификаты клиента проверяются в соответствии со значением свойства <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> класса <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-118">When using Secure Sockets Layer (SSL) over TCP or message (SOAP) security, client certificates are validated according to the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.CertificateValidationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="e6cf7-119">Свойство установлено в одно из значений <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-119">The property is set to one of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> values.</span></span> <span data-ttu-id="e6cf7-120">Проверка отзыва сертификатов выполняется в соответствии со значениями свойства <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> класса <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-120">Revocation checking is performed according to the values of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication.RevocationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ClientCertificateAuthentication> class.</span></span> <span data-ttu-id="e6cf7-121">Свойство установлено в одно из значений <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-121">The property is set to one of the <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> values.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#3)]
 [!code-vb[c_CertificateValidationDifferences#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#3)]  
  
## <a name="validation-of-service-certificate-in-ssl-over-tcp-and-soap-security"></a><span data-ttu-id="e6cf7-122">Проверка сертификатов службы в SSL по TCP или механизме безопасности SOAP</span><span class="sxs-lookup"><span data-stu-id="e6cf7-122">Validation of Service Certificate in SSL over TCP and SOAP Security</span></span>  
 <span data-ttu-id="e6cf7-123">При использовании протокола SSL по TCP или безопасности SOAP сертификаты службы проверяются в соответствии со значением свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> класса <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-123">When using SSL over TCP or (SOAP) message security, service certificates are validated according to the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> class.</span></span> <span data-ttu-id="e6cf7-124">Свойство установлено в одно из значений <xref:System.ServiceModel.Security.X509CertificateValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-124">The property is set to one of the <xref:System.ServiceModel.Security.X509CertificateValidationMode> values.</span></span>  
  
 <span data-ttu-id="e6cf7-125">Проверка отзыва сертификатов выполняется в соответствии со значениями свойства <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> класса <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-125">Revocation checking is performed according to the values of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.RevocationMode%2A> property value of the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication> class.</span></span> <span data-ttu-id="e6cf7-126">Свойство установлено в одно из значений <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode>.</span><span class="sxs-lookup"><span data-stu-id="e6cf7-126">The property is set to one of the <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> values.</span></span>  
  
 [!code-csharp[c_CertificateValidationDifferences#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_certificatevalidationdifferences/cs/source.cs#4)]
 [!code-vb[c_CertificateValidationDifferences#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_certificatevalidationdifferences/vb/source.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="e6cf7-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e6cf7-127">See Also</span></span>  
 <xref:System.Net.Security.RemoteCertificateValidationCallback>  
 [<span data-ttu-id="e6cf7-128">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="e6cf7-128">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
