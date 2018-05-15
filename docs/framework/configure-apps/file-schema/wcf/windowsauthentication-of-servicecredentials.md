---
title: '&lt;windowsAuthentication&gt; для &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: 9872b1f2520661ff3f31cef94b6822bb345ebfdf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltwindowsauthenticationgt-of-ltservicecredentialsgt"></a><span data-ttu-id="dc9af-102">&lt;windowsAuthentication&gt; для &lt;serviceCredentials&gt;</span><span class="sxs-lookup"><span data-stu-id="dc9af-102">&lt;windowsAuthentication&gt; of &lt;serviceCredentials&gt;</span></span>
<span data-ttu-id="dc9af-103">Задает параметры учетной записи службы Windows.</span><span class="sxs-lookup"><span data-stu-id="dc9af-103">Specifies the settings of a Windows service credential.</span></span>  
  
 <span data-ttu-id="dc9af-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dc9af-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc9af-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="dc9af-105">\<behaviors></span></span>  
<span data-ttu-id="dc9af-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dc9af-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="dc9af-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dc9af-107">\<behavior></span></span>  
<span data-ttu-id="dc9af-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="dc9af-108">\<serviceCredentials></span></span>  
<span data-ttu-id="dc9af-109">\<windowsAuthentication ></span><span class="sxs-lookup"><span data-stu-id="dc9af-109">\<windowsAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc9af-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dc9af-110">Syntax</span></span>  
  
```xml  
<windowsAuthentication  
      allowAnonymousLogons="Boolean"  
      includeWindowsGroups="Boolean" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc9af-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dc9af-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc9af-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dc9af-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc9af-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dc9af-113">Attributes</span></span>  
  
|<span data-ttu-id="dc9af-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dc9af-114">Attribute</span></span>|<span data-ttu-id="dc9af-115">Описание</span><span class="sxs-lookup"><span data-stu-id="dc9af-115">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="dc9af-116">Необязательный логический атрибут, который задает, включает ли система группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="dc9af-116">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="dc9af-117">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="dc9af-117">The default is `true`.</span></span><br /><br /> <span data-ttu-id="dc9af-118">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="dc9af-118">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="dc9af-119">Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="dc9af-119">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="dc9af-120">Необязательный логический атрибут, который указывает, разрешены ли анонимные, не прошедшие проверку подлинности вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="dc9af-120">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="dc9af-121">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="dc9af-121">The default is `false`.</span></span><br /><br /> <span data-ttu-id="dc9af-122">Когда атрибуту `clientCredentialType` привязки задано значение `Windows`, система не разрешает анонимные вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="dc9af-122">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="dc9af-123">Это значит, что доступ к системе разрешен только прошедшим проверку подлинности вызывающим объектам домена или рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="dc9af-123">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="dc9af-124">Это поведение можно переопределить с помощью данного атрибута.</span><span class="sxs-lookup"><span data-stu-id="dc9af-124">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="dc9af-125">Используйте этот режим с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="dc9af-125">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dc9af-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dc9af-126">Child Elements</span></span>  
 <span data-ttu-id="dc9af-127">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dc9af-127">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc9af-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dc9af-128">Parent Elements</span></span>  
  
|<span data-ttu-id="dc9af-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="dc9af-129">Element</span></span>|<span data-ttu-id="dc9af-130">Описание</span><span class="sxs-lookup"><span data-stu-id="dc9af-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc9af-131">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="dc9af-131">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="dc9af-132">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="dc9af-132">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc9af-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="dc9af-133">Remarks</span></span>  
 <span data-ttu-id="dc9af-134">Этот элемент используется, чтобы указать, разрешается ли доступ анонимных пользователей Windows путем установки атрибута `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="dc9af-134">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="dc9af-135">Также можно указать, включать ли сведения о группе, к которой принадлежат пользователи в AuthorizationContext, путем установки атрибута `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="dc9af-135">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="dc9af-136">Если атрибуту задано значение `true` (по умолчанию), служба может определить группы Windows, к которым принадлежит клиент.</span><span class="sxs-lookup"><span data-stu-id="dc9af-136">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc9af-137">См. также</span><span class="sxs-lookup"><span data-stu-id="dc9af-137">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WindowsServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>  
 <xref:System.ServiceModel.Security.WindowsServiceCredential>
