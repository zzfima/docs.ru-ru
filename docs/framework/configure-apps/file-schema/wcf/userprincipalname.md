---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: ff38a6975d1ec73c1a3014b94198ba630c3fec31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149984"
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="0da7b-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="0da7b-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="0da7b-103">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="0da7b-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="0da7b-104">Дополнительные сведения о параметрах UPN см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="0da7b-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="0da7b-105">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="0da7b-105">\<identity></span></span>  
<span data-ttu-id="0da7b-106">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="0da7b-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0da7b-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0da7b-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0da7b-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0da7b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0da7b-109">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0da7b-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0da7b-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0da7b-110">Attributes</span></span>  
  
|<span data-ttu-id="0da7b-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0da7b-111">Attribute</span></span>|<span data-ttu-id="0da7b-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0da7b-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0da7b-113">value</span><span class="sxs-lookup"><span data-stu-id="0da7b-113">value</span></span>|<span data-ttu-id="0da7b-114">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="0da7b-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="0da7b-115">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="0da7b-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="0da7b-116">Формат: someone@example.com (как для адреса электронной почты).</span><span class="sxs-lookup"><span data-stu-id="0da7b-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0da7b-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0da7b-117">Child Elements</span></span>  
 <span data-ttu-id="0da7b-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="0da7b-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0da7b-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0da7b-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0da7b-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="0da7b-120">Element</span></span>|<span data-ttu-id="0da7b-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="0da7b-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0da7b-122">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="0da7b-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="0da7b-123">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="0da7b-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0da7b-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="0da7b-124">Remarks</span></span>  
 <span data-ttu-id="0da7b-125">Защищенный клиент Windows Communication Foundation (WCF), который подключается к конечной точке с использованием этого удостоверения использует имя участника-пользователя при проверке подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="0da7b-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0da7b-126">Пример</span><span class="sxs-lookup"><span data-stu-id="0da7b-126">Example</span></span>  
 <span data-ttu-id="0da7b-127">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="0da7b-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="0da7b-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0da7b-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="0da7b-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="0da7b-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="0da7b-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="0da7b-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
