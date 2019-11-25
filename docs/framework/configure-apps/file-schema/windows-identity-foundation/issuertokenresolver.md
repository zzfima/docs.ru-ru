---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 451750a1facd9a886b53427a8d54580d1a939fa5
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73968513"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="e5431-101">\<Иссуертокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="e5431-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="e5431-102">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e5431-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e5431-103">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5431-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
<span data-ttu-id="e5431-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e5431-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e5431-105">&nbsp;&nbsp;[ **\<System. identityModel >** ](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e5431-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e5431-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e5431-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e5431-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e5431-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e5431-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e5431-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="e5431-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<иссуертокенресолвер >**</span><span class="sxs-lookup"><span data-stu-id="e5431-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5431-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5431-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5431-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5431-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e5431-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5431-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5431-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5431-113">Attributes</span></span>  
  
|<span data-ttu-id="e5431-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e5431-114">Attribute</span></span>|<span data-ttu-id="e5431-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e5431-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e5431-116">тип</span><span class="sxs-lookup"><span data-stu-id="e5431-116">type</span></span>|<span data-ttu-id="e5431-117">Указывает тип сопоставителя маркеров издателя.</span><span class="sxs-lookup"><span data-stu-id="e5431-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e5431-118">Должен быть либо классом <xref:System.IdentityModel.Tokens.IssuerTokenResolver>, либо типом, производным от класса <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e5431-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e5431-119">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e5431-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5431-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5431-120">Child Elements</span></span>  
 <span data-ttu-id="e5431-121">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="e5431-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e5431-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5431-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e5431-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5431-123">Element</span></span>|<span data-ttu-id="e5431-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e5431-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e5431-125">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="e5431-125">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e5431-126">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e5431-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5431-127">Заметки</span><span class="sxs-lookup"><span data-stu-id="e5431-127">Remarks</span></span>  
 <span data-ttu-id="e5431-128">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="e5431-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e5431-129">Он используется для получения криптографического материала, используемого для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="e5431-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e5431-130">Необходимо указать атрибут `type`.</span><span class="sxs-lookup"><span data-stu-id="e5431-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="e5431-131">Указанный тип может быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver>, либо настраиваемого типа, производного от класса <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e5431-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e5431-132">Некоторые обработчики маркеров позволяют задавать параметры сопоставителя маркеров издателя в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e5431-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e5431-133">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e5431-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5431-134">Указание элемента `<issuerTokenResolver>` в качестве дочернего элемента элемента [\<identityConfiguration >](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="e5431-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e5431-135">Параметры элемента `<securityTokenHandlerConfiguration>` переопределяют их в элементе `<identityConfiguration>`.</span><span class="sxs-lookup"><span data-stu-id="e5431-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5431-136">Пример</span><span class="sxs-lookup"><span data-stu-id="e5431-136">Example</span></span>  
 <span data-ttu-id="e5431-137">В следующем коде XML показана конфигурация для сопоставителя маркеров издателя, основанного на пользовательском классе, производном от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e5431-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e5431-138">Сопоставитель токенов поддерживает словарь пар ключей аудитории, которые инициализируются из настраиваемого элемента конфигурации (`<AddAudienceKeyPair>`), определенного для класса.</span><span class="sxs-lookup"><span data-stu-id="e5431-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e5431-139">Класс переопределяет метод <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> для обработки этого элемента.</span><span class="sxs-lookup"><span data-stu-id="e5431-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e5431-140">Переопределение показано в следующем примере. Однако методы, которые он вызывает, не отображаются для краткости.</span><span class="sxs-lookup"><span data-stu-id="e5431-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e5431-141">Полный пример см. в примере `CustomToken`.</span><span class="sxs-lookup"><span data-stu-id="e5431-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e5431-142">Пример</span><span class="sxs-lookup"><span data-stu-id="e5431-142">Example</span></span>
  
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
  
## <a name="see-also"></a><span data-ttu-id="e5431-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e5431-143">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
