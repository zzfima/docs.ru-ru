---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 29e18cdda9e18addef4f0f32fd30e9abf6af78fc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793852"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="cb666-101">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cb666-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="cb666-102">Предоставляет конфигурацию для коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="cb666-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="cb666-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="cb666-103">\<system.identityModel></span></span>  
<span data-ttu-id="cb666-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="cb666-104">\<identityConfiguration></span></span>  
<span data-ttu-id="cb666-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="cb666-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="cb666-106">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="cb666-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb666-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cb666-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb666-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cb666-108">Attributes and Elements</span></span>  
 <span data-ttu-id="cb666-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cb666-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb666-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cb666-110">Attributes</span></span>  
  
|<span data-ttu-id="cb666-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cb666-111">Attribute</span></span>|<span data-ttu-id="cb666-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cb666-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb666-113">saveBootstrapContext</span><span class="sxs-lookup"><span data-stu-id="cb666-113">saveBootstrapContext</span></span>|<span data-ttu-id="cb666-114">Указывает, включаются ли токены начальной загрузки в токен сеанса.</span><span class="sxs-lookup"><span data-stu-id="cb666-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="cb666-115">Также можно задать значение в коллекцию обработчиков токенов, задав `saveBootstrapContext` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="cb666-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="cb666-116">Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.</span><span class="sxs-lookup"><span data-stu-id="cb666-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="cb666-117">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="cb666-117">maximumClockSkew</span></span>|<span data-ttu-id="cb666-118">Объект <xref:System.TimeSpan> , указывающее максимальное допустимое время отклонения.</span><span class="sxs-lookup"><span data-stu-id="cb666-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="cb666-119">Определяет максимальное допустимое время отклонения при выполнении операций, зависящих от времени, таких как проверка срока действия сеанса входа в систему.</span><span class="sxs-lookup"><span data-stu-id="cb666-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="cb666-120">Значение по умолчанию — 5 минут «00: 05:00».</span><span class="sxs-lookup"><span data-stu-id="cb666-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="cb666-121">Дополнительные сведения о способах указания <xref:System.TimeSpan> значения, см. в разделе [значения Timespan](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="cb666-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="cb666-122">Также можно задать максимальную расфазировку синхронизирующих импульсов на уровне службы, задав `maximumClockSkew` атрибут [ \<identityConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="cb666-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md) element.</span></span> <span data-ttu-id="cb666-123">Значение, заданное на коллекцию обработчиков токенов переопределяет значение, заданное в службе.</span><span class="sxs-lookup"><span data-stu-id="cb666-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb666-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cb666-124">Child Elements</span></span>  
  
|<span data-ttu-id="cb666-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb666-125">Element</span></span>|<span data-ttu-id="cb666-126">Описание</span><span class="sxs-lookup"><span data-stu-id="cb666-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb666-127">\<audienceUris></span><span class="sxs-lookup"><span data-stu-id="cb666-127">\<audienceUris></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/audienceuris.md)|<span data-ttu-id="cb666-128">Задает набор URI, допустимых идентификаторов этой проверяющей стороне.</span><span class="sxs-lookup"><span data-stu-id="cb666-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="cb666-129">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-129">Optional.</span></span>|  
|[<span data-ttu-id="cb666-130">\<кэширует ></span><span class="sxs-lookup"><span data-stu-id="cb666-130">\<caches></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|<span data-ttu-id="cb666-131">Регистрирует кэши маркеров сеанса и обнаружения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="cb666-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="cb666-132">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb666-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="cb666-133">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-133">Optional.</span></span>|  
|[<span data-ttu-id="cb666-134">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="cb666-134">\<certificateValidation></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md)|<span data-ttu-id="cb666-135">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="cb666-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="cb666-136">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb666-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="cb666-137">Эти параметры переопределяются в том случае, если настроен собственный проверяющий элемент управления указанным обработчиком.</span><span class="sxs-lookup"><span data-stu-id="cb666-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="cb666-138">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-138">Optional.</span></span>|  
|[<span data-ttu-id="cb666-139">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="cb666-139">\<issuerNameRegistry></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuernameregistry.md)|<span data-ttu-id="cb666-140">Настраивает реестр имен издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="cb666-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="cb666-141">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-141">Optional.</span></span>|  
|[<span data-ttu-id="cb666-142">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="cb666-142">\<issuerTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/issuertokenresolver.md)|<span data-ttu-id="cb666-143">Регистрирует Сопоставитель токенов издателей, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="cb666-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="cb666-144">Сопоставитель токенов издателей используется для разрешения токена подписывания на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="cb666-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="cb666-145">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-145">Optional.</span></span>|  
|[<span data-ttu-id="cb666-146">\<serviceTokenResolver ></span><span class="sxs-lookup"><span data-stu-id="cb666-146">\<serviceTokenResolver></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicetokenresolver.md)|<span data-ttu-id="cb666-147">Регистрирует Сопоставитель токенов служб, используемый обработчиками в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="cb666-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="cb666-148">Сопоставитель токенов служб используется для разрешения токена шифрования на входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="cb666-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="cb666-149">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-149">Optional.</span></span>|  
|[<span data-ttu-id="cb666-150">\<tokenReplayDetection ></span><span class="sxs-lookup"><span data-stu-id="cb666-150">\<tokenReplayDetection></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)|<span data-ttu-id="cb666-151">Включает обнаружение воспроизведения токенов и определяет срок действия маркеров.</span><span class="sxs-lookup"><span data-stu-id="cb666-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="cb666-152">Можно указать на уровне службы или в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb666-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="cb666-153">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="cb666-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb666-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cb666-154">Parent Elements</span></span>  
  
|<span data-ttu-id="cb666-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="cb666-155">Element</span></span>|<span data-ttu-id="cb666-156">Описание</span><span class="sxs-lookup"><span data-stu-id="cb666-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cb666-157">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="cb666-157">\<securityTokenHandlers></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlers.md)|<span data-ttu-id="cb666-158">Задает коллекцию обработчиков токенов безопасности, которые зарегистрированы с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="cb666-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cb666-159">Примечания</span><span class="sxs-lookup"><span data-stu-id="cb666-159">Remarks</span></span>  
 <span data-ttu-id="cb666-160">В этом разделе содержатся значения свойств для <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> объекта.</span><span class="sxs-lookup"><span data-stu-id="cb666-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="cb666-161">Параметры, настроенные в этом разделе, переопределяют сконфигурирован в службе.</span><span class="sxs-lookup"><span data-stu-id="cb666-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="cb666-162">Некоторые из этих параметров могут в свою очередь, переопределяться параметры, заданные в случае, когда обработчик добавляется в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="cb666-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb666-163">Пример</span><span class="sxs-lookup"><span data-stu-id="cb666-163">Example</span></span>  
  
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
