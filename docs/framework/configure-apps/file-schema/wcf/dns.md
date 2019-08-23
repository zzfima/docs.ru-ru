---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 35d33fd4d174c8e4ccdaaf1ac33884663340e16a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919128"
---
# <a name="dns"></a><span data-ttu-id="c6fc3-101">\<DNS-></span><span class="sxs-lookup"><span data-stu-id="c6fc3-101">\<dns></span></span>
<span data-ttu-id="c6fc3-102">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="c6fc3-103">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="c6fc3-104">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="c6fc3-105">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="c6fc3-106">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="c6fc3-106">\<identity></span></span>  
<span data-ttu-id="c6fc3-107">\<DNS-></span><span class="sxs-lookup"><span data-stu-id="c6fc3-107">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6fc3-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6fc3-108">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c6fc3-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c6fc3-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c6fc3-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c6fc3-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c6fc3-111">Attributes</span></span>  
  
|<span data-ttu-id="c6fc3-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c6fc3-112">Attribute</span></span>|<span data-ttu-id="c6fc3-113">Описание</span><span class="sxs-lookup"><span data-stu-id="c6fc3-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c6fc3-114">value</span><span class="sxs-lookup"><span data-stu-id="c6fc3-114">value</span></span>|<span data-ttu-id="c6fc3-115">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-115">The DNS of the certificate.</span></span> <span data-ttu-id="c6fc3-116">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-116">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="c6fc3-117">Пользователи могут запоминать отображаемые имена, <https://go.microsoft.com/fwlink/?prd=10929> например [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)или, проще, чем адреса на основе чисел, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-117">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c6fc3-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c6fc3-118">Child Elements</span></span>  
 <span data-ttu-id="c6fc3-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c6fc3-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c6fc3-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c6fc3-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="c6fc3-121">Element</span></span>|<span data-ttu-id="c6fc3-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c6fc3-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c6fc3-123">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="c6fc3-123">\<identity></span></span>](identity.md)|<span data-ttu-id="c6fc3-124">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c6fc3-125">Пример</span><span class="sxs-lookup"><span data-stu-id="c6fc3-125">Example</span></span>  
 <span data-ttu-id="c6fc3-126">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="c6fc3-126">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="c6fc3-127">См. также</span><span class="sxs-lookup"><span data-stu-id="c6fc3-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="c6fc3-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="c6fc3-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c6fc3-129">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="c6fc3-129">\<identity></span></span>](identity.md)
