---
title: <add>
ms.date: 03/30/2017
ms.assetid: 4712a888-f154-4395-8887-ef14a88a6497
author: BrucePerlerMS
ms.openlocfilehash: 932e8452542ace66824fba1262694c220ce88676
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252189"
---
# <a name="add"></a><span data-ttu-id="167e1-101">\<add></span><span class="sxs-lookup"><span data-stu-id="167e1-101">\<add></span></span>
<span data-ttu-id="167e1-102">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="167e1-102">Adds the specified security token handler to the token handler collection.</span></span>  
  
<span data-ttu-id="167e1-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="167e1-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="167e1-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="167e1-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="167e1-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="167e1-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="167e1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="167e1-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="167e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="167e1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="167e1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="167e1-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="167e1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="167e1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="167e1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="167e1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="167e1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="167e1-111">Attributes</span></span>  
  
|<span data-ttu-id="167e1-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="167e1-112">Attribute</span></span>|<span data-ttu-id="167e1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="167e1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="167e1-114">type</span><span class="sxs-lookup"><span data-stu-id="167e1-114">type</span></span>|<span data-ttu-id="167e1-115">Имя типа CLR обработчика токенов, который необходимо добавить.</span><span class="sxs-lookup"><span data-stu-id="167e1-115">The CLR type name of the token handler to be added.</span></span> <span data-ttu-id="167e1-116">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span><span class="sxs-lookup"><span data-stu-id="167e1-116">For more information about how to specify the `type` attribute, see [Custom Type References](https://docs.microsoft.com/previous-versions/windows-identity-foundation/gg638728(v=msdn.10)#custom-type-references).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="167e1-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="167e1-117">Child Elements</span></span>  
  
|<span data-ttu-id="167e1-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="167e1-118">Element</span></span>|<span data-ttu-id="167e1-119">Описание</span><span class="sxs-lookup"><span data-stu-id="167e1-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="167e1-120">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="167e1-120">\<samlSecurityTokenRequirement></span></span>](samlsecuritytokenrequirement.md)|<span data-ttu-id="167e1-121">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="167e1-121">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span>|  
|[<span data-ttu-id="167e1-122">\<Сессионтокенрекуиремент ></span><span class="sxs-lookup"><span data-stu-id="167e1-122">\<sessionTokenRequirement></span></span>](sessiontokenrequirement.md)|<span data-ttu-id="167e1-123">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="167e1-123">Provides configuration for the <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="167e1-124">\<Усернамесекурититокенхандлеррекуиремент ></span><span class="sxs-lookup"><span data-stu-id="167e1-124">\<userNameSecurityTokenHandlerRequirement></span></span>](usernamesecuritytokenhandlerrequirement.md)|<span data-ttu-id="167e1-125">Предоставляет конфигурацию для <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="167e1-125">Provides configuration for the <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler> class or derived classes.</span></span>|  
|[<span data-ttu-id="167e1-126">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="167e1-126">\<x509SecurityTokenHandlerRequirement></span></span>](x509securitytokenhandlerrequirement.md)|<span data-ttu-id="167e1-127">Предоставляет необязательную конфигурацию для <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="167e1-127">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="167e1-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="167e1-128">Parent Elements</span></span>  
  
|<span data-ttu-id="167e1-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="167e1-129">Element</span></span>|<span data-ttu-id="167e1-130">Описание</span><span class="sxs-lookup"><span data-stu-id="167e1-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="167e1-131">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="167e1-131">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="167e1-132">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="167e1-132">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="167e1-133">Примечания</span><span class="sxs-lookup"><span data-stu-id="167e1-133">Remarks</span></span>  
 <span data-ttu-id="167e1-134">`<add>` Элемент может принимать один дочерний элемент, указывающий конфигурацию для обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="167e1-134">The `<add>` element can take a single child element that specifies the configuration for the token handler.</span></span> <span data-ttu-id="167e1-135">Это зависит от того, поддерживает ли эта функция класс обработчика, на `<add>` который ссылается `type` атрибут элемента.</span><span class="sxs-lookup"><span data-stu-id="167e1-135">This is dependent on whether the handler class referenced through the `type` attribute of the `<add>` element provides support for this feature.</span></span> <span data-ttu-id="167e1-136">Классы обработчиков маркеров, которые предоставляют эту функцию, должны предоставлять конструктор, <xref:System.Xml.XmlElement> принимающий объект.</span><span class="sxs-lookup"><span data-stu-id="167e1-136">Token handler classes that provide this feature must expose a constructor that takes an <xref:System.Xml.XmlElement> object.</span></span>  
  
