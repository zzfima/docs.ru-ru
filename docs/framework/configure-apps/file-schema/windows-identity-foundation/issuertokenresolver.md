---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: da591940910b16d42ef8ab1a05c4b244dbe543f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942630"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="9e240-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="9e240-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="9e240-102">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="9e240-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="9e240-103">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="9e240-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="9e240-104">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="9e240-104">\<system.identityModel></span></span>  
<span data-ttu-id="9e240-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9e240-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9e240-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="9e240-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="9e240-107">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="9e240-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="9e240-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="9e240-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e240-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e240-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e240-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e240-110">Attributes and Elements</span></span>  
 <span data-ttu-id="9e240-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9e240-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e240-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e240-112">Attributes</span></span>  
  
|<span data-ttu-id="9e240-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9e240-113">Attribute</span></span>|<span data-ttu-id="9e240-114">Описание</span><span class="sxs-lookup"><span data-stu-id="9e240-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9e240-115">type</span><span class="sxs-lookup"><span data-stu-id="9e240-115">type</span></span>|<span data-ttu-id="9e240-116">Указывает тип сопоставителя маркеров издателя.</span><span class="sxs-lookup"><span data-stu-id="9e240-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="9e240-117">Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> классом, либо типом, производным <xref:System.IdentityModel.Tokens.IssuerTokenResolver> от класса.</span><span class="sxs-lookup"><span data-stu-id="9e240-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="9e240-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="9e240-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e240-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e240-119">Child Elements</span></span>  
 <span data-ttu-id="9e240-120">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="9e240-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e240-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e240-121">Parent Elements</span></span>  
  
|<span data-ttu-id="9e240-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e240-122">Element</span></span>|<span data-ttu-id="9e240-123">Описание</span><span class="sxs-lookup"><span data-stu-id="9e240-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9e240-124">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="9e240-124">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="9e240-125">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="9e240-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e240-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e240-126">Remarks</span></span>  
 <span data-ttu-id="9e240-127">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="9e240-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="9e240-128">Он используется для получения криптографического материала, используемого для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="9e240-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="9e240-129">Необходимо указать `type` атрибут.</span><span class="sxs-lookup"><span data-stu-id="9e240-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="9e240-130">Указанный тип может быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> либо пользовательским типом, производным <xref:System.IdentityModel.Tokens.IssuerTokenResolver> от класса.</span><span class="sxs-lookup"><span data-stu-id="9e240-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="9e240-131">Некоторые обработчики маркеров позволяют задавать параметры сопоставителя маркеров издателя в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9e240-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="9e240-132">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="9e240-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e240-133">Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<issuerTokenResolver>`</span><span class="sxs-lookup"><span data-stu-id="9e240-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="9e240-134">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="9e240-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e240-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9e240-135">Example</span></span>  
 <span data-ttu-id="9e240-136">В следующем коде XML показана конфигурация для сопоставителя маркеров издателя, основанного на пользовательском классе, производном от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="9e240-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="9e240-137">Сопоставитель токенов поддерживает словарь пар ключей аудитории, которые инициализируются из настраиваемого элемента конфигурации (`<AddAudienceKeyPair>`), определенного для класса.</span><span class="sxs-lookup"><span data-stu-id="9e240-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="9e240-138">Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для обработки этого элемента.</span><span class="sxs-lookup"><span data-stu-id="9e240-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="9e240-139">Переопределение показано в следующем примере. Однако методы, которые он вызывает, не отображаются для краткости.</span><span class="sxs-lookup"><span data-stu-id="9e240-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="9e240-140">Полный пример см. в `CustomToken` примере.</span><span class="sxs-lookup"><span data-stu-id="9e240-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="9e240-141">Пример</span><span class="sxs-lookup"><span data-stu-id="9e240-141">Example</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="9e240-142">См. также</span><span class="sxs-lookup"><span data-stu-id="9e240-142">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
