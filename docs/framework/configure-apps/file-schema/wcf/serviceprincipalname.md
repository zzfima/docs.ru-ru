---
title: '&lt;servicePrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: a22a905744980d0b370023e6236734a9bb0d6357
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54150647"
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="43f0c-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="43f0c-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="43f0c-103">Указывает идентификацию службы по имени субъекта-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="43f0c-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="43f0c-104">Дополнительные сведения о настройке SPN см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="43f0c-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="43f0c-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="43f0c-105">\<identity></span></span>  
<span data-ttu-id="43f0c-106">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="43f0c-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f0c-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43f0c-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="43f0c-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="43f0c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="43f0c-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="43f0c-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="43f0c-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="43f0c-110">Attributes</span></span>  
  
|<span data-ttu-id="43f0c-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="43f0c-111">Attribute</span></span>|<span data-ttu-id="43f0c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="43f0c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="43f0c-113">value</span><span class="sxs-lookup"><span data-stu-id="43f0c-113">value</span></span>|<span data-ttu-id="43f0c-114">Имя, по которому клиент однозначно идентифицирует экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="43f0c-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="43f0c-115">Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="43f0c-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="43f0c-116">Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="43f0c-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="43f0c-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="43f0c-117">Child Elements</span></span>  
 <span data-ttu-id="43f0c-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="43f0c-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="43f0c-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="43f0c-119">Parent Elements</span></span>  
  
|<span data-ttu-id="43f0c-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="43f0c-120">Element</span></span>|<span data-ttu-id="43f0c-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="43f0c-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="43f0c-122">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="43f0c-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="43f0c-123">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="43f0c-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43f0c-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="43f0c-124">Remarks</span></span>  
 <span data-ttu-id="43f0c-125">Защищенный клиент Windows Communication Foundation (WCF), который подключается к конечной точке с использованием этого удостоверения использует SPN при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="43f0c-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f0c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="43f0c-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="43f0c-127">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="43f0c-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="43f0c-128">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="43f0c-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
