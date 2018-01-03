---
title: '&lt;DNS&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4c7585cfa85d805a3d1454b0c16e38eee297280a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltdnsgt"></a><span data-ttu-id="83ad9-102">&lt;DNS&gt;</span><span class="sxs-lookup"><span data-stu-id="83ad9-102">&lt;dns&gt;</span></span>
<span data-ttu-id="83ad9-103">Задает ожидаемое удостоверение сервера.</span><span class="sxs-lookup"><span data-stu-id="83ad9-103">Specifies the expected identity of the server.</span></span> <span data-ttu-id="83ad9-104">Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением.</span><span class="sxs-lookup"><span data-stu-id="83ad9-104">This identity is valid for X509 Certificate authentication mode if the server’s certificate contains a DNS with the same value.</span></span> <span data-ttu-id="83ad9-105">Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.</span><span class="sxs-lookup"><span data-stu-id="83ad9-105">It is also valid for Windows authentication mode if the SPN has the same value.</span></span>  
  
 <span data-ttu-id="83ad9-106">Дополнительные сведения о настройке значения элемента см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="83ad9-106">For more information about setting the element value, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="83ad9-107">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="83ad9-107">\<identity></span></span>  
<span data-ttu-id="83ad9-108">\<DNS ></span><span class="sxs-lookup"><span data-stu-id="83ad9-108">\<dns></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83ad9-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="83ad9-109">Syntax</span></span>  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83ad9-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="83ad9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="83ad9-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="83ad9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83ad9-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="83ad9-112">Attributes</span></span>  
  
|<span data-ttu-id="83ad9-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="83ad9-113">Attribute</span></span>|<span data-ttu-id="83ad9-114">Описание</span><span class="sxs-lookup"><span data-stu-id="83ad9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="83ad9-115">value</span><span class="sxs-lookup"><span data-stu-id="83ad9-115">value</span></span>|<span data-ttu-id="83ad9-116">Сервер DNS сертификата.</span><span class="sxs-lookup"><span data-stu-id="83ad9-116">The DNS of the certificate.</span></span> <span data-ttu-id="83ad9-117">Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP.</span><span class="sxs-lookup"><span data-stu-id="83ad9-117">DNS is an industry-standard protocol used to locate computers on an IP-based network.</span></span> <span data-ttu-id="83ad9-118">Пользователям проще запоминать отображаемые имена [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) или [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), проще, чем числовые адреса, например 207.46.131.137.</span><span class="sxs-lookup"><span data-stu-id="83ad9-118">Users can remember display names, such as [http://go.microsoft.com/fwlink/?prd=10929](http://go.microsoft.com/fwlink/?prd=10929) or [http://go.microsoft.com/fwlink/?LinkID=96165](http://go.microsoft.com/fwlink/?LinkID=96165), easier than number-based addresses, such as 207.46.131.137.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83ad9-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="83ad9-119">Child Elements</span></span>  
 <span data-ttu-id="83ad9-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="83ad9-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83ad9-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="83ad9-121">Parent Elements</span></span>  
  
|<span data-ttu-id="83ad9-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="83ad9-122">Element</span></span>|<span data-ttu-id="83ad9-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="83ad9-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83ad9-124">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="83ad9-124">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="83ad9-125">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="83ad9-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="83ad9-126">Пример</span><span class="sxs-lookup"><span data-stu-id="83ad9-126">Example</span></span>  
 <span data-ttu-id="83ad9-127">В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="83ad9-127">The following configuration code specifies the DNS of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="83ad9-128">См. также</span><span class="sxs-lookup"><span data-stu-id="83ad9-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [<span data-ttu-id="83ad9-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="83ad9-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="83ad9-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="83ad9-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
