---
title: '&lt;issuerNameRegistry&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0c0552e06564e09832cf78afeb8f183a0a0dc94c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuernameregistrygt"></a><span data-ttu-id="40945-102">&lt;issuerNameRegistry&gt;</span><span class="sxs-lookup"><span data-stu-id="40945-102">&lt;issuerNameRegistry&gt;</span></span>
<span data-ttu-id="40945-103">Настройка реестра имя издателя, используемая обработчиков в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="40945-103">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span>  
  
 <span data-ttu-id="40945-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="40945-104">\<system.identityModel></span></span>  
<span data-ttu-id="40945-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="40945-105">\<identityConfiguration></span></span>  
<span data-ttu-id="40945-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="40945-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="40945-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="40945-107">\<securityTokenHandlerConfiguration></span></span>  
<span data-ttu-id="40945-108">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="40945-108">\<issuerNameRegistry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40945-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="40945-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40945-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="40945-110">Attributes and Elements</span></span>  
 <span data-ttu-id="40945-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="40945-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40945-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="40945-112">Attributes</span></span>  
  
|<span data-ttu-id="40945-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="40945-113">Attribute</span></span>|<span data-ttu-id="40945-114">Описание</span><span class="sxs-lookup"><span data-stu-id="40945-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="40945-115">type</span><span class="sxs-lookup"><span data-stu-id="40945-115">type</span></span>|<span data-ttu-id="40945-116">Тип, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="40945-116">A type that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="40945-117">Дополнительные сведения о том, как задать пользовательский `type`, в разделе [ссылок на пользовательские типы].</span><span class="sxs-lookup"><span data-stu-id="40945-117">For more information about how to specify a custom `type`, see [Custom Type References].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40945-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="40945-118">Child Elements</span></span>  
  
|<span data-ttu-id="40945-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="40945-119">Element</span></span>|<span data-ttu-id="40945-120">Описание</span><span class="sxs-lookup"><span data-stu-id="40945-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40945-121">\<trustedIssuers ></span><span class="sxs-lookup"><span data-stu-id="40945-121">\<trustedIssuers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md)|<span data-ttu-id="40945-122">Когда `type` атрибут задает имя издателя на основе конфигурации реестра ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса), [ \<trustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) должен быть указан элемент.</span><span class="sxs-lookup"><span data-stu-id="40945-122">When the `type` attribute specifies the configuration-based issuer name registry (the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class), the [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element must be specified.</span></span> <span data-ttu-id="40945-123">[ \<TrustedIssuers >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) элемент может занять `<add>`, `<clear>`, или `<remove>` элементы в виде дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="40945-123">The [\<trustedIssuers>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/trustedissuers.md) element can take `<add>`, `<clear>`, or `<remove>` elements as child elements.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="40945-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="40945-124">Parent Elements</span></span>  
  
