---
title: '&lt;certificate&gt; для &lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: e7d8e7abbc95521d85dc5999c36687f9becea9fb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32749287"
---
# <a name="ltcertificategt-for-ltidentitygt"></a><span data-ttu-id="8c5b3-102">&lt;certificate&gt; для &lt;identity&gt;</span><span class="sxs-lookup"><span data-stu-id="8c5b3-102">&lt;certificate&gt; for &lt;identity&gt;</span></span>
<span data-ttu-id="8c5b3-103">Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
 <span data-ttu-id="8c5b3-104">Дополнительные сведения о настройке значения элемента см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8c5b3-104">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="8c5b3-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8c5b3-105">\<identity></span></span>  
<span data-ttu-id="8c5b3-106">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="8c5b3-106">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c5b3-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8c5b3-107">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8c5b3-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8c5b3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8c5b3-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8c5b3-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8c5b3-110">Attributes</span></span>  
  
|<span data-ttu-id="8c5b3-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8c5b3-111">Attribute</span></span>|<span data-ttu-id="8c5b3-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8c5b3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8c5b3-113">encodedValue</span><span class="sxs-lookup"><span data-stu-id="8c5b3-113">encodedValue</span></span>|<span data-ttu-id="8c5b3-114">Кодировка Base64 сертификата.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-114">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8c5b3-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8c5b3-115">Child Elements</span></span>  
 <span data-ttu-id="8c5b3-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8c5b3-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8c5b3-117">Parent Elements</span></span>  
  
|<span data-ttu-id="8c5b3-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="8c5b3-118">Element</span></span>|<span data-ttu-id="8c5b3-119">Описание</span><span class="sxs-lookup"><span data-stu-id="8c5b3-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8c5b3-120">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8c5b3-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="8c5b3-121">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8c5b3-122">Пример</span><span class="sxs-lookup"><span data-stu-id="8c5b3-122">Example</span></span>  
 <span data-ttu-id="8c5b3-123">В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="8c5b3-123">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c5b3-124">См. также</span><span class="sxs-lookup"><span data-stu-id="8c5b3-124">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [<span data-ttu-id="8c5b3-125">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="8c5b3-125">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="8c5b3-126">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="8c5b3-126">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
