---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: 003221ed4dc7f4ccf72d2e0d3a91265e13172813
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941958"
---
# <a name="audienceuris"></a><span data-ttu-id="313be-101">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="313be-101">\<audienceUris></span></span>
<span data-ttu-id="313be-102">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="313be-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="313be-103">Токены не принимаются, если для одного из допустимых URI аудитории не задана область действия.</span><span class="sxs-lookup"><span data-stu-id="313be-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
 <span data-ttu-id="313be-104">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="313be-104">\<system.identityModel></span></span>  
<span data-ttu-id="313be-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="313be-105">\<identityConfiguration></span></span>  
<span data-ttu-id="313be-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="313be-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="313be-107">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="313be-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="313be-108">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="313be-108">\<audienceUris></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="313be-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="313be-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="313be-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="313be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="313be-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="313be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="313be-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="313be-112">Attributes</span></span>  
  
|<span data-ttu-id="313be-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="313be-113">Attribute</span></span>|<span data-ttu-id="313be-114">Описание</span><span class="sxs-lookup"><span data-stu-id="313be-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="313be-115">режим</span><span class="sxs-lookup"><span data-stu-id="313be-115">mode</span></span>|<span data-ttu-id="313be-116">Значение <xref:System.IdentityModel.Selectors.AudienceUriMode> типа, указывающее, следует ли применять ограничение аудитории к входящему токену.</span><span class="sxs-lookup"><span data-stu-id="313be-116">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="313be-117">Возможные значения: "всегда", "Never" и "Беареркэйонли".</span><span class="sxs-lookup"><span data-stu-id="313be-117">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="313be-118">Значение по умолчанию — Always.</span><span class="sxs-lookup"><span data-stu-id="313be-118">The default is "Always".</span></span> <span data-ttu-id="313be-119">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="313be-119">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="313be-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="313be-120">Child Elements</span></span>  
  
|<span data-ttu-id="313be-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="313be-121">Element</span></span>|<span data-ttu-id="313be-122">Описание</span><span class="sxs-lookup"><span data-stu-id="313be-122">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="313be-123">Добавляет URI, указанный `value` атрибутом, в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="313be-123">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="313be-124">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="313be-124">The `value` attribute is required.</span></span> <span data-ttu-id="313be-125">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="313be-125">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="313be-126">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="313be-126">Clears the audienceUris collection.</span></span> <span data-ttu-id="313be-127">Все идентификаторы удаляются из коллекции.</span><span class="sxs-lookup"><span data-stu-id="313be-127">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="313be-128">Удаляет URI, указанный `value` атрибутом из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="313be-128">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="313be-129">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="313be-129">The `value` attribute is required.</span></span> <span data-ttu-id="313be-130">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="313be-130">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="313be-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="313be-131">Parent Elements</span></span>  
  
|<span data-ttu-id="313be-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="313be-132">Element</span></span>|<span data-ttu-id="313be-133">Описание</span><span class="sxs-lookup"><span data-stu-id="313be-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="313be-134">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="313be-134">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="313be-135">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="313be-135">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="313be-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="313be-136">Remarks</span></span>  
 <span data-ttu-id="313be-137">По умолчанию коллекция пуста; Используйте `<add>`элементы `<clear>`, и`<remove>` для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="313be-137">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="313be-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>объекты <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> и используют значения в коллекции URI аудитории для настройки любых допустимых ограничений URI аудитории в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектах.</span><span class="sxs-lookup"><span data-stu-id="313be-138"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="313be-139">`<audienceUris>` Элемент представлен<xref:System.IdentityModel.Configuration.AudienceUriElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="313be-139">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="313be-140">Отдельный URI, добавленный в коллекцию, представлен <xref:System.IdentityModel.Configuration.AudienceUriElement> классом.</span><span class="sxs-lookup"><span data-stu-id="313be-140">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="313be-141">Использование `<audienceUris>` элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="313be-141">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="313be-142">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="313be-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="313be-143">Пример</span><span class="sxs-lookup"><span data-stu-id="313be-143">Example</span></span>  
 <span data-ttu-id="313be-144">В следующем коде XML показано, как настроить допустимые URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="313be-144">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="313be-145">В этом примере настраивается один универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="313be-145">This example configures a single URI.</span></span> <span data-ttu-id="313be-146">Маркеры, областью которых является этот URI, будут приняты, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="313be-146">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
