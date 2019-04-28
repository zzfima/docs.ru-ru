---
title: <certificate> для <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 76bdcb40d5016d7fcbff6c0d9769819f710065fe
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673362"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="6be99-102">\<сертификат > для \<identity ></span><span class="sxs-lookup"><span data-stu-id="6be99-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="6be99-103">Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="6be99-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="6be99-104">Дополнительные сведения о настройке значения элемента см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6be99-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="6be99-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="6be99-105">\<identity></span></span>  
<span data-ttu-id="6be99-106">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="6be99-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6be99-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6be99-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6be99-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6be99-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6be99-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6be99-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6be99-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6be99-110">Attributes</span></span>  
  
|<span data-ttu-id="6be99-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6be99-111">Attribute</span></span>|<span data-ttu-id="6be99-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6be99-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6be99-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="6be99-113">encodedValue</span></span>|<span data-ttu-id="6be99-114">Кодировка Base64 сертификата.</span><span class="sxs-lookup"><span data-stu-id="6be99-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6be99-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6be99-115">Child Elements</span></span>  
 <span data-ttu-id="6be99-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6be99-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6be99-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6be99-117">Parent Elements</span></span>  
  
|<span data-ttu-id="6be99-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="6be99-118">Element</span></span>|<span data-ttu-id="6be99-119">Описание</span><span class="sxs-lookup"><span data-stu-id="6be99-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6be99-120">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="6be99-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="6be99-121">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="6be99-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6be99-122">Пример</span><span class="sxs-lookup"><span data-stu-id="6be99-122">Example</span></span>  
 <span data-ttu-id="6be99-123">В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="6be99-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="6be99-124">См. также</span><span class="sxs-lookup"><span data-stu-id="6be99-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="6be99-125">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="6be99-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6be99-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="6be99-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
