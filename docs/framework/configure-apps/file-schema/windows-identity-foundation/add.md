---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 83ba51cbbd5100bf7412f9914a270cac88f7faa1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973805"
---
# <a name="add"></a><span data-ttu-id="d67c2-101">\<add></span><span class="sxs-lookup"><span data-stu-id="d67c2-101">\<add></span></span>
<span data-ttu-id="d67c2-102">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="d67c2-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="d67c2-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d67c2-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d67c2-104">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="d67c2-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="d67c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="d67c2-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="d67c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="d67c2-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="d67c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<добавить >**</span><span class="sxs-lookup"><span data-stu-id="d67c2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d67c2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d67c2-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d67c2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d67c2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d67c2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d67c2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d67c2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d67c2-111">Attributes</span></span>  
  
|<span data-ttu-id="d67c2-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d67c2-112">Attribute</span></span>|<span data-ttu-id="d67c2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="d67c2-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d67c2-114">тип</span><span class="sxs-lookup"><span data-stu-id="d67c2-114">type</span></span>|<span data-ttu-id="d67c2-115">Имя типа CLR обработчика токенов, который необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="d67c2-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="d67c2-116">Дополнительные сведения об указании атрибута `type` см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="d67c2-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d67c2-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d67c2-117">Child Elements</span></span>  
  
|<span data-ttu-id="d67c2-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d67c2-118">Element</span></span>|<span data-ttu-id="d67c2-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d67c2-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d67c2-120">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="d67c2-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="d67c2-121">Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="d67c2-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="d67c2-122">\<Сессионтокенрекуиремент ></span><span class="sxs-lookup"><span data-stu-id="d67c2-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="d67c2-123">Предоставляет конфигурацию для класса <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> или производных классов.</span><span class="sxs-lookup"><span data-stu-id="d67c2-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="d67c2-124">\<Усернамесекурититокенхандлеррекуиремент ></span><span class="sxs-lookup"><span data-stu-id="d67c2-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="d67c2-125">Предоставляет конфигурацию для класса <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> или производных классов.</span><span class="sxs-lookup"><span data-stu-id="d67c2-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="d67c2-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="d67c2-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="d67c2-127">Предоставляет необязательную конфигурацию для класса <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> или производных классов.</span><span class="sxs-lookup"><span data-stu-id="d67c2-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d67c2-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d67c2-128">Parent Elements</span></span>  
  
|<span data-ttu-id="d67c2-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="d67c2-129">Element</span></span>|<span data-ttu-id="d67c2-130">Описание</span><span class="sxs-lookup"><span data-stu-id="d67c2-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d67c2-131">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="d67c2-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="d67c2-132">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="d67c2-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d67c2-133">Заметки</span><span class="sxs-lookup"><span data-stu-id="d67c2-133">Remarks</span></span>  
 <span data-ttu-id="d67c2-134">Элемент `<add>` может принимать один дочерний элемент, указывающий конфигурацию для обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="d67c2-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="d67c2-135">Это зависит от того, поддерживает ли этот компонент класс обработчика, на который ссылается атрибут `type` элемента `<add>`.</span><span class="sxs-lookup"><span data-stu-id="d67c2-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="d67c2-136">Классы обработчиков маркеров, которые предоставляют эту функцию, должны предоставлять конструктор, принимающий объект <xref:System.Xml.XmlElement>.</span><span class="sxs-lookup"><span data-stu-id="d67c2-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  

```csharp  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="d67c2-137">Некоторые из встроенных классов обработчиков маркеров безопасности предоставляют эту функцию.</span><span class="sxs-lookup"><span data-stu-id="d67c2-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="d67c2-138">Этими классами являются <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>и <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="d67c2-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d67c2-139">Коллекция обработчиков маркеров может содержать только один обработчик любого заданного типа.</span><span class="sxs-lookup"><span data-stu-id="d67c2-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="d67c2-140">Это означает, например, что если нужно добавить в коллекцию обработчик, производный от класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, необходимо сначала удалить <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который существует по умолчанию, из коллекции.</span><span class="sxs-lookup"><span data-stu-id="d67c2-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="d67c2-141">Можно использовать элемент [\<Remove >](remove.md) для удаления одного обработчика из коллекции или использовать [\<Clear >](clear.md) для удаления всех обработчиков из коллекции.</span><span class="sxs-lookup"><span data-stu-id="d67c2-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="d67c2-142">Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции обработчика маркеров в элементе [\<секурититокенхандлерконфигуратион >](securitytokenhandlerconfiguration.md) , и те, которые указаны на уровне службы в элементе [\<identityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="d67c2-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d67c2-143">Пример</span><span class="sxs-lookup"><span data-stu-id="d67c2-143">Example</span></span>  
 <span data-ttu-id="d67c2-144">В следующем XML-коде показано использование элементов `<add>` и `<remove>` для замены обработчика токенов сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="d67c2-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="d67c2-145">XML взят из примера `ClaimsAwareWebFarm`.</span><span class="sxs-lookup"><span data-stu-id="d67c2-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
