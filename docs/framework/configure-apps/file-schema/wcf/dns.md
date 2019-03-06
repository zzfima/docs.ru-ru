---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: eb5459625cf58feeef5ba29d76e74691a4f87cc8
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364701"
---
# <a name="dns"></a><span data-ttu-id="651c3-101">\<dns></span><span class="sxs-lookup"><span data-stu-id="651c3-101">\<dns></span></span>
<span data-ttu-id="651c3-102">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="651c3-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="651c3-103">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="651c3-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="651c3-104">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="651c3-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="651c3-105">Дополнительные сведения о настройке значения элемента см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="651c3-105">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="651c3-106">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="651c3-106">\<identity></span></span>  
<span data-ttu-id="651c3-107">\<dns></span><span class="sxs-lookup"><span data-stu-id="651c3-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="651c3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="651c3-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="651c3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="651c3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="651c3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="651c3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="651c3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="651c3-111">Attributes</span></span>  
  
|<span data-ttu-id="651c3-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="651c3-112">Attribute</span></span>|<span data-ttu-id="651c3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="651c3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="651c3-114">value</span><span class="sxs-lookup"><span data-stu-id="651c3-114">value</span></span>|<span data-ttu-id="651c3-115">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="651c3-115">The DNS of the certificate.</span></span> <span data-ttu-id="651c3-116">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="651c3-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="651c3-117">Пользователи могут запоминать отображаемые имена, такие как [ https://go.microsoft.com/fwlink/?prd=10929 ](https://go.microsoft.com/fwlink/?prd=10929) или [ https://go.microsoft.com/fwlink/?LinkID=96165 ](https://go.microsoft.com/fwlink/?LinkID=96165), проще, чем числовые адреса, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="651c3-117">Users can remember display names, such as [https://go.microsoft.com/fwlink/?prd=10929](https://go.microsoft.com/fwlink/?prd=10929) or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="651c3-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="651c3-118">Child Elements</span></span>  
 <span data-ttu-id="651c3-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="651c3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="651c3-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="651c3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="651c3-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="651c3-121">Element</span></span>|<span data-ttu-id="651c3-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="651c3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="651c3-123">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="651c3-123">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="651c3-124">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="651c3-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="651c3-125">Пример</span><span class="sxs-lookup"><span data-stu-id="651c3-125">Example</span></span>  
 <span data-ttu-id="651c3-126">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="651c3-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="651c3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="651c3-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="651c3-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="651c3-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="651c3-129">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="651c3-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
