---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7415cb3f1792d2de566161ae6c348ef591b4a0c3
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="ad16e-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="ad16e-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="ad16e-103">Задает набор URI, допустимых идентификаторов проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="ad16e-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="ad16e-104">Маркеры не будут приниматься, если только они относятся к одному из разрешенных URI аудитории.</span><span class="sxs-lookup"><span data-stu-id="ad16e-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="ad16e-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="ad16e-105">\<system.identityModel></span></span>  
<span data-ttu-id="ad16e-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ad16e-106">\<identityConfiguration></span></span>  
<span data-ttu-id="ad16e-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="ad16e-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="ad16e-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ad16e-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="ad16e-109">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="ad16e-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad16e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad16e-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <audienceUris mode=xs:string>  
          <add value=xs:string />  
          <clear />  
          <remove value=xs:string />  
        </audienceUris>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ad16e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ad16e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="ad16e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ad16e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ad16e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ad16e-113">Attributes</span></span>  
  
|<span data-ttu-id="ad16e-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ad16e-114">Attribute</span></span>|<span data-ttu-id="ad16e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="ad16e-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ad16e-116">режим</span><span class="sxs-lookup"><span data-stu-id="ad16e-116">mode</span></span>|<span data-ttu-id="ad16e-117"><xref:System.IdentityModel.Selectors.AudienceUriMode> Значение, которое указывает, должно ли применяться ограничения аудитории входящий токен.</span><span class="sxs-lookup"><span data-stu-id="ad16e-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="ad16e-118">Возможными значениями являются «Всегда», «Никогда» и «BearerKeyOnly».</span><span class="sxs-lookup"><span data-stu-id="ad16e-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="ad16e-119">Значение по умолчанию — «Always».</span><span class="sxs-lookup"><span data-stu-id="ad16e-119">The default is "Always".</span></span> <span data-ttu-id="ad16e-120">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="ad16e-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ad16e-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ad16e-121">Child Elements</span></span>  
  
|<span data-ttu-id="ad16e-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad16e-122">Element</span></span>|<span data-ttu-id="ad16e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="ad16e-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="ad16e-124">Добавляет URI, указанный параметром `value` атрибут в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="ad16e-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="ad16e-125">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ad16e-125">The `value` attribute is required.</span></span> <span data-ttu-id="ad16e-126">URI с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="ad16e-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="ad16e-127">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="ad16e-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="ad16e-128">Все идентификаторы будут удалены из коллекции.</span><span class="sxs-lookup"><span data-stu-id="ad16e-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="ad16e-129">Удаляет URI, указанный параметром `value` атрибута из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="ad16e-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="ad16e-130">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="ad16e-130">The `value` attribute is required.</span></span> <span data-ttu-id="ad16e-131">URI с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="ad16e-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ad16e-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ad16e-132">Parent Elements</span></span>  
  
|<span data-ttu-id="ad16e-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="ad16e-133">Element</span></span>|<span data-ttu-id="ad16e-134">Описание</span><span class="sxs-lookup"><span data-stu-id="ad16e-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ad16e-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ad16e-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="ad16e-136">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="ad16e-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad16e-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad16e-137">Remarks</span></span>  
 <span data-ttu-id="ad16e-138">По умолчанию коллекция пуста; Используйте `<add>`, `<clear>`, и `<remove>` элементов для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="ad16e-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="ad16e-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> и <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> объекты используют значения в коллекции URI аудитории для настройки любых разрешено аудитории ограничения URI в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектов.</span><span class="sxs-lookup"><span data-stu-id="ad16e-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="ad16e-140">`<audienceUris>` Представлен <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="ad16e-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="ad16e-141">Представляется отдельным URI, добавляемый в коллекцию <xref:System.IdentityModel.Configuration.AudienceUriElement> класса.</span><span class="sxs-lookup"><span data-stu-id="ad16e-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad16e-142">Использование `<audienceUris>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="ad16e-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="ad16e-143">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="ad16e-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad16e-144">Пример</span><span class="sxs-lookup"><span data-stu-id="ad16e-144">Example</span></span>  
 <span data-ttu-id="ad16e-145">Следующий код XML показано, как настроить допустимый URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="ad16e-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="ad16e-146">В этом примере настраивается один URI.</span><span class="sxs-lookup"><span data-stu-id="ad16e-146">This example configures a single URI.</span></span> <span data-ttu-id="ad16e-147">Принимаются только токены, заданные для данного универсального кода Ресурса, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="ad16e-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
