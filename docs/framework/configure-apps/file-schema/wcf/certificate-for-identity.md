---
title: <certificate> для <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 52d1fa31cebd949c91809464976739ef1334af29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919619"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="39408-102">\<> сертификатов для \<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="39408-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="39408-103">Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="39408-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="39408-104">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="39408-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="39408-105">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="39408-105">\<identity></span></span>  
<span data-ttu-id="39408-106">\<> сертификата</span><span class="sxs-lookup"><span data-stu-id="39408-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39408-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39408-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39408-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="39408-108">Attributes and Elements</span></span>  
 <span data-ttu-id="39408-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="39408-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39408-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="39408-110">Attributes</span></span>  
  
|<span data-ttu-id="39408-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="39408-111">Attribute</span></span>|<span data-ttu-id="39408-112">Описание</span><span class="sxs-lookup"><span data-stu-id="39408-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="39408-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="39408-113">encodedValue</span></span>|<span data-ttu-id="39408-114">Кодировка Base64 сертификата.</span><span class="sxs-lookup"><span data-stu-id="39408-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39408-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="39408-115">Child Elements</span></span>  
 <span data-ttu-id="39408-116">Нет.</span><span class="sxs-lookup"><span data-stu-id="39408-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="39408-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="39408-117">Parent Elements</span></span>  
  
|<span data-ttu-id="39408-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="39408-118">Element</span></span>|<span data-ttu-id="39408-119">Описание</span><span class="sxs-lookup"><span data-stu-id="39408-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39408-120">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="39408-120">\<identity></span></span>](identity.md)|<span data-ttu-id="39408-121">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="39408-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="39408-122">Пример</span><span class="sxs-lookup"><span data-stu-id="39408-122">Example</span></span>  
 <span data-ttu-id="39408-123">В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="39408-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="39408-124">См. также</span><span class="sxs-lookup"><span data-stu-id="39408-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="39408-125">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="39408-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="39408-126">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="39408-126">\<identity></span></span>](identity.md)
