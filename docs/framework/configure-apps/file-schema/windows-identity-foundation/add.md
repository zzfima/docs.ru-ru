---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 34643d10ef1ed2e87152e5013634e62859e0594e
ms.sourcegitcommit: 01ea420eaa4bf76d5fc47673294c8881379b3369
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2019
ms.locfileid: "55759487"
---
# <a name="add"></a><span data-ttu-id="c9187-101">\<add></span><span class="sxs-lookup"><span data-stu-id="c9187-101">\<add></span></span>
<span data-ttu-id="c9187-102">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="c9187-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
 <span data-ttu-id="c9187-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c9187-103">\<system.identityModel></span></span>  
<span data-ttu-id="c9187-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c9187-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c9187-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="c9187-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c9187-106">\<add></span><span class="sxs-lookup"><span data-stu-id="c9187-106">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9187-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9187-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c9187-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c9187-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c9187-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c9187-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c9187-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c9187-110">Attributes</span></span>  
  
|<span data-ttu-id="c9187-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c9187-111">Attribute</span></span>|<span data-ttu-id="c9187-112">Описание</span><span class="sxs-lookup"><span data-stu-id="c9187-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c9187-113">type</span><span class="sxs-lookup"><span data-stu-id="c9187-113">type</span></span>|<span data-ttu-id="c9187-114">Имя типа CLR обработчик токенов для добавления.</span><span class="sxs-lookup"><span data-stu-id="c9187-114">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="c9187-115">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="c9187-115">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c9187-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c9187-116">Child Elements</span></span>  
  
|<span data-ttu-id="c9187-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9187-117">Element</span></span>|<span data-ttu-id="c9187-118">Описание</span><span class="sxs-lookup"><span data-stu-id="c9187-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9187-119">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="c9187-119">\<samlSecurityTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/samlsecuritytokenrequirement.md)|<span data-ttu-id="c9187-120">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="c9187-120">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="c9187-121">\<sessionTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="c9187-121">\<sessionTokenRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessiontokenrequirement.md)|<span data-ttu-id="c9187-122">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="c9187-122">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="c9187-123">\<userNameSecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="c9187-123">\<userNameSecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="c9187-124">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="c9187-124">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="c9187-125">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="c9187-125">\<x509SecurityTokenHandlerRequirement></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/x509securitytokenhandlerrequirement.md)|<span data-ttu-id="c9187-126">Предоставляет вариант конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="c9187-126">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c9187-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c9187-127">Parent Elements</span></span>  
  
|<span data-ttu-id="c9187-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="c9187-128">Element</span></span>|<span data-ttu-id="c9187-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="c9187-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c9187-130">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="c9187-130">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="c9187-131">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="c9187-131">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9187-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="c9187-132">Remarks</span></span>  
 <span data-ttu-id="c9187-133">`<add>` Элемент может занять один дочерний элемент, указывающий конфигурацию для обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="c9187-133">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="c9187-134">Это зависит от того, является ли ссылка на класс обработчика через `type` атрибут `<add>` обеспечивает поддержку этой функции.</span><span class="sxs-lookup"><span data-stu-id="c9187-134">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="c9187-135">Классов для обработчиков маркеров, которые предоставляют этот компонент должен предоставлять конструктор, принимающий <xref:System.Xml.XmlElement> объекта.</span><span class="sxs-lookup"><span data-stu-id="c9187-135">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="c9187-136">Некоторые из классов для обработчиков маркеров встроенных средств безопасности предоставляет такой возможности.</span><span class="sxs-lookup"><span data-stu-id="c9187-136">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="c9187-137">Эти классы являются <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="c9187-137">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9187-138">Коллекция обработчиков токенов может содержать только один обработчик любого заданного типа.</span><span class="sxs-lookup"><span data-stu-id="c9187-138">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="c9187-139">Это означает, например, что если вы хотите добавить обработчик, который является производным от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса в коллекцию, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который присутствует по умолчанию из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9187-139">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="c9187-140">Можно использовать [ \<удалить >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) элемент нужно удалить из коллекции или использовать один обработчик [ \<снимите >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) элемент нужно удалить все обработчики из коллекции.</span><span class="sxs-lookup"><span data-stu-id="c9187-140">You can use the [\<remove>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/remove.md) element to remove a single handler from the collection or use the [\<clear>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="c9187-141">Настройки, указанные на обработчик переопределяют аналогичные параметры, указанные на коллекцию обработчиков токенов в разделе [ \<securityTokenHandlerConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) элемент и теми, которые указаны на уровне службы в разделе [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c9187-141">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c9187-142">Пример</span><span class="sxs-lookup"><span data-stu-id="c9187-142">Example</span></span>  
 <span data-ttu-id="c9187-143">Следующий код XML показывает использование `<add>` и `<remove>` элементов для замены маркера обработчик сеанса по умолчанию обработчик токенов пользовательского сеанса.</span><span class="sxs-lookup"><span data-stu-id="c9187-143">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="c9187-144">XML-код взят из `ClaimsAwareWebFarm` образца.</span><span class="sxs-lookup"><span data-stu-id="c9187-144">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
