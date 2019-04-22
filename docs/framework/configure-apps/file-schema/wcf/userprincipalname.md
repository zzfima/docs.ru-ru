---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 9e7b845d39495dba1d1a19af95faf308b8b8c0fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188253"
---
# <a name="userprincipalname"></a><span data-ttu-id="dd566-101">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="dd566-101">\<userPrincipalName></span></span>
<span data-ttu-id="dd566-102">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="dd566-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="dd566-103">Дополнительные сведения о параметрах UPN см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="dd566-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="dd566-104">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="dd566-104">\<identity></span></span>  
<span data-ttu-id="dd566-105">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="dd566-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd566-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd566-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd566-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dd566-107">Attributes and Elements</span></span>  
 <span data-ttu-id="dd566-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dd566-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd566-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dd566-109">Attributes</span></span>  
  
|<span data-ttu-id="dd566-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dd566-110">Attribute</span></span>|<span data-ttu-id="dd566-111">Описание</span><span class="sxs-lookup"><span data-stu-id="dd566-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd566-112">value</span><span class="sxs-lookup"><span data-stu-id="dd566-112">value</span></span>|<span data-ttu-id="dd566-113">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="dd566-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="dd566-114">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="dd566-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="dd566-115">Формат: someone@example.com (как для адреса электронной почты).</span><span class="sxs-lookup"><span data-stu-id="dd566-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd566-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dd566-116">Child Elements</span></span>  
 <span data-ttu-id="dd566-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dd566-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd566-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dd566-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dd566-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd566-119">Element</span></span>|<span data-ttu-id="dd566-120">Описание</span><span class="sxs-lookup"><span data-stu-id="dd566-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dd566-121">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="dd566-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="dd566-122">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="dd566-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd566-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd566-123">Remarks</span></span>  
 <span data-ttu-id="dd566-124">Защищенный клиент Windows Communication Foundation (WCF), который подключается к конечной точке с использованием этого удостоверения использует имя участника-пользователя при проверке подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="dd566-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd566-125">Пример</span><span class="sxs-lookup"><span data-stu-id="dd566-125">Example</span></span>  
 <span data-ttu-id="dd566-126">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="dd566-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="dd566-127">См. также</span><span class="sxs-lookup"><span data-stu-id="dd566-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="dd566-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="dd566-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="dd566-129">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="dd566-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
