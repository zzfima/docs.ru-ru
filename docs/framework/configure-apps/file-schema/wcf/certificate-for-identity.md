---
title: '&lt;certificate&gt; для &lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 0b65157aea84760f3e52bc294f7559967fc308f1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146918"
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="8e11a-102">&lt;certificate&gt; для &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="8e11a-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="8e11a-103">Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="8e11a-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="8e11a-104">Дополнительные сведения о настройке значения элемента см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8e11a-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="8e11a-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8e11a-105">\<identity></span></span>  
<span data-ttu-id="8e11a-106">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="8e11a-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e11a-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e11a-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8e11a-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8e11a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8e11a-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8e11a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8e11a-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8e11a-110">Attributes</span></span>  
  
|<span data-ttu-id="8e11a-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8e11a-111">Attribute</span></span>|<span data-ttu-id="8e11a-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8e11a-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8e11a-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="8e11a-113">encodedValue</span></span>|<span data-ttu-id="8e11a-114">Кодировка Base64 сертификата.</span><span class="sxs-lookup"><span data-stu-id="8e11a-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8e11a-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8e11a-115">Child Elements</span></span>  
 <span data-ttu-id="8e11a-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8e11a-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8e11a-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8e11a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8e11a-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="8e11a-118">Element</span></span>|<span data-ttu-id="8e11a-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8e11a-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8e11a-120">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8e11a-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8e11a-121">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="8e11a-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8e11a-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8e11a-122">Example</span></span>  
 <span data-ttu-id="8e11a-123">В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="8e11a-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="8e11a-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8e11a-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="8e11a-125">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="8e11a-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="8e11a-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8e11a-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
