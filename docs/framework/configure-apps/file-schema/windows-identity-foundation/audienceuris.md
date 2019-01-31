---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 556c444d5e48e27036c4b49338f6e70de7ef5c5d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55267280"
---
# <a name="audienceuris"></a><span data-ttu-id="6b986-101">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="6b986-101">\<audienceUris></span></span>
<span data-ttu-id="6b986-102">Задает набор URI, — это допустимые идентификаторы проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="6b986-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="6b986-103">Маркеры не будет принят, если только они относятся к одному из разрешенных URI аудитории.</span><span class="sxs-lookup"><span data-stu-id="6b986-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="6b986-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="6b986-104">\<system.identityModel></span></span>  
<span data-ttu-id="6b986-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b986-105">\<identityConfiguration></span></span>  
<span data-ttu-id="6b986-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="6b986-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="6b986-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b986-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="6b986-108">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="6b986-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b986-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b986-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b986-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6b986-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6b986-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6b986-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b986-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6b986-112">Attributes</span></span>  
  
|<span data-ttu-id="6b986-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6b986-113">Attribute</span></span>|<span data-ttu-id="6b986-114">Описание</span><span class="sxs-lookup"><span data-stu-id="6b986-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b986-115">режим</span><span class="sxs-lookup"><span data-stu-id="6b986-115">mode</span></span>|<span data-ttu-id="6b986-116"><xref:System.IdentityModel.Selectors.AudienceUriMode> Значение, указывающее, должна ли применяться ограничение аудитории на входящий токен.</span><span class="sxs-lookup"><span data-stu-id="6b986-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="6b986-117">Возможные значения: «Всегда», «Никогда» и «BearerKeyOnly».</span><span class="sxs-lookup"><span data-stu-id="6b986-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="6b986-118">По умолчанию используется «Всегда».</span><span class="sxs-lookup"><span data-stu-id="6b986-118">The default is "Always".</span></span> <span data-ttu-id="6b986-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6b986-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b986-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6b986-120">Child Elements</span></span>  
  
|<span data-ttu-id="6b986-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b986-121">Element</span></span>|<span data-ttu-id="6b986-122">Описание:</span><span class="sxs-lookup"><span data-stu-id="6b986-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="6b986-123">Добавляет URI, указанный параметром `value` атрибут в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="6b986-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="6b986-124">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="6b986-124">The `value` attribute is required.</span></span> <span data-ttu-id="6b986-125">URI с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="6b986-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="6b986-126">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="6b986-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="6b986-127">Все идентификаторы будут удалены из коллекции.</span><span class="sxs-lookup"><span data-stu-id="6b986-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="6b986-128">Удаляет URI, указанный параметром `value` атрибут из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="6b986-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="6b986-129">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="6b986-129">The `value` attribute is required.</span></span> <span data-ttu-id="6b986-130">URI с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="6b986-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b986-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6b986-131">Parent Elements</span></span>  
  
|<span data-ttu-id="6b986-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="6b986-132">Element</span></span>|<span data-ttu-id="6b986-133">Описание</span><span class="sxs-lookup"><span data-stu-id="6b986-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b986-134">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6b986-134">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="6b986-135">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="6b986-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b986-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="6b986-136">Remarks</span></span>  
 <span data-ttu-id="6b986-137">По умолчанию коллекция пуста; Используйте `<add>`, `<clear>`, и `<remove>` элементы для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="6b986-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="6b986-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> и <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> объектам используются значения в коллекцию URI аудитории для настройки любых допускается audience URI ограничения в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектов.</span><span class="sxs-lookup"><span data-stu-id="6b986-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="6b986-139">`<audienceUris>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="6b986-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="6b986-140">Представлен отдельным URI, добавляемый в коллекцию <xref:System.IdentityModel.Configuration.AudienceUriElement> класса.</span><span class="sxs-lookup"><span data-stu-id="6b986-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b986-141">Использование `<audienceUris>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="6b986-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="6b986-142">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="6b986-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b986-143">Пример</span><span class="sxs-lookup"><span data-stu-id="6b986-143">Example</span></span>  
 <span data-ttu-id="6b986-144">Следующий код XML показано, как настроить допустимые URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="6b986-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="6b986-145">В этом примере настраивается один URI.</span><span class="sxs-lookup"><span data-stu-id="6b986-145">This example configures a single URI.</span></span> <span data-ttu-id="6b986-146">Токены, заданные для данного универсального кода Ресурса будут приняты, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="6b986-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
