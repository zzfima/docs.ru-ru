---
title: '&lt;add&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: d863a0fc2b575aceef12370a57f7f7807261cb5a
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltaddgt"></a><span data-ttu-id="1bfc6-102">&lt;add&gt;</span><span class="sxs-lookup"><span data-stu-id="1bfc6-102">&lt;add&gt;</span></span>
<span data-ttu-id="1bfc6-103">Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-103">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="1bfc6-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="1bfc6-104">\<system.identityModel></span></span>  
<span data-ttu-id="1bfc6-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="1bfc6-105">\<identityConfiguration></span></span>  
<span data-ttu-id="1bfc6-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="1bfc6-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="1bfc6-107">\<add></span><span class="sxs-lookup"><span data-stu-id="1bfc6-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1bfc6-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bfc6-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type=xs:string>  
        <optionalConfigurationElement>  
        </optionalConfigurationElement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1bfc6-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1bfc6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1bfc6-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1bfc6-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1bfc6-111">Attributes</span></span>  
  
|<span data-ttu-id="1bfc6-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1bfc6-112">Attribute</span></span>|<span data-ttu-id="1bfc6-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1bfc6-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1bfc6-114">type</span><span class="sxs-lookup"><span data-stu-id="1bfc6-114">type</span></span>|<span data-ttu-id="1bfc6-115">Имя типа CLR обработчик маркеров для добавления.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="1bfc6-116">Дополнительные сведения о способах указания `type` см. в разделе [ссылок на пользовательские типы](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span><span class="sxs-lookup"><span data-stu-id="1bfc6-116">For more information about how to specify the `type` attribute, see [Custom Type References](http://msdn.microsoft.com/library/7286d2e3-c63d-49fd-abdc-ce2705f22c24).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1bfc6-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1bfc6-117">Child Elements</span></span>  
  
|<span data-ttu-id="1bfc6-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="1bfc6-118">Element</span></span>|<span data-ttu-id="1bfc6-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="1bfc6-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bfc6-120">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="1bfc6-120">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="1bfc6-121">Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса или производного класса от любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="1bfc6-122">\<sessionTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="1bfc6-122">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="1bfc6-123">Обеспечивает настройку для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="1bfc6-124">\<userNameSecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="1bfc6-124">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="1bfc6-125">Обеспечивает настройку для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="1bfc6-126">\<x509SecurityTokenHandlerRequirement></span><span class="sxs-lookup"><span data-stu-id="1bfc6-126">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="1bfc6-127">Предоставляет дополнительной конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1bfc6-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1bfc6-128">Parent Elements</span></span>  
  
|<span data-ttu-id="1bfc6-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="1bfc6-129">Element</span></span>|<span data-ttu-id="1bfc6-130">Описание:</span><span class="sxs-lookup"><span data-stu-id="1bfc6-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1bfc6-131">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="1bfc6-131">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="1bfc6-132">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1bfc6-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bfc6-133">Remarks</span></span>  
 <span data-ttu-id="1bfc6-134">`<add>` Элемент может занять один дочерний элемент, указывающий конфигурацию для обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="1bfc6-135">Это зависит от того, является ли ссылка на класс обработчика через `type` атрибут `<add>` обеспечивает поддержку этой функции.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="1bfc6-136">Классы обработчика токенов, которые поддерживают эту функцию должен предоставлять конструктор, принимающий <xref:System.Xml.XmlElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="1bfc6-137">Несколько классов обработчика токенов встроенных средств безопасности предоставляет эту функцию.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="1bfc6-138">Эти классы являются <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1bfc6-139">Коллекция обработчика токенов может содержать только один обработчик любого конкретного типа.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="1bfc6-140">Это означает, например, что если вы хотите добавить обработчик, который является производным от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса в коллекцию, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который по умолчанию присутствует, из коллекции.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="1bfc6-141">Можно использовать [ \<удалить >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) элемента, который требуется удалить из коллекции или использовать один обработчик [ \<снимите >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) элемента, который требуется удалить из коллекции все обработчики.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-141">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="1bfc6-142">Эквивалентные параметры, заданные в коллекцию обработчиков токенов в разделе переопределить параметры, заданные в обработчик [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент и теми, которые указаны на уровне службы в группе [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1bfc6-143">Пример</span><span class="sxs-lookup"><span data-stu-id="1bfc6-143">Example</span></span>  
 <span data-ttu-id="1bfc6-144">Следующий XML-КОДЕ показано использование `<add>` и `<remove>` элементов для замены токенов обработчик сеанса по умолчанию обработчик маркеров пользовательского сеанса.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="1bfc6-145">XML-код будет браться из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="1bfc6-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
