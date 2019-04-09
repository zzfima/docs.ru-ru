---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 75e95bcbaee229f19bdfdd119b548ed612f4ddaa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204410"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="231f7-101">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="231f7-101">\<servicePrincipalName></span></span>
<span data-ttu-id="231f7-102">Указывает идентификацию службы по имени субъекта-службы (SPN).</span><span class="sxs-lookup"><span data-stu-id="231f7-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="231f7-103">Дополнительные сведения о настройке SPN см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="231f7-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="231f7-104">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="231f7-104">\<identity></span></span>  
<span data-ttu-id="231f7-105">\<servicePrincipalName ></span><span class="sxs-lookup"><span data-stu-id="231f7-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231f7-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="231f7-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="231f7-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="231f7-107">Attributes and Elements</span></span>  
 <span data-ttu-id="231f7-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="231f7-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="231f7-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="231f7-109">Attributes</span></span>  
  
|<span data-ttu-id="231f7-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="231f7-110">Attribute</span></span>|<span data-ttu-id="231f7-111">Описание</span><span class="sxs-lookup"><span data-stu-id="231f7-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="231f7-112">value</span><span class="sxs-lookup"><span data-stu-id="231f7-112">value</span></span>|<span data-ttu-id="231f7-113">Имя, по которому клиент однозначно идентифицирует экземпляр службы.</span><span class="sxs-lookup"><span data-stu-id="231f7-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="231f7-114">Если на компьютерах в лесу установлено несколько экземпляров службы, то каждый экземпляр должен иметь свое имя участника-службы.</span><span class="sxs-lookup"><span data-stu-id="231f7-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="231f7-115">Каждый экземпляр службы может иметь несколько имен участников-служб при наличии нескольких имен, которые могут использоваться клиентами для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="231f7-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="231f7-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="231f7-116">Child Elements</span></span>  
 <span data-ttu-id="231f7-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="231f7-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="231f7-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="231f7-118">Parent Elements</span></span>  
  
|<span data-ttu-id="231f7-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="231f7-119">Element</span></span>|<span data-ttu-id="231f7-120">Описание</span><span class="sxs-lookup"><span data-stu-id="231f7-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="231f7-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="231f7-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="231f7-122">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="231f7-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="231f7-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="231f7-123">Remarks</span></span>  
 <span data-ttu-id="231f7-124">Защищенный клиент Windows Communication Foundation (WCF), который подключается к конечной точке с использованием этого удостоверения использует SPN при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="231f7-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="231f7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="231f7-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="231f7-126">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="231f7-126">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="231f7-127">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="231f7-127">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
