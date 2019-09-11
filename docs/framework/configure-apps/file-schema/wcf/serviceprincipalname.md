---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854990"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="ca503-101">\<">"</span><span class="sxs-lookup"><span data-stu-id="ca503-101">\<servicePrincipalName></span></span>
<span data-ttu-id="ca503-102">Указывает идентификацию службы по имени субъекта-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="ca503-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="ca503-103">Дополнительные сведения о настройке имени субъекта-службы см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="ca503-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="ca503-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ca503-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ca503-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="ca503-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="ca503-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="ca503-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="ca503-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="ca503-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="ca503-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> удостоверений**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="ca503-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="ca503-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<">"**</span><span class="sxs-lookup"><span data-stu-id="ca503-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca503-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca503-110">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca503-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ca503-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ca503-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ca503-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca503-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ca503-113">Attributes</span></span>  
  
|<span data-ttu-id="ca503-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ca503-114">Attribute</span></span>|<span data-ttu-id="ca503-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ca503-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca503-116">value</span><span class="sxs-lookup"><span data-stu-id="ca503-116">value</span></span>|<span data-ttu-id="ca503-117">Имя, по которому клиент однозначно определяет экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="ca503-117">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="ca503-118">Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="ca503-118">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="ca503-119">Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="ca503-119">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca503-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ca503-120">Child Elements</span></span>  
 <span data-ttu-id="ca503-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="ca503-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca503-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ca503-122">Parent Elements</span></span>  
  
|<span data-ttu-id="ca503-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca503-123">Element</span></span>|<span data-ttu-id="ca503-124">Описание</span><span class="sxs-lookup"><span data-stu-id="ca503-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ca503-125">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="ca503-125">\<identity></span></span>](identity.md)|<span data-ttu-id="ca503-126">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="ca503-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca503-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="ca503-127">Remarks</span></span>  
 <span data-ttu-id="ca503-128">Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя субъекта-службы при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="ca503-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca503-129">См. также</span><span class="sxs-lookup"><span data-stu-id="ca503-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="ca503-130">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="ca503-130">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ca503-131">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="ca503-131">\<identity></span></span>](identity.md)
