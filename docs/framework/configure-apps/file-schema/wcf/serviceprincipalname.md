---
title: '&lt;servicePrincipalName&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e472c7fcfd57341074489a75f7954be38291523b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="f486e-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="f486e-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="f486e-103">Указывает идентификацию службы по имени субъекта-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="f486e-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="f486e-104">Дополнительные сведения о настройке имени участника-службы см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f486e-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="f486e-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="f486e-105">\<identity></span></span>  
<span data-ttu-id="f486e-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="f486e-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f486e-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f486e-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f486e-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f486e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="f486e-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f486e-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f486e-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f486e-110">Attributes</span></span>  
  
|<span data-ttu-id="f486e-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f486e-111">Attribute</span></span>|<span data-ttu-id="f486e-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f486e-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f486e-113">value</span><span class="sxs-lookup"><span data-stu-id="f486e-113">value</span></span>|<span data-ttu-id="f486e-114">Имя, по которому клиент однозначно идентифицирует экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="f486e-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="f486e-115">Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="f486e-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="f486e-116">Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f486e-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f486e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f486e-117">Child Elements</span></span>  
 <span data-ttu-id="f486e-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f486e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f486e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f486e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="f486e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="f486e-120">Element</span></span>|<span data-ttu-id="f486e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="f486e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f486e-122">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="f486e-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f486e-123">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="f486e-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f486e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="f486e-124">Remarks</span></span>  
 <span data-ttu-id="f486e-125">Безопасный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с этим идентификатором, использует SPN при выполнении проверки подлинности SSPI в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="f486e-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f486e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="f486e-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="f486e-127">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="f486e-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="f486e-128">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="f486e-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
