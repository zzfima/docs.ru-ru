---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 26b45b17ecd7bbd3fffb5d03553834ec22eedc62
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611176"
---
# <a name="dns"></a><span data-ttu-id="cad79-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="cad79-101">\<dns></span></span>
<span data-ttu-id="cad79-102">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="cad79-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="cad79-103">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="cad79-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="cad79-104">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="cad79-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="cad79-105">Дополнительные сведения о настройке значения элемента см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="cad79-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="cad79-106">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="cad79-106">\<identity></span></span>  
<span data-ttu-id="cad79-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="cad79-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cad79-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cad79-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cad79-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cad79-109">Attributes and Elements</span></span>  
 <span data-ttu-id="cad79-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cad79-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cad79-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cad79-111">Attributes</span></span>  
  
|<span data-ttu-id="cad79-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cad79-112">Attribute</span></span>|<span data-ttu-id="cad79-113">Описание</span><span class="sxs-lookup"><span data-stu-id="cad79-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cad79-114">value</span><span class="sxs-lookup"><span data-stu-id="cad79-114">value</span></span>|<span data-ttu-id="cad79-115">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="cad79-115">The DNS of the certificate.</span></span> <span data-ttu-id="cad79-116">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="cad79-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="cad79-117">Пользователи могут запоминать отображаемые имена, такие как <https://go.microsoft.com/fwlink/?prd=10929> или [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), проще, чем числовые адреса, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="cad79-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cad79-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cad79-118">Child Elements</span></span>  
 <span data-ttu-id="cad79-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="cad79-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cad79-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cad79-120">Parent Elements</span></span>  
  
|<span data-ttu-id="cad79-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="cad79-121">Element</span></span>|<span data-ttu-id="cad79-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cad79-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cad79-123">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="cad79-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="cad79-124">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="cad79-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cad79-125">Пример</span><span class="sxs-lookup"><span data-stu-id="cad79-125">Example</span></span>  
 <span data-ttu-id="cad79-126">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="cad79-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="cad79-127">См. также</span><span class="sxs-lookup"><span data-stu-id="cad79-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="cad79-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="cad79-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="cad79-129">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="cad79-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
