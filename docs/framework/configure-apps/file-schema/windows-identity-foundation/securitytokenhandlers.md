---
title: '&lt;securityTokenHandlers&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3151ec3511bca598e5aaabc72b821bdd3aed0b7b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltsecuritytokenhandlersgt"></a><span data-ttu-id="bc968-102">&lt;securityTokenHandlers&gt;</span><span class="sxs-lookup"><span data-stu-id="bc968-102">&lt;securityTokenHandlers&gt;</span></span>
<span data-ttu-id="bc968-103">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="bc968-103">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="bc968-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="bc968-104">\<system.identityModel></span></span>  
<span data-ttu-id="bc968-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="bc968-105">\<identityConfiguration></span></span>  
<span data-ttu-id="bc968-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="bc968-106">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc968-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc968-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc968-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bc968-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bc968-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc968-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc968-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc968-110">Attributes</span></span>  
  
|<span data-ttu-id="bc968-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bc968-111">Attribute</span></span>|<span data-ttu-id="bc968-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bc968-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bc968-113">имя</span><span class="sxs-lookup"><span data-stu-id="bc968-113">name</span></span>|<span data-ttu-id="bc968-114">Указывает имя коллекции обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="bc968-114">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="bc968-115">Только значения, распознаваемые платформа: «ActAs» и «OnBehalfOf».</span><span class="sxs-lookup"><span data-stu-id="bc968-115">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="bc968-116">Если обработчик маркеров коллекций указаны с помощью любого из этих имен, коллекции будет использоваться при обработке ActAs "или" OnBehalfOf маркеров соответственно.</span><span class="sxs-lookup"><span data-stu-id="bc968-116">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc968-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc968-117">Child Elements</span></span>  
  
|<span data-ttu-id="bc968-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc968-118">Element</span></span>|<span data-ttu-id="bc968-119">Описание</span><span class="sxs-lookup"><span data-stu-id="bc968-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc968-120">\<add></span><span class="sxs-lookup"><span data-stu-id="bc968-120">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="bc968-121">Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="bc968-121">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="bc968-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="bc968-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md)|<span data-ttu-id="bc968-123">Удаляет все обработчики маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="bc968-123">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="bc968-124">\<remove></span><span class="sxs-lookup"><span data-stu-id="bc968-124">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md)|<span data-ttu-id="bc968-125">Удаляет обработчик маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="bc968-125">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="bc968-126">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="bc968-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="bc968-127">Обеспечивает настройку для коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="bc968-127">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc968-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc968-128">Parent Elements</span></span>  
  
|<span data-ttu-id="bc968-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc968-129">Element</span></span>|<span data-ttu-id="bc968-130">Описание</span><span class="sxs-lookup"><span data-stu-id="bc968-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc968-131">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="bc968-131">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="bc968-132">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="bc968-132">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc968-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc968-133">Remarks</span></span>  
 <span data-ttu-id="bc968-134">Можно указать одну или несколько именованных коллекций обработчиков токенов безопасности в конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="bc968-134">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="bc968-135">Можно указать имя для коллекции с помощью `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="bc968-135">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="bc968-136">Только имена, что маркеры framework являются «ActAs» и «OnBehalfOf».</span><span class="sxs-lookup"><span data-stu-id="bc968-136">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="bc968-137">Если в эти коллекции существуют обработчики, они используются службой маркеров безопасности (STS) вместо обработчики по умолчанию при обработке `ActAs` и `OnBehalfOf` маркеров.</span><span class="sxs-lookup"><span data-stu-id="bc968-137">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="bc968-138">По умолчанию коллекция заполняется следующие типы обработчиков: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="bc968-138">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="bc968-139">Коллекции можно изменить с помощью `<add>`, `<remove>`, и `<clear>` элементы.</span><span class="sxs-lookup"><span data-stu-id="bc968-139">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="bc968-140">Необходимо убедиться, что только один обработчик любого конкретного типа существует в коллекции.</span><span class="sxs-lookup"><span data-stu-id="bc968-140">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="bc968-141">Например, если вы наследуете обработчик из <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, либо обработчик или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> может быть настроен в одной коллекции, но не оба.</span><span class="sxs-lookup"><span data-stu-id="bc968-141">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="bc968-142">Используйте `<securityTokenHandlerConfiguration>` элемента, чтобы указать параметры конфигурации для обработчиков в коллекции.</span><span class="sxs-lookup"><span data-stu-id="bc968-142">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="bc968-143">Параметры, заданные с помощью этого элемента переопределить указанные службы с помощью [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="bc968-143">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="bc968-144">Обработчики (включая некоторые типы встроенных обработчиков) может поддерживать дополнительные конфигурации с помощью дочерний элемент элемента `<add>` элемент.</span><span class="sxs-lookup"><span data-stu-id="bc968-144">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="bc968-145">Параметры, заданные в обработчик переопределить эквивалентные настройки, заданные на коллекции или службы.</span><span class="sxs-lookup"><span data-stu-id="bc968-145">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
