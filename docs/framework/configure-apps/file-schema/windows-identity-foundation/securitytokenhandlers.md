---
title: <securityTokenHandlers>
ms.date: 03/30/2017
ms.assetid: f11a631d-4094-4e11-bb03-4ede74b30281
author: BrucePerlerMS
ms.openlocfilehash: 678e5c705181c55257b1ddb853690ada60ecd17a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942461"
---
# <a name="securitytokenhandlers"></a><span data-ttu-id="3fe95-101">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3fe95-101">\<securityTokenHandlers></span></span>
<span data-ttu-id="3fe95-102">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="3fe95-102">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>  
  
 <span data-ttu-id="3fe95-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="3fe95-103">\<system.identityModel></span></span>  
<span data-ttu-id="3fe95-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3fe95-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3fe95-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3fe95-105">\<securityTokenHandlers></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fe95-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3fe95-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3fe95-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3fe95-107">Attributes and Elements</span></span>  
 <span data-ttu-id="3fe95-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3fe95-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3fe95-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3fe95-109">Attributes</span></span>  
  
|<span data-ttu-id="3fe95-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3fe95-110">Attribute</span></span>|<span data-ttu-id="3fe95-111">Описание</span><span class="sxs-lookup"><span data-stu-id="3fe95-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3fe95-112">имя</span><span class="sxs-lookup"><span data-stu-id="3fe95-112">name</span></span>|<span data-ttu-id="3fe95-113">Указывает имя коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3fe95-113">Specifies the name of a token handler collection.</span></span> <span data-ttu-id="3fe95-114">Платформа принимает только те значения, которые распознаются платформой: "ActAs" и "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="3fe95-114">The only values recognized by the framework are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="3fe95-115">Если коллекции обработчиков маркеров указаны с одним из этих имен, коллекция будет использоваться при обработке маркеров ActAs или OnBehalfOf соответственно.</span><span class="sxs-lookup"><span data-stu-id="3fe95-115">If token handler collections are specified with either of these names, the collection will be used when processing ActAs or OnBehalfOf tokens respectively.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3fe95-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3fe95-116">Child Elements</span></span>  
  
|<span data-ttu-id="3fe95-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="3fe95-117">Element</span></span>|<span data-ttu-id="3fe95-118">Описание</span><span class="sxs-lookup"><span data-stu-id="3fe95-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fe95-119">\<add></span><span class="sxs-lookup"><span data-stu-id="3fe95-119">\<add></span></span>](add.md)|<span data-ttu-id="3fe95-120">Добавляет обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3fe95-120">Adds a security token handler to the token handler collection.</span></span>|  
|[<span data-ttu-id="3fe95-121">\<clear></span><span class="sxs-lookup"><span data-stu-id="3fe95-121">\<clear></span></span>](clear.md)|<span data-ttu-id="3fe95-122">Удаляет все обработчики маркеров безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3fe95-122">Clears all security token handlers from the token handler collection.</span></span>|  
|[<span data-ttu-id="3fe95-123">\<remove></span><span class="sxs-lookup"><span data-stu-id="3fe95-123">\<remove></span></span>](remove.md)|<span data-ttu-id="3fe95-124">Удаляет обработчик маркера безопасности из коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3fe95-124">Removes a security token handler from the token handler collection.</span></span>|  
|[<span data-ttu-id="3fe95-125">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="3fe95-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="3fe95-126">Предоставляет конфигурацию для коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3fe95-126">Provides configuration for the collection of token handlers.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3fe95-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3fe95-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3fe95-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="3fe95-128">Element</span></span>|<span data-ttu-id="3fe95-129">Описание</span><span class="sxs-lookup"><span data-stu-id="3fe95-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3fe95-130">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3fe95-130">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="3fe95-131">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="3fe95-131">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3fe95-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="3fe95-132">Remarks</span></span>  
 <span data-ttu-id="3fe95-133">В конфигурации службы можно указать одну или несколько именованных коллекций обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3fe95-133">You can specify one or more named collections of security token handlers in a service configuration.</span></span> <span data-ttu-id="3fe95-134">Имя коллекции можно указать с помощью `name` атрибута.</span><span class="sxs-lookup"><span data-stu-id="3fe95-134">You can specify a name for a collection by using the `name` attribute.</span></span> <span data-ttu-id="3fe95-135">Единственными именами, которые обрабатывает платформа, являются "ActAs" и "OnBehalfOf".</span><span class="sxs-lookup"><span data-stu-id="3fe95-135">The only names that the framework handles are "ActAs" and "OnBehalfOf".</span></span> <span data-ttu-id="3fe95-136">Если в этих коллекциях есть обработчики, они используются службой маркеров безопасности (STS) вместо обработчиков по умолчанию при обработке `ActAs` и `OnBehalfOf` токенах.</span><span class="sxs-lookup"><span data-stu-id="3fe95-136">If handlers exist in these collections, they are used by a security token service (STS) instead of the default handlers when processing `ActAs` and `OnBehalfOf` tokens.</span></span>  
  
 <span data-ttu-id="3fe95-137">По умолчанию <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>коллекция заполняется следующими типами обработчиков:, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler> <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler> <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, и <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="3fe95-137">By default, the collection is populated with the following handler types: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Tokens.KerberosSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.WindowsUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.RsaSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.EncryptedSecurityTokenHandler>.</span></span> <span data-ttu-id="3fe95-138">Коллекцию можно изменить с помощью `<add>`элементов, `<remove>`и `<clear>` .</span><span class="sxs-lookup"><span data-stu-id="3fe95-138">You can modify the collection by using the `<add>`, `<remove>`, and `<clear>` elements.</span></span> <span data-ttu-id="3fe95-139">Необходимо убедиться, что в коллекции существует только один обработчик любого определенного типа.</span><span class="sxs-lookup"><span data-stu-id="3fe95-139">You must ensure that only a single handler of any particular type exists in the collection.</span></span> <span data-ttu-id="3fe95-140">Например, если создать производный обработчик от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, то либо обработчик, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> либо может быть настроен в одной коллекции, но не в обоих.</span><span class="sxs-lookup"><span data-stu-id="3fe95-140">For example, if you derive a handler from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, either your handler or the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> may be configured in a single collection, but not both.</span></span>  
  
 <span data-ttu-id="3fe95-141">Используйте элемент `<securityTokenHandlerConfiguration>` , чтобы указать параметры конфигурации для обработчиков в коллекции.</span><span class="sxs-lookup"><span data-stu-id="3fe95-141">Use the `<securityTokenHandlerConfiguration>` element to specify configuration settings for the handlers in the collection.</span></span> <span data-ttu-id="3fe95-142">Параметры, заданные с помощью этого элемента, [ \<](identityconfiguration.md) переопределяют указанные в службе элементы с помощью элемента identityConfiguration >.</span><span class="sxs-lookup"><span data-stu-id="3fe95-142">Settings specified through this element override those specified on the service through the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="3fe95-143">Некоторые обработчики (включая несколько встроенных типов обработчиков) могут поддерживать дополнительную конфигурацию через дочерний элемент `<add>` элемента.</span><span class="sxs-lookup"><span data-stu-id="3fe95-143">Some handlers (including several of the built-in handler types) can support additional configuration through a child element of the `<add>` element.</span></span> <span data-ttu-id="3fe95-144">Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции или службе.</span><span class="sxs-lookup"><span data-stu-id="3fe95-144">Settings specified on a handler override equivalent settings specified on the collection or the service.</span></span>
