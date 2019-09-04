---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251967"
---
# <a name="issuernameregistry"></a><span data-ttu-id="fa964-101">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="fa964-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="fa964-102">Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="fa964-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
<span data-ttu-id="fa964-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa964-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa964-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="fa964-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="fa964-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fa964-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="fa964-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="fa964-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="fa964-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Секурититокенхандлерконфигуратион >** ](securitytokenhandlerconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fa964-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)</span></span>\
<span data-ttu-id="fa964-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<issuerNameRegistry >**</span><span class="sxs-lookup"><span data-stu-id="fa964-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa964-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa964-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa964-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa964-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fa964-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fa964-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa964-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa964-112">Attributes</span></span>  
  
|<span data-ttu-id="fa964-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fa964-113">Attribute</span></span>|<span data-ttu-id="fa964-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fa964-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa964-115">type</span><span class="sxs-lookup"><span data-stu-id="fa964-115">type</span></span>|<span data-ttu-id="fa964-116">Тип, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="fa964-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="fa964-117">Дополнительные сведения о том, как указать пользовательский `type`параметр, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="fa964-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa964-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa964-118">Child Elements</span></span>  
  
|<span data-ttu-id="fa964-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa964-119">Element</span></span>|<span data-ttu-id="fa964-120">Описание</span><span class="sxs-lookup"><span data-stu-id="fa964-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa964-121">\<Трустедиссуерс ></span><span class="sxs-lookup"><span data-stu-id="fa964-121">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="fa964-122">Если атрибут указывает реестр имен издателя на основе конфигурации <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (класс), [ \<](trustedissuers.md) необходимо указать элемент > трустедиссуерс. `type`</span><span class="sxs-lookup"><span data-stu-id="fa964-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="fa964-123">Элемент > `<add>` `<clear>`трустедиссуерс может принимать элементы, или `<remove>` в качестве дочерних элементов. [ \<](trustedissuers.md)</span><span class="sxs-lookup"><span data-stu-id="fa964-123">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa964-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa964-124">Parent Elements</span></span>  
  
|<span data-ttu-id="fa964-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa964-125">Element</span></span>|<span data-ttu-id="fa964-126">Описание</span><span class="sxs-lookup"><span data-stu-id="fa964-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa964-127">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="fa964-127">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="fa964-128">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="fa964-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa964-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa964-129">Remarks</span></span>  
 <span data-ttu-id="fa964-130">Все маркеры издателя проверяются с помощью реестра имени издателя.</span><span class="sxs-lookup"><span data-stu-id="fa964-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="fa964-131">Это объект, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="fa964-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="fa964-132">Реестр имен издателей используется для связывания назначенного имени с криптографическим материалом, необходимым для проверки подписей маркеров, созданных соответствующим издателем.</span><span class="sxs-lookup"><span data-stu-id="fa964-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="fa964-133">В реестре имен издателей хранится список издателей, которым доверяет приложение проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="fa964-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="fa964-134">Тип реестра имени издателя указывается с помощью `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="fa964-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="fa964-135">`<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, которые предоставляют конфигурацию для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="fa964-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="fa964-136">Вы предоставляете логику, которая обрабатывает эти дочерние элементы <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> , переопределяя метод.</span><span class="sxs-lookup"><span data-stu-id="fa964-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="fa964-137">WIF предоставляет один тип реестра имени поставщика из поля, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс.</span><span class="sxs-lookup"><span data-stu-id="fa964-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="fa964-138">Этот класс использует набор сертификатов доверенных издателей, указанных в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa964-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="fa964-139">Для этого требуется дочерний элемент `<trustedIssuers>`конфигурации, в котором настроена Коллекция сертификатов доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="fa964-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="fa964-140">Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1, которые добавляются или удаляются из `<add>`коллекции `<clear>`с помощью `<remove>` элементов, или.</span><span class="sxs-lookup"><span data-stu-id="fa964-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="fa964-141">`<issuerNameRegistry>` Элемент представлен<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> классом.</span><span class="sxs-lookup"><span data-stu-id="fa964-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa964-142">Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="fa964-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="fa964-143">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="fa964-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa964-144">Пример</span><span class="sxs-lookup"><span data-stu-id="fa964-144">Example</span></span>  
 <span data-ttu-id="fa964-145">В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fa964-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa964-146">См. также</span><span class="sxs-lookup"><span data-stu-id="fa964-146">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
