---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 67d7e0aa5b6b05bfe8b17a1b1efebb1fbddbb0eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152675"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="1ba80-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="1ba80-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="1ba80-102">Регистрирует токен-решателя эмитента, который используется обработчиками в коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="1ba80-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="1ba80-103">Разрешители маркеров эмитента используются для разрешения маркера подписи на входящих токенах и сообщениях.</span><span class="sxs-lookup"><span data-stu-id="1ba80-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="1ba80-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1ba80-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1ba80-105">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="1ba80-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="1ba80-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="1ba80-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="1ba80-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="1ba80-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="1ba80-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenhandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="1ba80-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="1ba80-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span><span class="sxs-lookup"><span data-stu-id="1ba80-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba80-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ba80-110">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1ba80-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1ba80-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1ba80-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1ba80-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1ba80-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1ba80-113">Attributes</span></span>  
  
|<span data-ttu-id="1ba80-114">attribute</span><span class="sxs-lookup"><span data-stu-id="1ba80-114">Attribute</span></span>|<span data-ttu-id="1ba80-115">Описание</span><span class="sxs-lookup"><span data-stu-id="1ba80-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ba80-116">type</span><span class="sxs-lookup"><span data-stu-id="1ba80-116">type</span></span>|<span data-ttu-id="1ba80-117">Определяет тип разрешительного маркера эмитента.</span><span class="sxs-lookup"><span data-stu-id="1ba80-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="1ba80-118">Должен быть <xref:System.IdentityModel.Tokens.IssuerTokenResolver> либо класс, либо тип, <xref:System.IdentityModel.Tokens.IssuerTokenResolver> который вытекает из класса.</span><span class="sxs-lookup"><span data-stu-id="1ba80-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="1ba80-119">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="1ba80-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1ba80-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1ba80-120">Child Elements</span></span>  
 <span data-ttu-id="1ba80-121">None</span><span class="sxs-lookup"><span data-stu-id="1ba80-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1ba80-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1ba80-122">Parent Elements</span></span>  
  
|<span data-ttu-id="1ba80-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="1ba80-123">Element</span></span>|<span data-ttu-id="1ba80-124">Описание</span><span class="sxs-lookup"><span data-stu-id="1ba80-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1ba80-125">\<securityTokenhandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="1ba80-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="1ba80-126">Обеспечивает конфигурацию для сбора обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1ba80-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ba80-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="1ba80-127">Remarks</span></span>  
 <span data-ttu-id="1ba80-128">Разрешители маркеров эмитента используются для разрешения маркера подписи на входящих токенах и сообщениях.</span><span class="sxs-lookup"><span data-stu-id="1ba80-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="1ba80-129">Он используется для извлечения криптографического материала, который используется для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="1ba80-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="1ba80-130">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="1ba80-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="1ba80-131">Указанный тип может <xref:System.IdentityModel.Tokens.IssuerTokenResolver> быть либо или пользовательским <xref:System.IdentityModel.Tokens.IssuerTokenResolver> типом, который вытекает из класса.</span><span class="sxs-lookup"><span data-stu-id="1ba80-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="1ba80-132">Некоторые обработчики токенов позволяют указывать настройки маркера эмитента в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1ba80-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="1ba80-133">Настройки отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="1ba80-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1ba80-134">Определение элемента `<issuerTokenResolver>` в качестве элемента ребенка [ \<идентификационных конфигураций>](identityconfiguration.md) элемента было изуродовано, но по-прежнему поддерживается для обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="1ba80-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="1ba80-135">Настройки элемента `<securityTokenHandlerConfiguration>` переопределяют элементы на элементе. `<identityConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="1ba80-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ba80-136">Пример</span><span class="sxs-lookup"><span data-stu-id="1ba80-136">Example</span></span>  
 <span data-ttu-id="1ba80-137">В следующем XML отображается конфигурация для разрешительного маркера эмитента, <xref:System.IdentityModel.Tokens.IssuerTokenResolver>основанная на пользовательском классе, который вытекает из.</span><span class="sxs-lookup"><span data-stu-id="1ba80-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="1ba80-138">Разрешители токенов поддерживают словарь пар ключей аудитории, который инициализирован из пользовательского элемента конфигурации (),`<AddAudienceKeyPair>`определенного для класса.</span><span class="sxs-lookup"><span data-stu-id="1ba80-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="1ba80-139">Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод обработки этого элемента.</span><span class="sxs-lookup"><span data-stu-id="1ba80-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="1ba80-140">Переопределение отображается в следующем примере; однако методы, которые он называет, не отображаются для краткости.</span><span class="sxs-lookup"><span data-stu-id="1ba80-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="1ba80-141">Для полного примера `CustomToken` смотрите пример.</span><span class="sxs-lookup"><span data-stu-id="1ba80-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="1ba80-142">Пример</span><span class="sxs-lookup"><span data-stu-id="1ba80-142">Example</span></span>
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a><span data-ttu-id="1ba80-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ba80-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
