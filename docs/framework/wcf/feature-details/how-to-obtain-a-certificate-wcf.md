---
title: Как выполнить Получение сертификата (WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: cefea47d77fef9a59234584b02b03dca4cd99ebe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709446"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="253a3-102">Как выполнить Получение сертификата (WCF)</span><span class="sxs-lookup"><span data-stu-id="253a3-102">How to: Obtain a Certificate (WCF)</span></span>
<span data-ttu-id="253a3-103">Windows Communication Foundation (WCF) использовать возможности, используют сертификаты X.509, сначала нужно получить сертификаты.</span><span class="sxs-lookup"><span data-stu-id="253a3-103">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="253a3-104">Получение сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="253a3-104">To obtain an X.509 certificate</span></span>  
  
1.  <span data-ttu-id="253a3-105">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="253a3-105">Choose one of the following:</span></span>  
  
    -   <span data-ttu-id="253a3-106">Приобретите сертификат в центре сертификации, например VeriSign, Inc.</span><span class="sxs-lookup"><span data-stu-id="253a3-106">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    -   <span data-ttu-id="253a3-107">Создайте собственную службу сертификатов и настройте ее так, чтобы центр сертификации подписывал сертификаты.</span><span class="sxs-lookup"><span data-stu-id="253a3-107">Set up your own certificate service and have a certification authority sign the certificates.</span></span> [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]<span data-ttu-id="253a3-108">, Windows 2000 Server, Windows 2000 Server Datacenter и Windows 2000 Datacenter Server включают службы сертификатов, поддерживающие инфраструктуру открытых ключей (PKI).</span><span class="sxs-lookup"><span data-stu-id="253a3-108">, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="253a3-109">В Windows Server 2008, использовать [служб сертификатов Active Directory](https://go.microsoft.com/fwlink/?LinkID=153483) роли для управления центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="253a3-109">In Windows Server 2008, use the [Active Directory Certificate Services](https://go.microsoft.com/fwlink/?LinkID=153483) role to manage a certification authority.</span></span>  
  
    -   <span data-ttu-id="253a3-110">Создайте собственную службу сертификатов и не настраивайте подпись сертификатов.</span><span class="sxs-lookup"><span data-stu-id="253a3-110">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="253a3-111">Независимо от того, какой способ выбран, получатель запроса SOAP, который содержит сертификат X.509, должен доверять сертификату X.509.</span><span class="sxs-lookup"><span data-stu-id="253a3-111">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="253a3-112">Это означает, что сертификат X.509 или издатель в цепи сертификатов находится в хранилище сертификатов "Доверенные лица" и сертификат X.509 не помещен в хранилище ненадежных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="253a3-112">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="253a3-113">См. также</span><span class="sxs-lookup"><span data-stu-id="253a3-113">See also</span></span>
- [<span data-ttu-id="253a3-114">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="253a3-114">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="253a3-115">Практическое руководство. Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="253a3-115">How to: Create Temporary Certificates for Use During Development</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-temporary-certificates-for-use-during-development.md)
