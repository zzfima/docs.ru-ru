---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48838485"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="c5bc9-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="c5bc9-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="c5bc9-103">Предоставляет конфигурацию для коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="c5bc9-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-104">\<system.identityModel></span></span>  
<span data-ttu-id="c5bc9-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-105">\<identityConfiguration></span></span>  
<span data-ttu-id="c5bc9-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="c5bc9-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bc9-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c5bc9-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c5bc9-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c5bc9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c5bc9-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c5bc9-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c5bc9-111">Attributes</span></span>  
  
|<span data-ttu-id="c5bc9-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c5bc9-112">Attribute</span></span>|<span data-ttu-id="c5bc9-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="c5bc9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c5bc9-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="c5bc9-114">saveBootstrapContext</span></span>|<span data-ttu-id="c5bc9-115">Указывает, включаются ли токены начальной загрузки в токен сеанса.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="c5bc9-116">Также можно задать значение в коллекцию обработчиков токенов, задав `saveBootstrapContext` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="c5bc9-117">Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="c5bc9-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="c5bc9-118">maximumClockSkew</span></span>|<span data-ttu-id="c5bc9-119">Объект <xref:System.TimeSpan> , указывающее максимальное допустимое время отклонения.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="c5bc9-120">Определяет максимальное допустимое время отклонения при выполнении операций, зависящих от времени, таких как проверка срока действия сеанса входа в систему.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="c5bc9-121">Значение по умолчанию — 5 минут «00: 05:00».</span><span class="sxs-lookup"><span data-stu-id="c5bc9-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="c5bc9-122">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="c5bc9-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="c5bc9-123">Также можно задать максимальную расфазировку синхронизирующих импульсов на уровне службы, задав `maximumClockSkew` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="c5bc9-124">Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c5bc9-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c5bc9-125">Child Elements</span></span>  
  
|<span data-ttu-id="c5bc9-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="c5bc9-126">Element</span></span>|<span data-ttu-id="c5bc9-127">Описание:</span><span class="sxs-lookup"><span data-stu-id="c5bc9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5bc9-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="c5bc9-129">Задает набор URI, допустимых идентификаторов этой проверяющей стороне.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="c5bc9-130">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-130">Optional.</span></span>|  
|[<span data-ttu-id="c5bc9-131">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="c5bc9-132">Регистрирует кэши маркеров сеанса и обнаружения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="c5bc9-133">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c5bc9-134">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-134">Optional.</span></span>|  
|[<span data-ttu-id="c5bc9-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="c5bc9-136">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="c5bc9-137">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c5bc9-138">Эти параметры переопределяются в том случае, если настроен собственный проверяющий элемент управления указанным обработчиком.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="c5bc9-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-139">Optional.</span></span>|  
|[<span data-ttu-id="c5bc9-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="c5bc9-141">Настраивает реестр имен издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c5bc9-142">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-142">Optional.</span></span>|  
|[<span data-ttu-id="c5bc9-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="c5bc9-144">Регистрирует Сопоставитель токенов издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c5bc9-145">Сопоставитель токенов издателей используется для разрешения токена подписывания на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="c5bc9-146">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-146">Optional.</span></span>|  
|[<span data-ttu-id="c5bc9-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="c5bc9-148">Регистрирует Сопоставитель токенов служб, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="c5bc9-149">Сопоставитель токенов служб используется для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="c5bc9-150">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-150">Optional.</span></span>|  
|[<span data-ttu-id="c5bc9-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="c5bc9-152">Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="c5bc9-153">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="c5bc9-154">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c5bc9-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c5bc9-155">Parent Elements</span></span>  
  
|<span data-ttu-id="c5bc9-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="c5bc9-156">Element</span></span>|<span data-ttu-id="c5bc9-157">Описание:</span><span class="sxs-lookup"><span data-stu-id="c5bc9-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c5bc9-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="c5bc9-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="c5bc9-159">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5bc9-160">Примечания</span><span class="sxs-lookup"><span data-stu-id="c5bc9-160">Remarks</span></span>  
 <span data-ttu-id="c5bc9-161">В этом разделе содержатся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="c5bc9-162">Параметры, настроенные в этом разделе, переопределяют сконфигурирован в службе.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="c5bc9-163">Некоторые из этих параметров могут в свою очередь, переопределяться параметры, заданные в случае, когда обработчик добавляется в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="c5bc9-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5bc9-164">Пример</span><span class="sxs-lookup"><span data-stu-id="c5bc9-164">Example</span></span>  
  
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
