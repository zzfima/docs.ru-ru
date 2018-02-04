---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 23e2599920c0ef0ea35569ec9b0b16b0f8735f1a
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="e19eb-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="e19eb-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="e19eb-103">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="e19eb-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="e19eb-104">Дополнительные сведения о настройке имени участника-пользователя см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e19eb-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="e19eb-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="e19eb-105">\<identity></span></span>  
<span data-ttu-id="e19eb-106">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="e19eb-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e19eb-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e19eb-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e19eb-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e19eb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e19eb-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e19eb-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e19eb-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e19eb-110">Attributes</span></span>  
  
|<span data-ttu-id="e19eb-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e19eb-111">Attribute</span></span>|<span data-ttu-id="e19eb-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e19eb-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e19eb-113">value</span><span class="sxs-lookup"><span data-stu-id="e19eb-113">value</span></span>|<span data-ttu-id="e19eb-114">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="e19eb-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="e19eb-115">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="e19eb-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="e19eb-116">Недопустимый формат: someone@example.com (аналогично адресу электронной почты).</span><span class="sxs-lookup"><span data-stu-id="e19eb-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e19eb-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e19eb-117">Child Elements</span></span>  
 <span data-ttu-id="e19eb-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e19eb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e19eb-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e19eb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e19eb-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="e19eb-120">Element</span></span>|<span data-ttu-id="e19eb-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="e19eb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e19eb-122">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="e19eb-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e19eb-123">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="e19eb-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e19eb-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="e19eb-124">Remarks</span></span>  
 <span data-ttu-id="e19eb-125">Безопасный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с этим идентификатором, использует UPN при выполнении проверки подлинности SSPI в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e19eb-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e19eb-126">Пример</span><span class="sxs-lookup"><span data-stu-id="e19eb-126">Example</span></span>  
 <span data-ttu-id="e19eb-127">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="e19eb-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e19eb-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e19eb-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="e19eb-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="e19eb-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="e19eb-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="e19eb-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
