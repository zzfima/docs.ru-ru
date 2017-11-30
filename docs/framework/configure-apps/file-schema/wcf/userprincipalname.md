---
title: '&lt;userPrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b93a0cc24953024e265df418ec6dd738598dd0f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="b33b4-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="b33b4-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="b33b4-103">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="b33b4-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="b33b4-104">Дополнительные сведения о настройке имени участника-пользователя см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b33b4-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="b33b4-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="b33b4-105">\<identity></span></span>  
<span data-ttu-id="b33b4-106">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="b33b4-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b33b4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b33b4-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b33b4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b33b4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b33b4-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b33b4-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b33b4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b33b4-110">Attributes</span></span>  
  
|<span data-ttu-id="b33b4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b33b4-111">Attribute</span></span>|<span data-ttu-id="b33b4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="b33b4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b33b4-113">value</span><span class="sxs-lookup"><span data-stu-id="b33b4-113">value</span></span>|<span data-ttu-id="b33b4-114">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="b33b4-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="b33b4-115">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="b33b4-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="b33b4-116">Недопустимый формат: someone@example.com (аналогично адресу электронной почты).</span><span class="sxs-lookup"><span data-stu-id="b33b4-116">The format is: someone@example.com (as for an e-mail address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b33b4-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b33b4-117">Child Elements</span></span>  
 <span data-ttu-id="b33b4-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b33b4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b33b4-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b33b4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="b33b4-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="b33b4-120">Element</span></span>|<span data-ttu-id="b33b4-121">Описание</span><span class="sxs-lookup"><span data-stu-id="b33b4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b33b4-122">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="b33b4-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="b33b4-123">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="b33b4-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b33b4-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="b33b4-124">Remarks</span></span>  
 <span data-ttu-id="b33b4-125">Безопасный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с этим идентификатором, использует UPN при выполнении проверки подлинности SSPI в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="b33b4-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b33b4-126">Пример</span><span class="sxs-lookup"><span data-stu-id="b33b4-126">Example</span></span>  
 <span data-ttu-id="b33b4-127">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="b33b4-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b33b4-128">См. также</span><span class="sxs-lookup"><span data-stu-id="b33b4-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="b33b4-129">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b33b4-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="b33b4-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="b33b4-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