```  
public class CustomTokenHandler : Microsoft.IdentityModel.Tokens.SecurityTokenHandler  
{  
    public CustomTokenHandler( XmlElement customConfig )  
    {  
    }  
}  
```  
  
 <span data-ttu-id="167e1-137">Некоторые из встроенных классов обработчиков маркеров безопасности предоставляют эту функцию.</span><span class="sxs-lookup"><span data-stu-id="167e1-137">Several of the built-in security token handler classes do provide this functionality.</span></span> <span data-ttu-id="167e1-138">Эти классы: <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> ,<xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>,, и<xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>. <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler></span><span class="sxs-lookup"><span data-stu-id="167e1-138">These classes are <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, <xref:System.IdentityModel.Services.Tokens.MembershipUserNameSecurityTokenHandler>, <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler>, and <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="167e1-139">Коллекция обработчиков маркеров может содержать только один обработчик любого заданного типа.</span><span class="sxs-lookup"><span data-stu-id="167e1-139">The token handler collection can only contain a single handler of any given type.</span></span> <span data-ttu-id="167e1-140">Это означает, например, что если требуется добавить обработчик, производный от <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, в коллекцию, необходимо сначала удалить объект <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, который существует по умолчанию, из коллекции.</span><span class="sxs-lookup"><span data-stu-id="167e1-140">This means, for example, that if you want to add a handler that is derived from the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class to the collection, you must first remove the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>, which is present by default, from the collection.</span></span> <span data-ttu-id="167e1-141">Можно использовать [ \<элемент remove >](remove.md) для удаления одного обработчика из [ \<](clear.md) коллекции или использовать элемент clear > для удаления всех обработчиков из коллекции.</span><span class="sxs-lookup"><span data-stu-id="167e1-141">You can use the [\<remove>](remove.md) element to remove a single handler from the collection or use the [\<clear>](clear.md) element to remove all handlers from the collection.</span></span>  
  
 <span data-ttu-id="167e1-142">Параметры, заданные для обработчика, переопределяют эквивалентные параметры, указанные в коллекции обработчика маркеров в [ \<элементе > секурититокенхандлерконфигуратион](securitytokenhandlerconfiguration.md) , и те, которые указаны на уровне службы в разделе [ \< Элемент > identityConfiguration](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="167e1-142">Settings specified on a handler override equivalent settings specified on the token handler collection under the [\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md) element and those specified at the service-level under the [\<identityConfiguration>](identityconfiguration.md) element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="167e1-143">Пример</span><span class="sxs-lookup"><span data-stu-id="167e1-143">Example</span></span>  
 <span data-ttu-id="167e1-144">В следующем коде XML показано использование `<add>` элементов и `<remove>` для замены обработчика токена сеанса по умолчанию обработчиком пользовательского маркера сеанса.</span><span class="sxs-lookup"><span data-stu-id="167e1-144">The following XML shows the use of the `<add>` and `<remove>` elements to replace the default session token handler with a custom session token handler.</span></span> <span data-ttu-id="167e1-145">XML взят из `ClaimsAwareWebFarm` примера.</span><span class="sxs-lookup"><span data-stu-id="167e1-145">The XML is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<securityTokenHandlers>  
  <remove type="System.IdentityModel.Tokens.SessionSecurityTokenHandler, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
  <add type="System.IdentityModel.Services.Tokens.MachineKeySessionSecurityTokenHandler, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />  
</securityTokenHandlers>  
```