|<span data-ttu-id="40945-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="40945-125">Element</span></span>|<span data-ttu-id="40945-126">Описание</span><span class="sxs-lookup"><span data-stu-id="40945-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="40945-127">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="40945-127">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="40945-128">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="40945-128">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40945-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="40945-129">Remarks</span></span>  
 <span data-ttu-id="40945-130">Все маркеры издателей проверяются с помощью реестра имя издателя.</span><span class="sxs-lookup"><span data-stu-id="40945-130">All issuer tokens are validated using an issuer name registry.</span></span> <span data-ttu-id="40945-131">Это объект, который является производным от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="40945-131">This is an object that derives from the <xref:System.IdentityModel.Tokens.IssuerNameRegistry> class.</span></span> <span data-ttu-id="40945-132">Реестр имен поставщиков позволяет связать имя, назначенный криптографические материалы, необходимые для проверки подписи токенов, созданных соответствующего поставщика.</span><span class="sxs-lookup"><span data-stu-id="40945-132">The issuer name registry is used to associate a mnemonic name to the cryptographic material that is needed to verify the signatures of tokens produced by the corresponding issuer.</span></span> <span data-ttu-id="40945-133">Реестр имен поставщиков ведет список издателей, которым доверяют приложения проверяющей стороны (RP).</span><span class="sxs-lookup"><span data-stu-id="40945-133">The issuer name registry maintains a list of issuers that are trusted by the relying party (RP) application.</span></span> <span data-ttu-id="40945-134">Тип реестра имя поставщика задается с помощью `type` атрибута.</span><span class="sxs-lookup"><span data-stu-id="40945-134">The type of the issuer name registry is specified using the `type` attribute.</span></span> <span data-ttu-id="40945-135">`<issuerNameRegistry>` Элемент может иметь один или несколько дочерних элементов, предоставляющих конфигурации для указанного типа.</span><span class="sxs-lookup"><span data-stu-id="40945-135">The `<issuerNameRegistry>` element can have one or more child elements that provide configuration for the specified type.</span></span> <span data-ttu-id="40945-136">Предоставляют логику, которая обрабатывает эти дочерние элементы, переопределив <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="40945-136">You provide the logic that processes these child elements by overriding the <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> method.</span></span>  
  
 <span data-ttu-id="40945-137">WIF предоставляет одного издателя, имя типа реестра без дополнительной настройки <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класса.</span><span class="sxs-lookup"><span data-stu-id="40945-137">WIF provides a single issuer name registry type out of the box, the <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> class.</span></span> <span data-ttu-id="40945-138">Этот класс используется набор доверенных издателей сертификатов, которые указаны в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="40945-138">This class uses a set of trusted issuer certificates that are specified in configuration.</span></span> <span data-ttu-id="40945-139">Требуется дочерний элемент конфигурации, `<trustedIssuers>`, в которой настроено в коллекцию сертификатов доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="40945-139">It requires a child configuration element, `<trustedIssuers>`, under which the collection of trusted issuer certificates is configured.</span></span> <span data-ttu-id="40945-140">Доверенные сертификаты указываются с помощью ASN.1 отпечаток сертификата в кодировке и добавления или удаления из коллекции с помощью `<add>`, `<clear>`, или `<remove>` элементы.</span><span class="sxs-lookup"><span data-stu-id="40945-140">Trusted certificates are specified using the ASN.1 encoded form of the certificate thumbprint and are added or removed from the collection by using `<add>`, `<clear>`, or `<remove>` elements.</span></span>  
  
 <span data-ttu-id="40945-141">`<issuerNameRegistry>` Представлен <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> класса.</span><span class="sxs-lookup"><span data-stu-id="40945-141">The `<issuerNameRegistry>` element is represented by the <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40945-142">Указание `<issuerNameRegistry>` элемент как дочерний элемент элемента [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент является устаревшим, но по-прежнему поддерживается для обеспечения обратной совместимости.</span><span class="sxs-lookup"><span data-stu-id="40945-142">Specifying the `<issuerNameRegistry>` element as a child element of the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element has been deprecated, but is still supported for backward compatibility.</span></span> <span data-ttu-id="40945-143">Параметры на `<securityTokenHandlerConfiguration>` элемент переопределяют на `<identityConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="40945-143">Settings on the `<securityTokenHandlerConfiguration>` element override those on the `<identityConfiguration>` element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40945-144">Пример</span><span class="sxs-lookup"><span data-stu-id="40945-144">Example</span></span>  
 <span data-ttu-id="40945-145">Следующий код XML показано, как указать поставщика конфигурации на основе реестра имя.</span><span class="sxs-lookup"><span data-stu-id="40945-145">The following XML shows how to specify the configuration based issuer name registry.</span></span>  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40945-146">См. также</span><span class="sxs-lookup"><span data-stu-id="40945-146">See Also</span></span>  
 <xref:System.IdentityModel.Tokens.IssuerNameRegistry>  
 <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>
