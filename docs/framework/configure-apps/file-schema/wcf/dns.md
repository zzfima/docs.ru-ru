---
title: '&lt;DNS&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 10fe4c63b08459914a16b2c736c1a454c6914a0b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145306"
---
# <a name="ltdnsgt"></a><span data-ttu-id="da900-102">&lt;DNS&gt;</span><span class="sxs-lookup"><span data-stu-id="da900-102">&lt;dns&gt;</span></span>
<span data-ttu-id="da900-103">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="da900-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="da900-104">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="da900-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="da900-105">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="da900-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="da900-106">Дополнительные сведения о настройке значения элемента см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="da900-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="da900-107">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="da900-107">\<identity></span></span>  
<span data-ttu-id="da900-108">\<DNS ></span><span class="sxs-lookup"><span data-stu-id="da900-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da900-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="da900-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da900-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="da900-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da900-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="da900-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da900-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="da900-112">Attributes</span></span>  
  
|<span data-ttu-id="da900-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="da900-113">Attribute</span></span>|<span data-ttu-id="da900-114">Описание</span><span class="sxs-lookup"><span data-stu-id="da900-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="da900-115">value</span><span class="sxs-lookup"><span data-stu-id="da900-115">value</span></span>|<span data-ttu-id="da900-116">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="da900-116">The DNS of the certificate.</span></span> <span data-ttu-id="da900-117">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="da900-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="da900-118">Пользователи могут запоминать отображаемые имена, такие как [ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929) или [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), проще, чем числовые адреса, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="da900-118">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da900-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="da900-119">Child Elements</span></span>  
 <span data-ttu-id="da900-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="da900-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da900-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="da900-121">Parent Elements</span></span>  
  
|<span data-ttu-id="da900-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="da900-122">Element</span></span>|<span data-ttu-id="da900-123">Описание</span><span class="sxs-lookup"><span data-stu-id="da900-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da900-124">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="da900-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="da900-125">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="da900-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="da900-126">Пример</span><span class="sxs-lookup"><span data-stu-id="da900-126">Example</span></span>  
 <span data-ttu-id="da900-127">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="da900-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="da900-128">См. также</span><span class="sxs-lookup"><span data-stu-id="da900-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="da900-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="da900-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="da900-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="da900-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
