---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 0aefaa808dfc32085a208420fcd582b1671acc64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942445"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="aa920-101">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="aa920-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="aa920-102">Предоставляет конфигурацию для коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="aa920-102">Provides configuration for the collection of token handlers.</span></span>  
  
 <span data-ttu-id="aa920-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="aa920-103">\<system.identityModel></span></span>  
<span data-ttu-id="aa920-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="aa920-104">\<identityConfiguration></span></span>  
<span data-ttu-id="aa920-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="aa920-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="aa920-106">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="aa920-106">\<securityTokenHandlerConfiguration></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa920-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aa920-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aa920-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aa920-108">Attributes and Elements</span></span>  
 <span data-ttu-id="aa920-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aa920-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aa920-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aa920-110">Attributes</span></span>  
  
|<span data-ttu-id="aa920-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aa920-111">Attribute</span></span>|<span data-ttu-id="aa920-112">Описание</span><span class="sxs-lookup"><span data-stu-id="aa920-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aa920-113">савебутстрапконтекст</span><span class="sxs-lookup"><span data-stu-id="aa920-113">saveBootstrapContext</span></span>|<span data-ttu-id="aa920-114">Указывает, следует ли включать в маркер сеанса начальные токены.</span><span class="sxs-lookup"><span data-stu-id="aa920-114">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="aa920-115">Значение также может быть задано в коллекции обработчиков маркеров путем установки `saveBootstrapContext` атрибута [ \<для элемента identityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="aa920-115">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="aa920-116">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="aa920-116">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="aa920-117">максимумклоккскев</span><span class="sxs-lookup"><span data-stu-id="aa920-117">maximumClockSkew</span></span>|<span data-ttu-id="aa920-118">Значение <xref:System.TimeSpan> типа, указывающее максимально допустимую отклонение в часах.</span><span class="sxs-lookup"><span data-stu-id="aa920-118">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="aa920-119">Управляет максимально разрешенным отклонением по часам при выполнении операций с учетом времени, таких как проверка срока действия сеанса входа.</span><span class="sxs-lookup"><span data-stu-id="aa920-119">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="aa920-120">Значение по умолчанию — 5 минут, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="aa920-120">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="aa920-121">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="aa920-121">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="aa920-122">Максимальная разница в часах может также быть задана на уровне службы путем задания `maximumClockSkew` атрибута [ \<для элемента identityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="aa920-122">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="aa920-123">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="aa920-123">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aa920-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aa920-124">Child Elements</span></span>  
  
|<span data-ttu-id="aa920-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa920-125">Element</span></span>|<span data-ttu-id="aa920-126">Описание</span><span class="sxs-lookup"><span data-stu-id="aa920-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa920-127">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="aa920-127">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="aa920-128">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами этой проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="aa920-128">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="aa920-129">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-129">Optional.</span></span>|  
|[<span data-ttu-id="aa920-130">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="aa920-130">\<caches></span></span>](caches.md)|<span data-ttu-id="aa920-131">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="aa920-131">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="aa920-132">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa920-132">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="aa920-133">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-133">Optional.</span></span>|  
|[<span data-ttu-id="aa920-134">\<Цертификатевалидатион ></span><span class="sxs-lookup"><span data-stu-id="aa920-134">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="aa920-135">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="aa920-135">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="aa920-136">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa920-136">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="aa920-137">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="aa920-137">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="aa920-138">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-138">Optional.</span></span>|  
|[<span data-ttu-id="aa920-139">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="aa920-139">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="aa920-140">Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="aa920-140">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="aa920-141">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-141">Optional.</span></span>|  
|[<span data-ttu-id="aa920-142">\<Иссуертокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="aa920-142">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="aa920-143">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="aa920-143">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="aa920-144">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="aa920-144">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="aa920-145">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-145">Optional.</span></span>|  
|[<span data-ttu-id="aa920-146">\<Сервицетокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="aa920-146">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="aa920-147">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="aa920-147">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="aa920-148">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="aa920-148">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="aa920-149">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-149">Optional.</span></span>|  
|[<span data-ttu-id="aa920-150">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="aa920-150">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="aa920-151">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="aa920-151">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="aa920-152">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa920-152">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="aa920-153">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="aa920-153">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="aa920-154">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aa920-154">Parent Elements</span></span>  
  
|<span data-ttu-id="aa920-155">Элемент</span><span class="sxs-lookup"><span data-stu-id="aa920-155">Element</span></span>|<span data-ttu-id="aa920-156">Описание</span><span class="sxs-lookup"><span data-stu-id="aa920-156">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aa920-157">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="aa920-157">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="aa920-158">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="aa920-158">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aa920-159">Примечания</span><span class="sxs-lookup"><span data-stu-id="aa920-159">Remarks</span></span>  
 <span data-ttu-id="aa920-160">В <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> этом разделе приводятся значения свойств для объекта.</span><span class="sxs-lookup"><span data-stu-id="aa920-160">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="aa920-161">Параметры, настроенные в этом разделе, переопределяют настройки, настроенные в службе.</span><span class="sxs-lookup"><span data-stu-id="aa920-161">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="aa920-162">Некоторые из этих параметров, в свою очередь, могут быть переопределены параметрами, заданными при добавлении обработчика в коллекцию обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa920-162">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aa920-163">Пример</span><span class="sxs-lookup"><span data-stu-id="aa920-163">Example</span></span>  
  
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
