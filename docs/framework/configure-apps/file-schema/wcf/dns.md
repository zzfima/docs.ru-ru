---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: c68cabd03eca71b41a0d0acce26897fa2653f4d3
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855375"
---
# <a name="dns"></a><span data-ttu-id="0218a-101">\<DNS-></span><span class="sxs-lookup"><span data-stu-id="0218a-101">\<dns></span></span>
<span data-ttu-id="0218a-102">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="0218a-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="0218a-103">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="0218a-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="0218a-104">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="0218a-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="0218a-105">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="0218a-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="0218a-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="0218a-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="0218a-107">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="0218a-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="0218a-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="0218a-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="0218a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="0218a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="0218a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> удостоверений**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="0218a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="0218a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<DNS->**</span><span class="sxs-lookup"><span data-stu-id="0218a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0218a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0218a-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0218a-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0218a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="0218a-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0218a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0218a-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0218a-115">Attributes</span></span>  
  
|<span data-ttu-id="0218a-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0218a-116">Attribute</span></span>|<span data-ttu-id="0218a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0218a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0218a-118">value</span><span class="sxs-lookup"><span data-stu-id="0218a-118">value</span></span>|<span data-ttu-id="0218a-119">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="0218a-119">The DNS of the certificate.</span></span> <span data-ttu-id="0218a-120">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="0218a-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="0218a-121">Пользователи могут запоминать отображаемые имена, <https://go.microsoft.com/fwlink/?prd=10929> например [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165)или, проще, чем адреса на основе чисел, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="0218a-121">Users can remember display names, such as <https://go.microsoft.com/fwlink/?prd=10929> or [https://go.microsoft.com/fwlink/?LinkID=96165](https://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0218a-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0218a-122">Child Elements</span></span>  
 <span data-ttu-id="0218a-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="0218a-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0218a-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0218a-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0218a-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="0218a-125">Element</span></span>|<span data-ttu-id="0218a-126">Описание</span><span class="sxs-lookup"><span data-stu-id="0218a-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0218a-127">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="0218a-127">\<identity></span></span>](identity.md)|<span data-ttu-id="0218a-128">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="0218a-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0218a-129">Пример</span><span class="sxs-lookup"><span data-stu-id="0218a-129">Example</span></span>  
 <span data-ttu-id="0218a-130">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="0218a-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="0218a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0218a-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="0218a-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="0218a-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="0218a-133">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="0218a-133">\<identity></span></span>](identity.md)
