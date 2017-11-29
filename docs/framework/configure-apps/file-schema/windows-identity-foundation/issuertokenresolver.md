---
title: '&lt;issuerTokenResolver&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 02e2beb285cb0c4d88f98c3155ab5a3ff5e31e0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltissuertokenresolvergt"></a><span data-ttu-id="e0c0c-102">&lt;issuerTokenResolver&gt;</span><span class="sxs-lookup"><span data-stu-id="e0c0c-102">&lt;issuerTokenResolver&gt;</span></span>
<span data-ttu-id="e0c0c-103">Регистрирует Сопоставитель токена издателя, используемая обработчиков в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-103">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e0c0c-104">Распознавателю маркеров издателя используется для разрешения маркера подписи для входящих токенов и сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-104">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span>  
  
 <span data-ttu-id="e0c0c-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="e0c0c-105">\<system.identityModel></span></span>  
<span data-ttu-id="e0c0c-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e0c0c-106">\<identityConfiguration></span></span>  
<span data-ttu-id="e0c0c-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e0c0c-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e0c0c-108">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e0c0c-108">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="e0c0c-109">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="e0c0c-109">\<issuerTokenResolver></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c0c-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0c0c-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e0c0c-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e0c0c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e0c0c-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e0c0c-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e0c0c-113">Attributes</span></span>  
  
|<span data-ttu-id="e0c0c-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e0c0c-114">Attribute</span></span>|<span data-ttu-id="e0c0c-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e0c0c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e0c0c-116">type</span><span class="sxs-lookup"><span data-stu-id="e0c0c-116">type</span></span>|<span data-ttu-id="e0c0c-117">Указывает тип издателя Распознавателю маркеров.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-117">Specifies the type of the issuer token resolver.</span></span> <span data-ttu-id="e0c0c-118">Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класс или тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-118">Must be either the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class or a type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span> <span data-ttu-id="e0c0c-119">Обязательный.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-119">Required.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e0c0c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e0c0c-120">Child Elements</span></span>  
 <span data-ttu-id="e0c0c-121">Нет</span><span class="sxs-lookup"><span data-stu-id="e0c0c-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e0c0c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e0c0c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e0c0c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="e0c0c-123">Element</span></span>|<span data-ttu-id="e0c0c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="e0c0c-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e0c0c-125">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e0c0c-125">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="e0c0c-126">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-126">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0c0c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="e0c0c-127">Remarks</span></span>  
 <span data-ttu-id="e0c0c-128">Распознавателю маркеров издателя используется для разрешения маркера подписи для входящих токенов и сообщения.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-128">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e0c0c-129">Он используется для извлечения шифровальных материалов, который используется для проверки подписи.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-129">It is used to retrieve the cryptographic material that is used for checking the signature.</span></span> <span data-ttu-id="e0c0c-130">Необходимо указать `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-130">You must specify the `type` attribute.</span></span> <span data-ttu-id="e0c0c-131">Указанный тип может быть как <xref:System.IdentityModel.Tokens.IssuerTokenResolver> или пользовательский тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-131">The type specified can be either <xref:System.IdentityModel.Tokens.IssuerTokenResolver> or a custom type that derives from the <xref:System.IdentityModel.Tokens.IssuerTokenResolver> class.</span></span>  
  
 <span data-ttu-id="e0c0c-132">Некоторые обработчики маркеров позволяют задать параметры поставщика арбитр маркеров в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-132">Some token handlers allow you to specify issuer token resolver settings in configuration.</span></span> <span data-ttu-id="e0c0c-133">Параметры на отдельных обработчиков маркеров переопределить указанных в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-133">Settings on individual token handlers override those specified on the security token handler collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e0c0c-134">Указание `<issuerTokenResolver>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-134">Specifying the `<issuerTokenResolver>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e0c0c-135">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-135">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0c0c-136">Пример</span><span class="sxs-lookup"><span data-stu-id="e0c0c-136">Example</span></span>  
 <span data-ttu-id="e0c0c-137">Следующий код XML показывает конфигурацию для арбитр маркеров издателя, который основан на пользовательский класс, производный от <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-137">The following XML shows configuration for an issuer token resolver that is based on a custom class that derives from <xref:System.IdentityModel.Tokens.IssuerTokenResolver>.</span></span> <span data-ttu-id="e0c0c-138">Распознавателю маркеров поддерживает словарь пар ключ аудитории, который инициализируется из настраиваемых элементов конфигурации (`<AddAudienceKeyPair>`) для класса определены.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-138">The token resolver maintains a dictionary of audience-key pairs that is initialized from a custom configuration element (`<AddAudienceKeyPair>`) defined for the class.</span></span> <span data-ttu-id="e0c0c-139">Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для обработки этого элемента.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-139">The class overrides the <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> method to process this element.</span></span> <span data-ttu-id="e0c0c-140">Переопределение показано в следующем примере; Тем не менее для краткости не отображаются методы, которые она вызывает.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-140">The override is shown in the following example; however, the methods it calls are not shown for brevity.</span></span> <span data-ttu-id="e0c0c-141">Полный пример см. в разделе `CustomToken` образца.</span><span class="sxs-lookup"><span data-stu-id="e0c0c-141">For the complete example, see the `CustomToken` sample.</span></span>  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a><span data-ttu-id="e0c0c-142">Пример</span><span class="sxs-lookup"><span data-stu-id="e0c0c-142">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0c0c-143">См. также</span><span class="sxs-lookup"><span data-stu-id="e0c0c-143">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerTokenResolver>
