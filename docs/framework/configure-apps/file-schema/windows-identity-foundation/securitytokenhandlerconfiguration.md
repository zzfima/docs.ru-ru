---
title: '&lt;securityTokenHandlerConfiguration&gt;'
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: d66771ec7ed52ace52df6bb3bfafdcf9cce989b5
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070933"
---
# <a name="ltsecuritytokenhandlerconfigurationgt"></a><span data-ttu-id="8f047-102">&lt;securityTokenHandlerConfiguration&gt;</span><span class="sxs-lookup"><span data-stu-id="8f047-102">&lt;securityTokenHandlerConfiguration&gt;</span></span>
<span data-ttu-id="8f047-103">Предоставляет конфигурацию для коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="8f047-103">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="8f047-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="8f047-104">\<system.identityModel></span></span>  
<span data-ttu-id="8f047-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8f047-105">\<identityConfiguration></span></span>  
<span data-ttu-id="8f047-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="8f047-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="8f047-107">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="8f047-107">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f047-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f047-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8f047-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8f047-109">Attributes and Elements</span></span>  
 <span data-ttu-id="8f047-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8f047-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8f047-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8f047-111">Attributes</span></span>  
  
|<span data-ttu-id="8f047-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8f047-112">Attribute</span></span>|<span data-ttu-id="8f047-113">Описание</span><span class="sxs-lookup"><span data-stu-id="8f047-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8f047-114">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="8f047-114">saveBootstrapContext</span></span>|<span data-ttu-id="8f047-115">Указывает, включаются ли токены начальной загрузки в токен сеанса.</span><span class="sxs-lookup"><span data-stu-id="8f047-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="8f047-116">Также можно задать значение в коллекцию обработчиков токенов, задав `saveBootstrapContext` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="8f047-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="8f047-117">Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.</span><span class="sxs-lookup"><span data-stu-id="8f047-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="8f047-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="8f047-118">maximumClockSkew</span></span>|<span data-ttu-id="8f047-119">Объект <xref:System.TimeSpan> , указывающее максимальное допустимое время отклонения.</span><span class="sxs-lookup"><span data-stu-id="8f047-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="8f047-120">Определяет максимальное допустимое время отклонения при выполнении операций, зависящих от времени, таких как проверка срока действия сеанса входа в систему.</span><span class="sxs-lookup"><span data-stu-id="8f047-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="8f047-121">Значение по умолчанию — 5 минут «00: 05:00».</span><span class="sxs-lookup"><span data-stu-id="8f047-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="8f047-122">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="8f047-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="8f047-123">Также можно задать максимальную расфазировку синхронизирующих импульсов на уровне службы, задав `maximumClockSkew` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="8f047-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="8f047-124">Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.</span><span class="sxs-lookup"><span data-stu-id="8f047-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8f047-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8f047-125">Child Elements</span></span>  
  
|<span data-ttu-id="8f047-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f047-126">Element</span></span>|<span data-ttu-id="8f047-127">Описание</span><span class="sxs-lookup"><span data-stu-id="8f047-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f047-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="8f047-128">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="8f047-129">Задает набор URI, допустимых идентификаторов этой проверяющей стороне.</span><span class="sxs-lookup"><span data-stu-id="8f047-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="8f047-130">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-130">Optional.</span></span>|  
|[<span data-ttu-id="8f047-131">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="8f047-131">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="8f047-132">Регистрирует кэши маркеров сеанса и обнаружения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="8f047-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="8f047-133">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="8f047-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8f047-134">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-134">Optional.</span></span>|  
|[<span data-ttu-id="8f047-135">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="8f047-135">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="8f047-136">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="8f047-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="8f047-137">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="8f047-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8f047-138">Эти параметры переопределяются в том случае, если настроен собственный проверяющий элемент управления указанным обработчиком.</span><span class="sxs-lookup"><span data-stu-id="8f047-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="8f047-139">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-139">Optional.</span></span>|  
|[<span data-ttu-id="8f047-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="8f047-140">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="8f047-141">Настраивает реестр имен издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="8f047-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8f047-142">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-142">Optional.</span></span>|  
|[<span data-ttu-id="8f047-143">\<issuerTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="8f047-143">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="8f047-144">Регистрирует Сопоставитель токенов издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="8f047-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8f047-145">Сопоставитель токенов издателей используется для разрешения токена подписывания на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="8f047-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="8f047-146">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-146">Optional.</span></span>|  
|[<span data-ttu-id="8f047-147">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="8f047-147">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="8f047-148">Регистрирует Сопоставитель токенов служб, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="8f047-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="8f047-149">Сопоставитель токенов служб используется для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="8f047-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="8f047-150">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-150">Optional.</span></span>|  
|[<span data-ttu-id="8f047-151">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="8f047-151">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="8f047-152">Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="8f047-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="8f047-153">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="8f047-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="8f047-154">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="8f047-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8f047-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8f047-155">Parent Elements</span></span>  
  
|<span data-ttu-id="8f047-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="8f047-156">Element</span></span>|<span data-ttu-id="8f047-157">Описание</span><span class="sxs-lookup"><span data-stu-id="8f047-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8f047-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="8f047-158">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="8f047-159">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="8f047-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8f047-160">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f047-160">Remarks</span></span>  
 <span data-ttu-id="8f047-161">В этом разделе содержатся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта.</span><span class="sxs-lookup"><span data-stu-id="8f047-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="8f047-162">Параметры, настроенные в этом разделе, переопределяют сконфигурирован в службе.</span><span class="sxs-lookup"><span data-stu-id="8f047-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="8f047-163">Некоторые из этих параметров могут в свою очередь, переопределяться параметры, заданные в случае, когда обработчик добавляется в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="8f047-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f047-164">Пример</span><span class="sxs-lookup"><span data-stu-id="8f047-164">Example</span></span>  
  
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
