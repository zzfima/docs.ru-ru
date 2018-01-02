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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f9b4ec506097cf010af78b3504def08102e0774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="2ad73-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="2ad73-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="2ad73-103">Указывает идентификацию службы по имени субъекта-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="2ad73-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="2ad73-104">Дополнительные сведения о настройке имени участника-службы см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="2ad73-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="2ad73-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="2ad73-105">\<identity></span></span>  
<span data-ttu-id="2ad73-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="2ad73-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ad73-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ad73-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ad73-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ad73-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2ad73-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ad73-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ad73-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ad73-110">Attributes</span></span>  
  
|<span data-ttu-id="2ad73-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ad73-111">Attribute</span></span>|<span data-ttu-id="2ad73-112">Описание</span><span class="sxs-lookup"><span data-stu-id="2ad73-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2ad73-113">value</span><span class="sxs-lookup"><span data-stu-id="2ad73-113">value</span></span>|<span data-ttu-id="2ad73-114">Имя, по которому клиент однозначно идентифицирует экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="2ad73-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="2ad73-115">Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="2ad73-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="2ad73-116">Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2ad73-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ad73-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ad73-117">Child Elements</span></span>  
 <span data-ttu-id="2ad73-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="2ad73-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ad73-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ad73-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2ad73-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ad73-120">Element</span></span>|<span data-ttu-id="2ad73-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="2ad73-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ad73-122">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="2ad73-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="2ad73-123">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="2ad73-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ad73-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ad73-124">Remarks</span></span>  
 <span data-ttu-id="2ad73-125">Безопасный клиент [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], подключающийся к конечной точке с этим идентификатором, использует SPN при выполнении проверки подлинности SSPI в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="2ad73-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ad73-126">См. также</span><span class="sxs-lookup"><span data-stu-id="2ad73-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="2ad73-127">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="2ad73-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="2ad73-128">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="2ad73-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
