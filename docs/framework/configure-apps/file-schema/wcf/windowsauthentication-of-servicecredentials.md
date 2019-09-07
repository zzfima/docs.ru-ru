---
title: <windowsAuthentication> из <serviceCredentials>
ms.date: 03/30/2017
ms.assetid: e0709473-0997-4de3-8f49-783527309a48
ms.openlocfilehash: ded04f6e87fce2e12dac8f681ba2d4178f8fd204
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399111"
---
# <a name="windowsauthentication-of-servicecredentials"></a><span data-ttu-id="4ef38-102">\<windowsAuthentication > \<ServiceCredentials ></span><span class="sxs-lookup"><span data-stu-id="4ef38-102">\<windowsAuthentication> of \<serviceCredentials></span></span>
<span data-ttu-id="4ef38-103">Задает параметры учетной записи службы Windows.</span><span class="sxs-lookup"><span data-stu-id="4ef38-103">Specifies the settings of a Windows service credential.</span></span>  
  
<span data-ttu-id="4ef38-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4ef38-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4ef38-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4ef38-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4ef38-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4ef38-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="4ef38-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4ef38-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="4ef38-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="4ef38-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="4ef38-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="4ef38-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="4ef38-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsAuthentication >**</span><span class="sxs-lookup"><span data-stu-id="4ef38-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ef38-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ef38-111">Syntax</span></span>  
  
```xml  
<windowsAuthentication allowAnonymousLogons="Boolean"
                       includeWindowsGroups="Boolean" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ef38-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4ef38-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4ef38-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4ef38-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ef38-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4ef38-114">Attributes</span></span>  
  
|<span data-ttu-id="4ef38-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4ef38-115">Attribute</span></span>|<span data-ttu-id="4ef38-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4ef38-116">Description</span></span>|  
|---------------|-----------------|  
|`includeWindowsGroups`|<span data-ttu-id="4ef38-117">Необязательный логический атрибут, который задает, включает ли система группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="4ef38-117">An optional Boolean attribute that specifies whether the system includes Windows groups in the security context.</span></span> <span data-ttu-id="4ef38-118">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="4ef38-118">The default is `true`.</span></span><br /><br /> <span data-ttu-id="4ef38-119">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="4ef38-119">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="4ef38-120">Если нет необходимости устанавливать список групп, к которым принадлежит пользователь, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4ef38-120">Set this attribute to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`allowAnonymousLogons`|<span data-ttu-id="4ef38-121">Необязательный логический атрибут, который указывает, разрешены ли анонимные, не прошедшие проверку подлинности вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="4ef38-121">An optional Boolean attribute that specifies whether anonymous, unauthenticated callers are allowed.</span></span> <span data-ttu-id="4ef38-122">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="4ef38-122">The default is `false`.</span></span><br /><br /> <span data-ttu-id="4ef38-123">Когда атрибуту `clientCredentialType` привязки задано значение `Windows`, система не разрешает анонимные вызывающие объекты.</span><span class="sxs-lookup"><span data-stu-id="4ef38-123">When the `clientCredentialType` attribute of a binding is set to `Windows`, the system does not allow anonymous callers.</span></span> <span data-ttu-id="4ef38-124">Это значит, что доступ к системе разрешен только прошедшим проверку подлинности вызывающим объектам домена или рабочей группы.</span><span class="sxs-lookup"><span data-stu-id="4ef38-124">This means that only domain or workgroup authenticated callers are allowed to access the system.</span></span> <span data-ttu-id="4ef38-125">Это поведение можно переопределить с помощью данного атрибута.</span><span class="sxs-lookup"><span data-stu-id="4ef38-125">You can override this behavior by using this attribute.</span></span><br /><br /> <span data-ttu-id="4ef38-126">Используйте этот режим с особой осторожностью.</span><span class="sxs-lookup"><span data-stu-id="4ef38-126">Use this setting with extreme caution.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ef38-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4ef38-127">Child Elements</span></span>  
 <span data-ttu-id="4ef38-128">Нет.</span><span class="sxs-lookup"><span data-stu-id="4ef38-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ef38-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4ef38-129">Parent Elements</span></span>  
  
|<span data-ttu-id="4ef38-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="4ef38-130">Element</span></span>|<span data-ttu-id="4ef38-131">Описание</span><span class="sxs-lookup"><span data-stu-id="4ef38-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ef38-132">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="4ef38-132">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="4ef38-133">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="4ef38-133">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ef38-134">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ef38-134">Remarks</span></span>  
 <span data-ttu-id="4ef38-135">Этот элемент используется, чтобы указать, разрешается ли доступ анонимных пользователей Windows путем установки атрибута `allowAnonymousLogons`.</span><span class="sxs-lookup"><span data-stu-id="4ef38-135">Use this element to specify whether to allow anonymous Windows users access by setting the `allowAnonymousLogons` attribute.</span></span> <span data-ttu-id="4ef38-136">Также можно указать, включать ли сведения о группе, к которой принадлежат пользователи в AuthorizationContext, путем установки атрибута `includeWindowsGroups`.</span><span class="sxs-lookup"><span data-stu-id="4ef38-136">You can also specify whether to include group information to which users belong in the AuthorizationContext by setting the `includeWindowsGroups` attribute.</span></span> <span data-ttu-id="4ef38-137">Если атрибуту задано значение `true` (по умолчанию), служба может определить группы Windows, к которым принадлежит клиент.</span><span class="sxs-lookup"><span data-stu-id="4ef38-137">If it is set to `true` (the default setting), the service can determine the Windows groups to which the client belongs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef38-138">См. также</span><span class="sxs-lookup"><span data-stu-id="4ef38-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WindowsServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.WindowsAuthentication%2A>
- <xref:System.ServiceModel.Security.WindowsServiceCredential>
