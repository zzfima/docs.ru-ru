---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: 330e52bd73a8032e4073fe434c852e5bdf8e1d47
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251891"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="e73f9-101">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="e73f9-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="e73f9-102">Предоставляет конфигурацию для коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e73f9-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="e73f9-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e73f9-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e73f9-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="e73f9-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="e73f9-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="e73f9-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="e73f9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="e73f9-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="e73f9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Секурититокенхандлерконфигуратион >**</span><span class="sxs-lookup"><span data-stu-id="e73f9-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e73f9-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e73f9-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e73f9-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e73f9-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e73f9-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e73f9-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e73f9-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e73f9-111">Attributes</span></span>  
  
|<span data-ttu-id="e73f9-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e73f9-112">Attribute</span></span>|<span data-ttu-id="e73f9-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e73f9-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e73f9-114">савебутстрапконтекст</span><span class="sxs-lookup"><span data-stu-id="e73f9-114">saveBootstrapContext</span></span>|<span data-ttu-id="e73f9-115">Указывает, следует ли включать в маркер сеанса начальные токены.</span><span class="sxs-lookup"><span data-stu-id="e73f9-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="e73f9-116">Значение также может быть задано в коллекции обработчиков маркеров путем установки `saveBootstrapContext` атрибута [ \<для элемента identityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="e73f9-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="e73f9-117">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="e73f9-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="e73f9-118">максимумклоккскев</span><span class="sxs-lookup"><span data-stu-id="e73f9-118">maximumClockSkew</span></span>|<span data-ttu-id="e73f9-119">Значение <xref:System.TimeSpan> типа, указывающее максимально допустимую отклонение в часах.</span><span class="sxs-lookup"><span data-stu-id="e73f9-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="e73f9-120">Управляет максимально разрешенным отклонением по часам при выполнении операций с учетом времени, таких как проверка срока действия сеанса входа.</span><span class="sxs-lookup"><span data-stu-id="e73f9-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="e73f9-121">Значение по умолчанию — 5 минут, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="e73f9-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="e73f9-122">Дополнительные сведения об указании <xref:System.TimeSpan> значений см. в разделе [значения TimeSpan](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="e73f9-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="e73f9-123">Максимальная разница в часах может также быть задана на уровне службы путем задания `maximumClockSkew` атрибута [ \<для элемента identityConfiguration >](identityconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="e73f9-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="e73f9-124">Значение, заданное в коллекции обработчиков маркеров, переопределяет значение, заданное для службы.</span><span class="sxs-lookup"><span data-stu-id="e73f9-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e73f9-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e73f9-125">Child Elements</span></span>  
  
|<span data-ttu-id="e73f9-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e73f9-126">Element</span></span>|<span data-ttu-id="e73f9-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e73f9-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e73f9-128">\<audienceUris ></span><span class="sxs-lookup"><span data-stu-id="e73f9-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="e73f9-129">Указывает набор универсальных кодов ресурса (URI), которые являются допустимыми идентификаторами этой проверяющей стороны.</span><span class="sxs-lookup"><span data-stu-id="e73f9-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="e73f9-130">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-130">Optional.</span></span>|  
|[<span data-ttu-id="e73f9-131">\<> кэшей</span><span class="sxs-lookup"><span data-stu-id="e73f9-131">\<caches></span></span>](caches.md)|<span data-ttu-id="e73f9-132">Регистрирует кэши, используемые для маркеров сеансов и определения воспроизведения маркеров.</span><span class="sxs-lookup"><span data-stu-id="e73f9-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="e73f9-133">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e73f9-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e73f9-134">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-134">Optional.</span></span>|  
|[<span data-ttu-id="e73f9-135">\<Цертификатевалидатион ></span><span class="sxs-lookup"><span data-stu-id="e73f9-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="e73f9-136">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e73f9-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="e73f9-137">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e73f9-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e73f9-138">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e73f9-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="e73f9-139">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-139">Optional.</span></span>|  
|[<span data-ttu-id="e73f9-140">\<issuerNameRegistry ></span><span class="sxs-lookup"><span data-stu-id="e73f9-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="e73f9-141">Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e73f9-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e73f9-142">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-142">Optional.</span></span>|  
|[<span data-ttu-id="e73f9-143">\<Иссуертокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="e73f9-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="e73f9-144">Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e73f9-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e73f9-145">Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="e73f9-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="e73f9-146">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-146">Optional.</span></span>|  
|[<span data-ttu-id="e73f9-147">\<Сервицетокенресолвер ></span><span class="sxs-lookup"><span data-stu-id="e73f9-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="e73f9-148">Регистрирует сопоставитель маркеров службы, используемый обработчиками в коллекции обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="e73f9-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="e73f9-149">Сопоставитель токенов службы используется для разрешения маркера шифрования входящих токенов и сообщений.</span><span class="sxs-lookup"><span data-stu-id="e73f9-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="e73f9-150">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-150">Optional.</span></span>|  
|[<span data-ttu-id="e73f9-151">\<Токенреплайдетектион ></span><span class="sxs-lookup"><span data-stu-id="e73f9-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="e73f9-152">Включает обнаружение воспроизведения маркеров и задает срок действия токенов.</span><span class="sxs-lookup"><span data-stu-id="e73f9-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="e73f9-153">Может указываться на уровне службы или в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e73f9-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="e73f9-154">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="e73f9-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e73f9-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e73f9-155">Parent Elements</span></span>  
  
|<span data-ttu-id="e73f9-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="e73f9-156">Element</span></span>|<span data-ttu-id="e73f9-157">Описание</span><span class="sxs-lookup"><span data-stu-id="e73f9-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e73f9-158">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="e73f9-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="e73f9-159">Указывает коллекцию обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="e73f9-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e73f9-160">Примечания</span><span class="sxs-lookup"><span data-stu-id="e73f9-160">Remarks</span></span>  
 <span data-ttu-id="e73f9-161">В <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> этом разделе приводятся значения свойств для объекта.</span><span class="sxs-lookup"><span data-stu-id="e73f9-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="e73f9-162">Параметры, настроенные в этом разделе, переопределяют настройки, настроенные в службе.</span><span class="sxs-lookup"><span data-stu-id="e73f9-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="e73f9-163">Некоторые из этих параметров, в свою очередь, могут быть переопределены параметрами, заданными при добавлении обработчика в коллекцию обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="e73f9-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e73f9-164">Пример</span><span class="sxs-lookup"><span data-stu-id="e73f9-164">Example</span></span>  
  
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
