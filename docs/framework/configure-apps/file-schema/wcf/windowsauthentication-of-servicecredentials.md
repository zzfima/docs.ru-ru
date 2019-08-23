---
title: <windowsAuthentication> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 81793b0d58a95166bc23f98d46ce94a5f1e1d018
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940293"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="b9eea-102">\<windowsAuthentication > \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b9eea-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="b9eea-103">Задает параметры учетной записи службы Windows.</span><span class="sxs-lookup"><span data-stu-id="b9eea-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="b9eea-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b9eea-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="b9eea-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b9eea-105">\<behaviors></span></span>  
<span data-ttu-id="b9eea-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="b9eea-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="b9eea-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="b9eea-107">\<behavior></span></span>  
<span data-ttu-id="b9eea-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b9eea-108">\<serviceCredentials></span></span>  
<span data-ttu-id="b9eea-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="b9eea-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9eea-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9eea-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9eea-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b9eea-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b9eea-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b9eea-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9eea-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b9eea-113">Attributes</span></span>  
  
|<span data-ttu-id="b9eea-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b9eea-114">Attribute</span></span>|<span data-ttu-id="b9eea-115">Описание</span><span class="sxs-lookup"><span data-stu-id="b9eea-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="b9eea-116">Необязательный логический атрибут, который задает, включает ли система группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="b9eea-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="b9eea-117">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="b9eea-118">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="b9eea-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="b9eea-119">Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="b9eea-120">Необязательный логический атрибут, который указывает, разрешены ли анонимные, не прошедшие проверку подлинности вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="b9eea-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="b9eea-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="b9eea-122">Когда атрибуту `clientCredentialType` привязки задано значение `Windows`, система не разрешает анонимные вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="b9eea-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="b9eea-123">Это значит, что доступ к системе разрешен только прошедшим проверку подлинности вызывающим объектам домена или рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="b9eea-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="b9eea-124">Это поведение можно переопределить с помощью данного атрибута.</span><span class="sxs-lookup"><span data-stu-id="b9eea-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="b9eea-125">Используйте этот режим с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="b9eea-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9eea-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b9eea-126">Child Elements</span></span>  
 <span data-ttu-id="b9eea-127">Нет.</span><span class="sxs-lookup"><span data-stu-id="b9eea-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9eea-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b9eea-128">Parent Elements</span></span>  
  
|<span data-ttu-id="b9eea-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9eea-129">Element</span></span>|<span data-ttu-id="b9eea-130">Описание</span><span class="sxs-lookup"><span data-stu-id="b9eea-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9eea-131">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="b9eea-131">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="b9eea-132">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="b9eea-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9eea-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9eea-133">Remarks</span></span>  
 <span data-ttu-id="b9eea-134">Этот элемент используется, чтобы указать, разрешается ли доступ анонимных пользователей Windows путем установки атрибута `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="b9eea-135">Также можно указать, включать ли сведения о группе, к которой принадлежат пользователи в AuthorizationContext, путем установки атрибута `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="b9eea-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="b9eea-136">Если атрибуту задано значение `true` (по умолчанию), служба может определить группы Windows, к которым принадлежит клиент.</span><span class="sxs-lookup"><span data-stu-id="b9eea-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9eea-137">См. также</span><span class="sxs-lookup"><span data-stu-id="b9eea-137">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
