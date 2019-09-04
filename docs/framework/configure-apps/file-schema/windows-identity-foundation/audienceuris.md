---
title: <audienceUris>
ms.date: 03/30/2017
ms.assetid: 7a3d8515-d756-4afe-a22d-07cbe2217ee3
author: BrucePerlerMS
ms.openlocfilehash: bd04e4ebdf5c58adaeea0ff0ca5993d7d9ce38f1
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252171"
---
# <a name="audienceuris"></a><span data-ttu-id="bcc20-101">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="bcc20-101">\<audienceUris></span></span>
<span data-ttu-id="bcc20-102">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="bcc20-102">Specifies the set of URIs that are acceptable identifiers of the relying party (RP).</span></span> <span data-ttu-id="bcc20-103">Токены не принимаются, если для одного из допустимых URI аудитории не задана область действия.</span><span class="sxs-lookup"><span data-stu-id="bcc20-103">Tokens will not be accepted unless they are scoped for one of the allowed audience URIs.</span></span>  
  
<span data-ttu-id="bcc20-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bcc20-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bcc20-105">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="bcc20-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="bcc20-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bcc20-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="bcc20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="bcc20-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="bcc20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="bcc20-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="bcc20-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<audienceUris >**</span><span class="sxs-lookup"><span data-stu-id="bcc20-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<audienceUris>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcc20-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcc20-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bcc20-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bcc20-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bcc20-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bcc20-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bcc20-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bcc20-113">Attributes</span></span>  
  
|<span data-ttu-id="bcc20-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bcc20-114">Attribute</span></span>|<span data-ttu-id="bcc20-115">Описание</span><span class="sxs-lookup"><span data-stu-id="bcc20-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bcc20-116">режим</span><span class="sxs-lookup"><span data-stu-id="bcc20-116">mode</span></span>|<span data-ttu-id="bcc20-117">Значение <xref:System.IdentityModel.Selectors.AudienceUriMode> типа, указывающее, следует ли применять ограничение аудитории к входящему токену.</span><span class="sxs-lookup"><span data-stu-id="bcc20-117">An <xref:System.IdentityModel.Selectors.AudienceUriMode> value that specifies whether the audience restriction should be applied to an incoming token.</span></span> <span data-ttu-id="bcc20-118">Возможные значения: "всегда", "Never" и "Беареркэйонли".</span><span class="sxs-lookup"><span data-stu-id="bcc20-118">The possible values are "Always", "Never", and "BearerKeyOnly".</span></span> <span data-ttu-id="bcc20-119">Значение по умолчанию — Always.</span><span class="sxs-lookup"><span data-stu-id="bcc20-119">The default is "Always".</span></span> <span data-ttu-id="bcc20-120">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="bcc20-120">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bcc20-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bcc20-121">Child Elements</span></span>  
  
|<span data-ttu-id="bcc20-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcc20-122">Element</span></span>|<span data-ttu-id="bcc20-123">Описание</span><span class="sxs-lookup"><span data-stu-id="bcc20-123">Description</span></span>|  
|-------------|-----------------|  
|`<add value=xs:string>`|<span data-ttu-id="bcc20-124">Добавляет URI, указанный `value` атрибутом, в коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bcc20-124">Adds the URI specified by the `value` attribute to the audienceUris collection.</span></span> <span data-ttu-id="bcc20-125">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bcc20-125">The `value` attribute is required.</span></span> <span data-ttu-id="bcc20-126">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="bcc20-126">The URI is case-sensitive.</span></span>|  
|`<clear>`|<span data-ttu-id="bcc20-127">Очищает коллекцию audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bcc20-127">Clears the audienceUris collection.</span></span> <span data-ttu-id="bcc20-128">Все идентификаторы удаляются из коллекции.</span><span class="sxs-lookup"><span data-stu-id="bcc20-128">All identifiers are removed from the collection.</span></span>|  
|`<remove value=xs:string>`|<span data-ttu-id="bcc20-129">Удаляет URI, указанный `value` атрибутом из коллекции audienceUris.</span><span class="sxs-lookup"><span data-stu-id="bcc20-129">Removes the URI specified by the `value` attribute from the audienceUris collection.</span></span> <span data-ttu-id="bcc20-130">Атрибут `value` является обязательным.</span><span class="sxs-lookup"><span data-stu-id="bcc20-130">The `value` attribute is required.</span></span> <span data-ttu-id="bcc20-131">В URI учитывается регистр.</span><span class="sxs-lookup"><span data-stu-id="bcc20-131">The URI is case-sensitive.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bcc20-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bcc20-132">Parent Elements</span></span>  
  
|<span data-ttu-id="bcc20-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="bcc20-133">Element</span></span>|<span data-ttu-id="bcc20-134">Описание</span><span class="sxs-lookup"><span data-stu-id="bcc20-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bcc20-135">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="bcc20-135">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="bcc20-136">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="bcc20-136">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bcc20-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="bcc20-137">Remarks</span></span>  
 <span data-ttu-id="bcc20-138">По умолчанию коллекция пуста; Используйте `<add>`элементы `<clear>`, и`<remove>` для изменения коллекции.</span><span class="sxs-lookup"><span data-stu-id="bcc20-138">By default, the collection is empty; use `<add>`, `<clear>`, and `<remove>` elements to modify the collection.</span></span> <span data-ttu-id="bcc20-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>объекты <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> и используют значения в коллекции URI аудитории для настройки любых допустимых ограничений URI аудитории в <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> объектах.</span><span class="sxs-lookup"><span data-stu-id="bcc20-139"><xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> and <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> objects use the values in the audience URI collection to configure any allowed audience URI restrictions in <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> objects.</span></span>  
  
 <span data-ttu-id="bcc20-140">`<audienceUris>` Элемент представлен<xref:System.IdentityModel.Configuration.AudienceUriElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="bcc20-140">The `<audienceUris>` element is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElementCollection> class.</span></span> <span data-ttu-id="bcc20-141">Отдельный URI, добавленный в коллекцию, представлен <xref:System.IdentityModel.Configuration.AudienceUriElement> классом.</span><span class="sxs-lookup"><span data-stu-id="bcc20-141">An individual URI added to the collection is represented by the <xref:System.IdentityModel.Configuration.AudienceUriElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bcc20-142">Использование `<audienceUris>` элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="bcc20-142">The use of the `<audienceUris>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="bcc20-143">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="bcc20-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcc20-144">Пример</span><span class="sxs-lookup"><span data-stu-id="bcc20-144">Example</span></span>  
 <span data-ttu-id="bcc20-145">В следующем коде XML показано, как настроить допустимые URI аудитории для приложения.</span><span class="sxs-lookup"><span data-stu-id="bcc20-145">The following XML shows how to configure the acceptable audience URIs for an application.</span></span> <span data-ttu-id="bcc20-146">В этом примере настраивается один универсальный код ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="bcc20-146">This example configures a single URI.</span></span> <span data-ttu-id="bcc20-147">Маркеры, областью которых является этот URI, будут приняты, все остальные будут отклонены.</span><span class="sxs-lookup"><span data-stu-id="bcc20-147">Tokens scoped for this URI will be accepted, all others will be rejected.</span></span>  
  
```xml  
<audienceUris>  
  <add value="http://localhost:19851/"/>  
</audienceUris>  
```
