---
title: "Практическое руководство. Получение сертификата (WCF)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 468298c7a0ea673a90e0cde9d481333fad60e4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="68668-102">Практическое руководство. Получение сертификата (WCF)</span><span class="sxs-lookup"><span data-stu-id="68668-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="68668-103">Чтобы воспользоваться какими-либо функциями [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], которые используют сертификаты X.509, сначала нужно получить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="68668-103">To use any of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="68668-104">Получение сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="68668-104">To obtain an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="68668-105">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="68668-105">Choose one of the following:</span></span>  
  
    -   <span data-ttu-id="68668-106">Приобретите сертификат в центре сертификации, например VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="68668-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    -   <span data-ttu-id="68668-107">Создайте собственную службу сертификатов и настройте ее так, чтобы центр сертификации подписывал сертификаты.</span><span class="sxs-lookup"><span data-stu-id="68668-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="68668-108">, Windows 2000 Server, Windows 2000 Server Datacenter и Windows 2000 Datacenter Server включают службы сертификатов, поддерживающие инфраструктуру открытых ключей (PKI).</span><span class="sxs-lookup"><span data-stu-id="68668-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="68668-109">В Windows Server 2008 с помощью [служб сертификатов Active Directory](http://go.microsoft.com/fwlink/?LinkID=153483) роли для управления центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="68668-109">In Windows Server 2008, use the [Active Directory Certificate Services](http://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    -   <span data-ttu-id="68668-110">Создайте собственную службу сертификатов и не настраивайте подпись сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68668-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="68668-111">Независимо от того, какой способ выбран, получатель запроса SOAP, который содержит сертификат X.509, должен доверять сертификату X.509.</span><span class="sxs-lookup"><span data-stu-id="68668-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="68668-112">Это означает, что сертификат X.509 или издатель в цепи сертификатов находится в хранилище сертификатов "Доверенные лица" и сертификат X.509 не помещен в хранилище ненадежных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68668-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68668-113">См. также</span><span class="sxs-lookup"><span data-stu-id="68668-113">See Also</span></span>  
 [<span data-ttu-id="68668-114">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="68668-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="68668-115">Как: создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="68668-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
