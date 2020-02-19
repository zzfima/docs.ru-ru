---
title: <dns>
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: e49a564c9793b371425b2b787586bb9d3cbed58b
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452231"
---
# <a name="dns"></a><span data-ttu-id="de8aa-101">\<> DNS</span><span class="sxs-lookup"><span data-stu-id="de8aa-101">\<dns></span></span>
<span data-ttu-id="de8aa-102">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="de8aa-102">Specifies the expected identity of the server.</span></span> <span data-ttu-id="de8aa-103">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="de8aa-103">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="de8aa-104">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="de8aa-104">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
<span data-ttu-id="de8aa-105">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="de8aa-105">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="de8aa-106">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de8aa-106">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de8aa-107">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="de8aa-107">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="de8aa-108">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<клиента**](client.md) ></span><span class="sxs-lookup"><span data-stu-id="de8aa-108">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="de8aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**Конечная точка**](endpoint-of-client.md) ></span><span class="sxs-lookup"><span data-stu-id="de8aa-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="de8aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identity >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="de8aa-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="de8aa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<dns >**</span><span class="sxs-lookup"><span data-stu-id="de8aa-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dns>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de8aa-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="de8aa-112">Syntax</span></span>  
  
```xml  
<dns value = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de8aa-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="de8aa-113">Attributes and Elements</span></span>  
 <span data-ttu-id="de8aa-114">Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="de8aa-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de8aa-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="de8aa-115">Attributes</span></span>  
  
|<span data-ttu-id="de8aa-116">attribute</span><span class="sxs-lookup"><span data-stu-id="de8aa-116">Attribute</span></span>|<span data-ttu-id="de8aa-117">Description</span><span class="sxs-lookup"><span data-stu-id="de8aa-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="de8aa-118">value</span><span class="sxs-lookup"><span data-stu-id="de8aa-118">value</span></span>|<span data-ttu-id="de8aa-119">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="de8aa-119">The DNS of the certificate.</span></span> <span data-ttu-id="de8aa-120">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="de8aa-120">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="de8aa-121">Пользователи могут запоминать отображаемые имена, например `https://go.microsoft.com/fwlink/?prd=10929` или `https://go.microsoft.com/fwlink/?LinkID=96165`, проще, чем адреса на основе чисел, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="de8aa-121">Users can remember display names, such as `https://go.microsoft.com/fwlink/?prd=10929` or `https://go.microsoft.com/fwlink/?LinkID=96165`, easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de8aa-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="de8aa-122">Child Elements</span></span>  
 <span data-ttu-id="de8aa-123">Нет.</span><span class="sxs-lookup"><span data-stu-id="de8aa-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de8aa-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="de8aa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="de8aa-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="de8aa-125">Element</span></span>|<span data-ttu-id="de8aa-126">Description</span><span class="sxs-lookup"><span data-stu-id="de8aa-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de8aa-127">> удостоверения \<</span><span class="sxs-lookup"><span data-stu-id="de8aa-127">\<identity></span></span>](identity.md)|<span data-ttu-id="de8aa-128">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="de8aa-128">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="de8aa-129">Пример</span><span class="sxs-lookup"><span data-stu-id="de8aa-129">Example</span></span>  
 <span data-ttu-id="de8aa-130">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="de8aa-130">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <dns value = "www.cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="de8aa-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="de8aa-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.DnsEndpointIdentity>
- [<span data-ttu-id="de8aa-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="de8aa-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="de8aa-133">> удостоверения \<</span><span class="sxs-lookup"><span data-stu-id="de8aa-133">\<identity></span></span>](identity.md)
