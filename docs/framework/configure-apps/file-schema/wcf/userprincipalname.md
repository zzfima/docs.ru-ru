---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854822"
---
# <a name="userprincipalname"></a><span data-ttu-id="7f12a-101">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="7f12a-101">\<userPrincipalName></span></span>
<span data-ttu-id="7f12a-102">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="7f12a-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="7f12a-103">Дополнительные сведения о настройке имени участника-пользователя см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="7f12a-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="7f12a-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f12a-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f12a-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7f12a-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7f12a-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="7f12a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="7f12a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="7f12a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="7f12a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> удостоверений**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="7f12a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="7f12a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName >**</span><span class="sxs-lookup"><span data-stu-id="7f12a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f12a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7f12a-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f12a-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7f12a-111">Attributes and Elements</span></span>  
 <span data-ttu-id="7f12a-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7f12a-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f12a-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7f12a-113">Attributes</span></span>  
  
|<span data-ttu-id="7f12a-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7f12a-114">Attribute</span></span>|<span data-ttu-id="7f12a-115">Описание</span><span class="sxs-lookup"><span data-stu-id="7f12a-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f12a-116">value</span><span class="sxs-lookup"><span data-stu-id="7f12a-116">value</span></span>|<span data-ttu-id="7f12a-117">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="7f12a-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="7f12a-118">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="7f12a-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="7f12a-119">Формат: someone@example.com (как для адреса электронной почты).</span><span class="sxs-lookup"><span data-stu-id="7f12a-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f12a-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7f12a-120">Child Elements</span></span>  
 <span data-ttu-id="7f12a-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="7f12a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7f12a-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7f12a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="7f12a-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="7f12a-123">Element</span></span>|<span data-ttu-id="7f12a-124">Описание</span><span class="sxs-lookup"><span data-stu-id="7f12a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f12a-125">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="7f12a-125">\<identity></span></span>](identity.md)|<span data-ttu-id="7f12a-126">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="7f12a-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7f12a-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="7f12a-127">Remarks</span></span>  
 <span data-ttu-id="7f12a-128">Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя участника-пользователя при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="7f12a-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7f12a-129">Пример</span><span class="sxs-lookup"><span data-stu-id="7f12a-129">Example</span></span>  
 <span data-ttu-id="7f12a-130">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="7f12a-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="7f12a-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7f12a-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="7f12a-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="7f12a-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7f12a-133">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="7f12a-133">\<identity></span></span>](identity.md)
