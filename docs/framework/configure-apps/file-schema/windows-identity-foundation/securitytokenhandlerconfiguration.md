---
title: <securityTokenHandlerConfiguration>
ms.date: 03/30/2017
ms.assetid: 28724cc6-020c-4a06-9a1f-d7594f315019
author: BrucePerlerMS
ms.openlocfilehash: e3e65820fa4dc341371d4f67689a288cd3f63951
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152571"
---
# <a name="securitytokenhandlerconfiguration"></a><span data-ttu-id="6072e-101">\<securityTokenhandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="6072e-101">\<securityTokenHandlerConfiguration></span></span>
<span data-ttu-id="6072e-102">Обеспечивает конфигурацию для сбора обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="6072e-102">Provides configuration for the collection of token handlers.</span></span>  
  
<span data-ttu-id="6072e-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6072e-104">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="6072e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="6072e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="6072e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenhandlerConfiguration>**</span><span class="sxs-lookup"><span data-stu-id="6072e-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<securityTokenHandlerConfiguration>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6072e-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6072e-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6072e-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6072e-109">Attributes and Elements</span></span>  
 <span data-ttu-id="6072e-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6072e-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6072e-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6072e-111">Attributes</span></span>  
  
|<span data-ttu-id="6072e-112">attribute</span><span class="sxs-lookup"><span data-stu-id="6072e-112">Attribute</span></span>|<span data-ttu-id="6072e-113">Описание</span><span class="sxs-lookup"><span data-stu-id="6072e-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6072e-114">saveBootstrapКонтекст</span><span class="sxs-lookup"><span data-stu-id="6072e-114">saveBootstrapContext</span></span>|<span data-ttu-id="6072e-115">Определяет, следует ли включать токены bootstrap в токен сеанса.</span><span class="sxs-lookup"><span data-stu-id="6072e-115">Specifies whether bootstrap tokens should be included in the session token.</span></span> <span data-ttu-id="6072e-116">Значение также может быть установлено на коллекции `saveBootstrapContext` обработчика маркеров, установив атрибут на элементе [ \<конфигурации>.](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-116">The value may also be set on a token handler collection by setting the `saveBootstrapContext` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="6072e-117">Значение, установленное в коллекции обработчика токенов, переопределяет значение, установленное в службе.</span><span class="sxs-lookup"><span data-stu-id="6072e-117">A value set on the token handler collection overrides the value set on the service.</span></span>|  
|<span data-ttu-id="6072e-118">maximumClockSkew</span><span class="sxs-lookup"><span data-stu-id="6072e-118">maximumClockSkew</span></span>|<span data-ttu-id="6072e-119">A, <xref:System.TimeSpan> который определяет максимально допустимые перекосы часов.</span><span class="sxs-lookup"><span data-stu-id="6072e-119">A <xref:System.TimeSpan> that specifies the maximum allowed clock skew.</span></span> <span data-ttu-id="6072e-120">Контролирует максимально допустимые перекосы часов при выполнении операций, чувствительных к времени, таких как проверка времени истечения сеанса входе.</span><span class="sxs-lookup"><span data-stu-id="6072e-120">Controls the maximum allowed clock skew when performing time-sensitive operations, such as validating the expiration time of a sign-in session.</span></span> <span data-ttu-id="6072e-121">По умолчанию 5 минут, "00:05:00".</span><span class="sxs-lookup"><span data-stu-id="6072e-121">The default is 5 minutes, "00:05:00".</span></span> <span data-ttu-id="6072e-122">Для получения дополнительной информации о том, как указать <xref:System.TimeSpan> значения, см. [Timespan Values](../windows-workflow-foundation/index.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-122">For more information about how to specify <xref:System.TimeSpan> values, see [Timespan Values](../windows-workflow-foundation/index.md).</span></span> <span data-ttu-id="6072e-123">Максимальное перекос часов также может быть установлен `maximumClockSkew` на уровне обслуживания, установив атрибут на [ \<элементе конфигурации>.](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="6072e-123">The maximum clock skew may also be set at the service level by setting the `maximumClockSkew` attribute on the [\<identityConfiguration>](identityconfiguration.md) element.</span></span> <span data-ttu-id="6072e-124">Значение, установленное в коллекции обработчика токенов, переопределяет значение, установленное в службе.</span><span class="sxs-lookup"><span data-stu-id="6072e-124">A value set on the token handler collection overrides the value set on the service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6072e-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6072e-125">Child Elements</span></span>  
  
|<span data-ttu-id="6072e-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="6072e-126">Element</span></span>|<span data-ttu-id="6072e-127">Описание</span><span class="sxs-lookup"><span data-stu-id="6072e-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6072e-128">\<аудиторияУрис></span><span class="sxs-lookup"><span data-stu-id="6072e-128">\<audienceUris></span></span>](audienceuris.md)|<span data-ttu-id="6072e-129">Определяет набор УРИ, которые являются приемлемыми идентификаторами этой полагающейся стороны.</span><span class="sxs-lookup"><span data-stu-id="6072e-129">Specifies the set of URIs that are acceptable identifiers of this relying party.</span></span> <span data-ttu-id="6072e-130">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-130">Optional.</span></span>|  
|[<span data-ttu-id="6072e-131">\<кэши></span><span class="sxs-lookup"><span data-stu-id="6072e-131">\<caches></span></span>](caches.md)|<span data-ttu-id="6072e-132">Регистрирует кэши, используемые для маркеров сеанса и обнаружения воспроизведения токенов.</span><span class="sxs-lookup"><span data-stu-id="6072e-132">Registers the caches used for session tokens and token replay detection.</span></span> <span data-ttu-id="6072e-133">Может быть указан на уровне обслуживания или в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6072e-133">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6072e-134">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-134">Optional.</span></span>|  
|[<span data-ttu-id="6072e-135">\<сертификатВалиста></span><span class="sxs-lookup"><span data-stu-id="6072e-135">\<certificateValidation></span></span>](certificatevalidation.md)|<span data-ttu-id="6072e-136">Контролирует настройки, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6072e-136">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="6072e-137">Может быть указан на уровне обслуживания или в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6072e-137">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6072e-138">Эти параметры переопределяются, если определенный обработчик настроен с собственным валидатором.</span><span class="sxs-lookup"><span data-stu-id="6072e-138">These settings are overridden if a specific handler is configured with its own validator.</span></span> <span data-ttu-id="6072e-139">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-139">Optional.</span></span>|  
|[<span data-ttu-id="6072e-140">\<>эмитентаNameRegistry</span><span class="sxs-lookup"><span data-stu-id="6072e-140">\<issuerNameRegistry></span></span>](issuernameregistry.md)|<span data-ttu-id="6072e-141">Настраивает реестр имен эмитента, который используется обработчиками в коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="6072e-141">Configures the issuer name registry that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6072e-142">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-142">Optional.</span></span>|  
|[<span data-ttu-id="6072e-143">\<issuerTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6072e-143">\<issuerTokenResolver></span></span>](issuertokenresolver.md)|<span data-ttu-id="6072e-144">Регистрирует токен-решателя эмитента, который используется обработчиками в коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="6072e-144">Registers the issuer token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6072e-145">Разрешители маркеров эмитента используются для разрешения маркера подписи на входящих токенах и сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6072e-145">The issuer token resolver is used to resolve the signing token on incoming tokens and messages.</span></span> <span data-ttu-id="6072e-146">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-146">Optional.</span></span>|  
|[<span data-ttu-id="6072e-147">\<serviceTokenResolver></span><span class="sxs-lookup"><span data-stu-id="6072e-147">\<serviceTokenResolver></span></span>](servicetokenresolver.md)|<span data-ttu-id="6072e-148">Регистрирует разрешителер маркеров службы, используемый обработчиками в коллекции обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="6072e-148">Registers the service token resolver that is used by handlers in the token handler collection.</span></span> <span data-ttu-id="6072e-149">Разрешители токенов службы используются для разрешения маркера шифрования на входящих токенах и сообщениях.</span><span class="sxs-lookup"><span data-stu-id="6072e-149">The service token resolver is used to resolve the encryption token on incoming tokens and messages.</span></span> <span data-ttu-id="6072e-150">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-150">Optional.</span></span>|  
|[<span data-ttu-id="6072e-151">\<токенReplayDetection></span><span class="sxs-lookup"><span data-stu-id="6072e-151">\<tokenReplayDetection></span></span>](tokenreplaydetection.md)|<span data-ttu-id="6072e-152">Позволяет обнаружить маркеры и определяет время истечения срока действия токенов.</span><span class="sxs-lookup"><span data-stu-id="6072e-152">Enables token replay detection and specifies the expiration time for tokens.</span></span> <span data-ttu-id="6072e-153">Может быть указан на уровне обслуживания или в коллекции обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6072e-153">Can be specified at the service-level or on a security token handler collection.</span></span> <span data-ttu-id="6072e-154">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="6072e-154">Optional.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6072e-155">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6072e-155">Parent Elements</span></span>  
  
|<span data-ttu-id="6072e-156">Элемент</span><span class="sxs-lookup"><span data-stu-id="6072e-156">Element</span></span>|<span data-ttu-id="6072e-157">Описание</span><span class="sxs-lookup"><span data-stu-id="6072e-157">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6072e-158">\<securityTokenHandlers></span><span class="sxs-lookup"><span data-stu-id="6072e-158">\<securityTokenHandlers></span></span>](securitytokenhandlers.md)|<span data-ttu-id="6072e-159">Определяет набор обработчиков маркеров безопасности, зарегистрированных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="6072e-159">Specifies a collection of security token handlers that are registered with the endpoint.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6072e-160">Remarks</span><span class="sxs-lookup"><span data-stu-id="6072e-160">Remarks</span></span>  
 <span data-ttu-id="6072e-161">В этом разделе приведены <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> значения свойств для объекта.</span><span class="sxs-lookup"><span data-stu-id="6072e-161">This section provides property values for a <xref:System.IdentityModel.Tokens.SecurityTokenHandlerConfiguration> object.</span></span> <span data-ttu-id="6072e-162">Настройки, настроенные в этом разделе, переопределяют настройки, настроенные на службу.</span><span class="sxs-lookup"><span data-stu-id="6072e-162">Settings configured in this section override those configured on the service.</span></span> <span data-ttu-id="6072e-163">Некоторые из этих параметров, в свою очередь, могут быть перекрыты настройками, которые указаны при добавлении обработчика в коллекцию обработчика маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="6072e-163">Some of these settings can, in turn, be overridden by settings that are specified when a handler is added to the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6072e-164">Пример</span><span class="sxs-lookup"><span data-stu-id="6072e-164">Example</span></span>  
  
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
