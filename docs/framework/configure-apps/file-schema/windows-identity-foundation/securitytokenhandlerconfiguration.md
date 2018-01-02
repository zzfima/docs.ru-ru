---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ac7284fa418c1540582c40bd744e913ba31aa881
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="a6861-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="a6861-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="a6861-103">Обеспечивает настройку для коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="a6861-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="a6861-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="a6861-104">\<system.identityModel></span></span>  
<span data-ttu-id="a6861-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a6861-105">\<identityConfiguration></span></span>  
<span data-ttu-id="a6861-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="a6861-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="a6861-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="a6861-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6861-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6861-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration saveBootstrapContext=xs:boolean  
          maximumClockSkew=TimeSpan>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6861-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a6861-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a6861-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a6861-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6861-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a6861-111">Attributes</span></span>  
  
|<span data-ttu-id="a6861-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a6861-112">Attribute</span></span>|<span data-ttu-id="a6861-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="a6861-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a6861-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="a6861-114">saveBootstrapContext</span></span>|<span data-ttu-id="a6861-115">Указывает, следует ли включать в токен сеанса начальной загрузки маркеры.</span><span class="sxs-lookup"><span data-stu-id="a6861-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="a6861-116">Значение также может быть задана для коллекции обработчика токенов, задав `saveBootstrapContext` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="a6861-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="a6861-117">Значение, заданное в коллекцию обработчиков токенов переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="a6861-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="a6861-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="a6861-118">maximumClockSkew</span></span>|<span data-ttu-id="a6861-119">Объект <xref:System.TimeSpan> , указывающее максимально допустимое время отклонения.</span><span class="sxs-lookup"><span data-stu-id="a6861-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="a6861-120">Определяет максимально допустимое время отклонения при выполнении операций, зависящих от времени, например для проверки истечения срока действия сеанса входа в систему.</span><span class="sxs-lookup"><span data-stu-id="a6861-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="a6861-121">Значение по умолчанию — 5 минут «00: 05:00».</span><span class="sxs-lookup"><span data-stu-id="a6861-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="a6861-122">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="a6861-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="a6861-123">Также можно задать максимальную расфазировку синхронизирующих импульсов на уровне службы, задав `maximumClockSkew` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="a6861-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="a6861-124">Значение, заданное в коллекцию обработчиков токенов переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="a6861-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6861-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a6861-125">Child Elements</span></span>  
  
|<span data-ttu-id="a6861-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6861-126">Element</span></span>|<span data-ttu-id="a6861-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="a6861-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6861-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="a6861-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="a6861-129">Задает набор URI, допустимых идентификаторов этой проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="a6861-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="a6861-130">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-130">Optional.</span></span>|  
|[<span data-ttu-id="a6861-131">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="a6861-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="a6861-132">Регистрирует кэши, используемый для маркеров сеансов и обнаружение воспроизведения токенов.</span><span class="sxs-lookup"><span data-stu-id="a6861-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="a6861-133">Можно указать на уровне службы или в коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="a6861-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="a6861-134">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-134">Optional.</span></span>|  
|[<span data-ttu-id="a6861-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="a6861-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="a6861-136">Управляет параметрами обработчиков токенов, используемых для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a6861-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="a6861-137">Можно указать на уровне службы или в коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="a6861-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="a6861-138">Эти параметры переопределяются, если обработчик конкретного настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="a6861-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="a6861-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-139">Optional.</span></span>|  
|[<span data-ttu-id="a6861-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="a6861-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="a6861-141">Настройка реестра имя издателя, используемая обработчиков в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="a6861-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a6861-142">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-142">Optional.</span></span>|  
|[<span data-ttu-id="a6861-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="a6861-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="a6861-144">Регистрирует Сопоставитель токена издателя, используемая обработчиков в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="a6861-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a6861-145">Распознавателю маркеров издателя используется для разрешения маркера подписи для входящих токенов и сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6861-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="a6861-146">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-146">Optional.</span></span>|  
|[<span data-ttu-id="a6861-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="a6861-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="a6861-148">Регистрирует Сопоставитель токена службы, используемой обработчиков в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="a6861-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="a6861-149">Распознавателю маркеров службы используется для разрешения маркера шифрования для входящих токенов и сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6861-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="a6861-150">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-150">Optional.</span></span>|  
|[<span data-ttu-id="a6861-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="a6861-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="a6861-152">Включает обнаружение воспроизведения токенов и определяет время жизни токенов.</span><span class="sxs-lookup"><span data-stu-id="a6861-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="a6861-153">Можно указать на уровне службы или в коллекцию обработчика токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="a6861-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="a6861-154">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="a6861-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6861-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a6861-155">Parent Elements</span></span>  
  
|<span data-ttu-id="a6861-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6861-156">Element</span></span>|<span data-ttu-id="a6861-157">Описание:</span><span class="sxs-lookup"><span data-stu-id="a6861-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a6861-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="a6861-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="a6861-159">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="a6861-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6861-160">Примечания</span><span class="sxs-lookup"><span data-stu-id="a6861-160">Remarks</span></span>  
 <span data-ttu-id="a6861-161">В этом разделе содержатся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта.</span><span class="sxs-lookup"><span data-stu-id="a6861-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="a6861-162">Параметры, настроенные в этом разделе переопределяют настройки на стороне службы.</span><span class="sxs-lookup"><span data-stu-id="a6861-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="a6861-163">Некоторые из этих параметров можно переопределить в свою очередь, используются параметры, которые указаны при добавлении обработчик в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="a6861-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6861-164">Пример</span><span class="sxs-lookup"><span data-stu-id="a6861-164">Example</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>   
      <securityTokenHandlerConfiguration>  
  
        <audienceUris>  
          <clear/>  
          <add value="http://www.example.com/myapp/" />  
        </audienceUris>  
  
        <issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel">  
          <trustedIssuers>  
            <add thumbprint="97249e1a … 4c9158de" name="contoso.com" />  
          </trustedIssuers>  
        </issuerNameRegistry>  
  
        <issuerTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
        <serviceTokenResolver type="MyNamespace.CustomTokenResolver, MyAssembly" />  
  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```
