---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: db4e0492772d6fd0e155843422b7350aa630f713
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369686"
---
# <a name="issuernameregistry"></a><span data-ttu-id="eadcc-101">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="eadcc-101">\<issuerNameRegistry></span></span>
<span data-ttu-id="eadcc-102">Настраивает реестр имен издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="eadcc-102">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="eadcc-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="eadcc-103">\<system.identityModel></span></span>  
<span data-ttu-id="eadcc-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="eadcc-104">\<identityConfiguration></span></span>  
<span data-ttu-id="eadcc-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="eadcc-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="eadcc-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="eadcc-106">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="eadcc-107">\<issuerNameRegistry></span><span class="sxs-lookup"><span data-stu-id="eadcc-107">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eadcc-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eadcc-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eadcc-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eadcc-109">Attributes and Elements</span></span>  
 <span data-ttu-id="eadcc-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eadcc-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eadcc-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eadcc-111">Attributes</span></span>  
  
|<span data-ttu-id="eadcc-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eadcc-112">Attribute</span></span>|<span data-ttu-id="eadcc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="eadcc-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eadcc-114">type</span><span class="sxs-lookup"><span data-stu-id="eadcc-114">type</span></span>|<span data-ttu-id="eadcc-115">Тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="eadcc-115">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="eadcc-116">Дополнительные сведения о том, как задать пользовательский `type`, см. в разделе [ссылки на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="eadcc-116">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eadcc-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eadcc-117">Child Elements</span></span>  
  
|<span data-ttu-id="eadcc-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="eadcc-118">Element</span></span>|<span data-ttu-id="eadcc-119">Описание</span><span class="sxs-lookup"><span data-stu-id="eadcc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eadcc-120">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="eadcc-120">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="eadcc-121">Когда `type` атрибут задает реестр имен издателей на основе конфигурации ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент должен быть указан.</span><span class="sxs-lookup"><span data-stu-id="eadcc-121">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="eadcc-122">[ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент может занять `<add>`, `<clear>`, или `<remove>` элементы как дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="eadcc-122">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eadcc-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eadcc-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eadcc-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="eadcc-124">Element</span></span>|<span data-ttu-id="eadcc-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="eadcc-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eadcc-126">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="eadcc-126">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="eadcc-127">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="eadcc-127">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eadcc-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="eadcc-128">Remarks</span></span>  
 <span data-ttu-id="eadcc-129">Все маркеры издателей проверяются с помощью реестра имен издателей.</span><span class="sxs-lookup"><span data-stu-id="eadcc-129">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="eadcc-130">Это объект, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="eadcc-130">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="eadcc-131">Реестр имен издателей используется для сопоставления мнемонического имени с криптографическим материалом, необходимым для проверки подписи токенов, выдаваемых соответствующим издателем.</span><span class="sxs-lookup"><span data-stu-id="eadcc-131">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="eadcc-132">Реестр имен издателей ведет список издателей, которым доверяет приложение проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="eadcc-132">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="eadcc-133">Тип реестр имен издателей задается с помощью `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="eadcc-133">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="eadcc-134">`<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, обеспечивающие конфигурацию для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="eadcc-134">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="eadcc-135">Обеспечивают логику, которая обрабатывает эти дочерние элементы, переопределив <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="eadcc-135">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="eadcc-136">WIF предоставляет единый издателя тип реестра имя по умолчанию, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="eadcc-136">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="eadcc-137">Этот класс использует набор доверенных сертификатов издателей, которые указаны в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eadcc-137">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="eadcc-138">Он требуется дочерний элемент конфигурации, `<trustedIssuers>`, в которой настроено коллекции доверенных сертификатов издателей.</span><span class="sxs-lookup"><span data-stu-id="eadcc-138">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="eadcc-139">Доверенные сертификаты указываются с помощью ASN.1 отпечатка сертификата в кодировке и добавляются или удаляются из коллекции с помощью `<add>`, `<clear>`, или `<remove>` элементов.</span><span class="sxs-lookup"><span data-stu-id="eadcc-139">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="eadcc-140">`<issuerNameRegistry>` Элемент, представленный объектом <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> класса.</span><span class="sxs-lookup"><span data-stu-id="eadcc-140">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eadcc-141">Указание `<issuerNameRegistry>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="eadcc-141">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="eadcc-142">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="eadcc-142">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eadcc-143">Пример</span><span class="sxs-lookup"><span data-stu-id="eadcc-143">Example</span></span>  
 <span data-ttu-id="eadcc-144">Следующий код XML показано, как указать поставщика конфигурации на основе реестра имен.</span><span class="sxs-lookup"><span data-stu-id="eadcc-144">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eadcc-145">См. также</span><span class="sxs-lookup"><span data-stu-id="eadcc-145">See also</span></span>
- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
