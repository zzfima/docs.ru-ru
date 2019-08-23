---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 423a3249a9298675517f0cff08566c3735fa35f1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940515"
---
# <a name="userprincipalname"></a><span data-ttu-id="28ed4-101">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="28ed4-101">\<userPrincipalName></span></span>
<span data-ttu-id="28ed4-102">Задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="28ed4-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="28ed4-103">Дополнительные сведения о настройке имени участника-пользователя см. в статье [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="28ed4-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="28ed4-104">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="28ed4-104">\<identity></span></span>  
<span data-ttu-id="28ed4-105">\<userPrincipalName ></span><span class="sxs-lookup"><span data-stu-id="28ed4-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28ed4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28ed4-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28ed4-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="28ed4-107">Attributes and Elements</span></span>  
 <span data-ttu-id="28ed4-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="28ed4-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28ed4-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="28ed4-109">Attributes</span></span>  
  
|<span data-ttu-id="28ed4-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="28ed4-110">Attribute</span></span>|<span data-ttu-id="28ed4-111">Описание</span><span class="sxs-lookup"><span data-stu-id="28ed4-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="28ed4-112">value</span><span class="sxs-lookup"><span data-stu-id="28ed4-112">value</span></span>|<span data-ttu-id="28ed4-113">Имя учетной записи пользователя (которая иногда называется именем входа пользователя) и имя домена, которое определяет домен, в котором располагается учетная запись пользователя.</span><span class="sxs-lookup"><span data-stu-id="28ed4-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="28ed4-114">Это стандартный способ входа в домен Windows.</span><span class="sxs-lookup"><span data-stu-id="28ed4-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="28ed4-115">Формат: someone@example.com (как для адреса электронной почты).</span><span class="sxs-lookup"><span data-stu-id="28ed4-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28ed4-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="28ed4-116">Child Elements</span></span>  
 <span data-ttu-id="28ed4-117">Нет.</span><span class="sxs-lookup"><span data-stu-id="28ed4-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28ed4-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="28ed4-118">Parent Elements</span></span>  
  
|<span data-ttu-id="28ed4-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="28ed4-119">Element</span></span>|<span data-ttu-id="28ed4-120">Описание</span><span class="sxs-lookup"><span data-stu-id="28ed4-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28ed4-121">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="28ed4-121">\<identity></span></span>](identity.md)|<span data-ttu-id="28ed4-122">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="28ed4-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28ed4-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="28ed4-123">Remarks</span></span>  
 <span data-ttu-id="28ed4-124">Клиент Secure Windows Communication Foundation (WCF), который подключается к конечной точке с этим удостоверением, использует имя участника-пользователя при выполнении проверки подлинности SSPI с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="28ed4-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28ed4-125">Пример</span><span class="sxs-lookup"><span data-stu-id="28ed4-125">Example</span></span>  
 <span data-ttu-id="28ed4-126">Приводимый ниже код конфигурации задает имя участника-пользователя (UPN) для службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="28ed4-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="28ed4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="28ed4-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="28ed4-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="28ed4-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="28ed4-129">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="28ed4-129">\<identity></span></span>](identity.md)
