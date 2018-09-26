---
title: '&lt;audienceUris&gt;'
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: af138a4da49a48ed43e1bc8f2c2c81c56892feed
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47216654"
---
# <a name="ltaudienceurisgt"></a><span data-ttu-id="48b74-102">&lt;audienceUris&gt;</span><span class="sxs-lookup"><span data-stu-id="48b74-102">&lt;audienceUris&gt;</span></span>
<span data-ttu-id="48b74-103">Задает набор URI, — это допустимые идентификаторы проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="48b74-103">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="48b74-104">Маркеры не будет принят, если только они относятся к одному из разрешенных URI аудитории.</span><span class="sxs-lookup"><span data-stu-id="48b74-104">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="48b74-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="48b74-105">\<system.identityModel></span></span>  
<span data-ttu-id="48b74-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="48b74-106">\<identityConfiguration></span></span>  
<span data-ttu-id="48b74-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="48b74-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="48b74-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="48b74-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="48b74-109">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="48b74-109">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48b74-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48b74-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48b74-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="48b74-111">Attributes and Elements</span></span>  
 <span data-ttu-id="48b74-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="48b74-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48b74-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="48b74-113">Attributes</span></span>  
  
|<span data-ttu-id="48b74-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="48b74-114">Attribute</span></span>|<span data-ttu-id="48b74-115">Описание</span><span class="sxs-lookup"><span data-stu-id="48b74-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="48b74-116">режим</span><span class="sxs-lookup"><span data-stu-id="48b74-116">mode</span></span>|<span data-ttu-id="48b74-117"><xref:System.IdentityModel.Selectors.AudienceUriMode> Значение, указывающее, должна ли применяться ограничение аудитории на входящий токен.</span><span class="sxs-lookup"><span data-stu-id="48b74-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="48b74-118">Возможные значения: «Всегда», «Никогда» и «BearerKeyOnly».</span><span class="sxs-lookup"><span data-stu-id="48b74-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="48b74-119">По умолчанию используется «Всегда».</span><span class="sxs-lookup"><span data-stu-id="48b74-119">The default is "Always".</span></span> <span data-ttu-id="48b74-120">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="48b74-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48b74-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="48b74-121">Child Elements</span></span>  
  
|<span data-ttu-id="48b74-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="48b74-122">Element</span></span>|<span data-ttu-id="48b74-123">Описание</span><span class="sxs-lookup"><span data-stu-id="48b74-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="48b74-124">Добавляет URI, указанный параметром `value` атрибут в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="48b74-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="48b74-125">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="48b74-125">The `value` attribute is required.</span></span> <span data-ttu-id="48b74-126">URI с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="48b74-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="48b74-127">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="48b74-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="48b74-128">Все идентификаторы будут удалены из коллекции.</span><span class="sxs-lookup"><span data-stu-id="48b74-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="48b74-129">Удаляет URI, указанный параметром `value` атрибут из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="48b74-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="48b74-130">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="48b74-130">The `value` attribute is required.</span></span> <span data-ttu-id="48b74-131">URI с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="48b74-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48b74-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="48b74-132">Parent Elements</span></span>  
  
|<span data-ttu-id="48b74-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="48b74-133">Element</span></span>|<span data-ttu-id="48b74-134">Описание</span><span class="sxs-lookup"><span data-stu-id="48b74-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48b74-135">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="48b74-135">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="48b74-136">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="48b74-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48b74-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="48b74-137">Remarks</span></span>  
 <span data-ttu-id="48b74-138">По умолчанию коллекция пуста; Используйте `<add>`, `<clear>`, и `<remove>` элементы для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="48b74-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="48b74-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> и <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> объектам используются значения в коллекцию URI аудитории для настройки любых допускается audience URI ограничения в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектов.</span><span class="sxs-lookup"><span data-stu-id="48b74-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="48b74-140">`<audienceUris>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="48b74-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="48b74-141">Представлен отдельным URI, добавляемый в коллекцию <xref:System.IdentityModel.Configuration.AudienceUriElement> класса.</span><span class="sxs-lookup"><span data-stu-id="48b74-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48b74-142">Использование `<audienceUris>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="48b74-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="48b74-143">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="48b74-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48b74-144">Пример</span><span class="sxs-lookup"><span data-stu-id="48b74-144">Example</span></span>  
 <span data-ttu-id="48b74-145">Следующий код XML показано, как настроить допустимые URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="48b74-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="48b74-146">В этом примере настраивается один URI.</span><span class="sxs-lookup"><span data-stu-id="48b74-146">This example configures a single URI.</span></span> <span data-ttu-id="48b74-147">Токены, заданные для данного универсального кода Ресурса будут приняты, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="48b74-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
