---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: d0a1f8dd0c29aaee56c2ca1162cc70cc1e5ed106
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942665"
---
# <a name="issuernameregistry"></a><span data-ttu-id="e4128-101">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="e4128-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="e4128-102">Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e4128-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="e4128-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="e4128-103">\<system.identityModel></span></span>  
<span data-ttu-id="e4128-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="e4128-104">\<identityConfiguration></span></span>  
<span data-ttu-id="e4128-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e4128-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="e4128-106">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="e4128-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="e4128-107">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="e4128-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4128-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4128-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4128-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e4128-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e4128-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e4128-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4128-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e4128-111">Attributes</span></span>  
  
|<span data-ttu-id="e4128-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e4128-112">Attribute</span></span>|<span data-ttu-id="e4128-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e4128-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e4128-114">type</span><span class="sxs-lookup"><span data-stu-id="e4128-114">type</span></span>|<span data-ttu-id="e4128-115">Тип, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="e4128-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="e4128-116">Дополнительные сведения о том, как указать пользовательский `type`параметр, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="e4128-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e4128-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e4128-117">Child Elements</span></span>  
  
|<span data-ttu-id="e4128-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="e4128-118">Element</span></span>|<span data-ttu-id="e4128-119">Описание</span><span class="sxs-lookup"><span data-stu-id="e4128-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4128-120">\<Трустедиссуерс ></span><span class="sxs-lookup"><span data-stu-id="e4128-120">\<trustedIssuers></span></span>](trustedissuers.md)|<span data-ttu-id="e4128-121">Если атрибут указывает реестр имен издателя на основе конфигурации <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> (класс), [ \<](trustedissuers.md) необходимо указать элемент > трустедиссуерс. `type`</span><span class="sxs-lookup"><span data-stu-id="e4128-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="e4128-122">Элемент > `<add>` `<clear>`трустедиссуерс может принимать элементы, или `<remove>` в качестве дочерних элементов. [ \<](trustedissuers.md)</span><span class="sxs-lookup"><span data-stu-id="e4128-122">The [\<trustedIssuers>](trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e4128-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e4128-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e4128-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e4128-124">Element</span></span>|<span data-ttu-id="e4128-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e4128-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e4128-126">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="e4128-126">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="e4128-127">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e4128-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4128-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4128-128">Remarks</span></span>  
 <span data-ttu-id="e4128-129">Все маркеры издателя проверяются с помощью реестра имени издателя.</span><span class="sxs-lookup"><span data-stu-id="e4128-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="e4128-130">Это объект, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="e4128-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="e4128-131">Реестр имен издателей используется для связывания назначенного имени с криптографическим материалом, необходимым для проверки подписей маркеров, созданных соответствующим издателем.</span><span class="sxs-lookup"><span data-stu-id="e4128-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="e4128-132">В реестре имен издателей хранится список издателей, которым доверяет приложение проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="e4128-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="e4128-133">Тип реестра имени издателя указывается с помощью `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="e4128-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="e4128-134">`<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, которые предоставляют конфигурацию для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="e4128-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="e4128-135">Вы предоставляете логику, которая обрабатывает эти дочерние элементы <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> , переопределяя метод.</span><span class="sxs-lookup"><span data-stu-id="e4128-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="e4128-136">WIF предоставляет один тип реестра имени поставщика из поля, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс.</span><span class="sxs-lookup"><span data-stu-id="e4128-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="e4128-137">Этот класс использует набор сертификатов доверенных издателей, указанных в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4128-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="e4128-138">Для этого требуется дочерний элемент `<trustedIssuers>`конфигурации, в котором настроена Коллекция сертификатов доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="e4128-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="e4128-139">Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1, которые добавляются или удаляются из `<add>`коллекции `<clear>`с помощью `<remove>` элементов, или.</span><span class="sxs-lookup"><span data-stu-id="e4128-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="e4128-140">`<issuerNameRegistry>` Элемент представлен<xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> классом.</span><span class="sxs-lookup"><span data-stu-id="e4128-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4128-141">Указание элемента в качестве дочернего элемента [ \<элемента > identityConfiguration](identityconfiguration.md) является устаревшим, но по-прежнему поддерживается для обратной совместимости. `<issuerNameRegistry>`</span><span class="sxs-lookup"><span data-stu-id="e4128-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="e4128-142">Параметры элемента переопределяют их `<identityConfiguration>` для элемента. `<securityTokenHandlerConfiguration>`</span><span class="sxs-lookup"><span data-stu-id="e4128-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4128-143">Пример</span><span class="sxs-lookup"><span data-stu-id="e4128-143">Example</span></span>  
 <span data-ttu-id="e4128-144">В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e4128-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4128-145">См. также</span><span class="sxs-lookup"><span data-stu-id="e4128-145">See also</span></span>

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
