---
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: a37935fa9302493c0ecaab0f56e1414d44637af6
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269228"
---
# <a name="issuertokenresolver"></a><span data-ttu-id="b9612-101">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b9612-101">\<issuerTokenResolver></span></span>
<span data-ttu-id="b9612-102">Регистрирует Сопоставитель токенов издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="b9612-102">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="b9612-103">Сопоставитель токенов издателей используется для разрешения токена подписывания на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="b9612-103">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="b9612-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="b9612-104">\<system.identityModel></span></span>  
<span data-ttu-id="b9612-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="b9612-105">\<identityConfiguration></span></span>  
<span data-ttu-id="b9612-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="b9612-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="b9612-107">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b9612-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="b9612-108">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="b9612-108">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9612-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9612-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b9612-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b9612-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b9612-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b9612-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b9612-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b9612-112">Attributes</span></span>  
  
|<span data-ttu-id="b9612-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b9612-113">Attribute</span></span>|<span data-ttu-id="b9612-114">Описание</span><span class="sxs-lookup"><span data-stu-id="b9612-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b9612-115">type</span><span class="sxs-lookup"><span data-stu-id="b9612-115">type</span></span>|<span data-ttu-id="b9612-116">Указывает тип Сопоставитель токенов издателей.</span><span class="sxs-lookup"><span data-stu-id="b9612-116">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="b9612-117">Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класс или тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="b9612-117">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="b9612-118">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="b9612-118">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b9612-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b9612-119">Child Elements</span></span>  
 <span data-ttu-id="b9612-120">Нет</span><span class="sxs-lookup"><span data-stu-id="b9612-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b9612-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b9612-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b9612-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="b9612-122">Element</span></span>|<span data-ttu-id="b9612-123">Описание:</span><span class="sxs-lookup"><span data-stu-id="b9612-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b9612-124">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="b9612-124">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="b9612-125">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="b9612-125">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9612-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9612-126">Remarks</span></span>  
 <span data-ttu-id="b9612-127">Сопоставитель токенов издателей используется для разрешения токена подписывания на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="b9612-127">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="b9612-128">Он используется для получения криптографическим материалом, используемый для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="b9612-128">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="b9612-129">Необходимо указать `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="b9612-129">You must specify the `type` attribute.</span></span> <span data-ttu-id="b9612-130">Указанный тип может быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> или пользовательский тип, производный от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="b9612-130">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="b9612-131">Некоторые обработчики маркеров позволяют задать параметры Сопоставитель токенов поставщика в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b9612-131">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="b9612-132">Параметры на отдельных обработчиков маркеров в переопределите указанных в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="b9612-132">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b9612-133">Указание `<issuerTokenResolver>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="b9612-133">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="b9612-134">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="b9612-134">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9612-135">Пример</span><span class="sxs-lookup"><span data-stu-id="b9612-135">Example</span></span>  
 <span data-ttu-id="b9612-136">Следующий код XML показана конфигурация для Сопоставитель токенов издателей, который основан на пользовательский класс, производный от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="b9612-136">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="b9612-137">Распознавателю маркеров поддерживает словарь пар "ключ аудитории", который инициализируется из настраиваемых элементов конфигурации (`<AddAudienceKeyPair>`) определенные для класса.</span><span class="sxs-lookup"><span data-stu-id="b9612-137">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="b9612-138">Этот класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для обработки этого элемента.</span><span class="sxs-lookup"><span data-stu-id="b9612-138">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="b9612-139">Переопределение показан в следующем примере; Тем не менее для краткости не показаны методы, которые она вызывает.</span><span class="sxs-lookup"><span data-stu-id="b9612-139">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="b9612-140">Полный пример см. в разделе `CustomToken` образца.</span><span class="sxs-lookup"><span data-stu-id="b9612-140">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="b9612-141">Пример</span><span class="sxs-lookup"><span data-stu-id="b9612-141">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9612-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b9612-142">See also</span></span>
- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
