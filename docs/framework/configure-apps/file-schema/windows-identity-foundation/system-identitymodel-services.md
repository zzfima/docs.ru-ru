---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: e9488c0681e1a5f0fe94112a36b65ec73bf9fd09
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251810"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="bec11-102">\<> System. identityModel. Services</span><span class="sxs-lookup"><span data-stu-id="bec11-102">\<system.identityModel.services></span></span>
<span data-ttu-id="bec11-103">Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="bec11-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="bec11-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bec11-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bec11-105">&nbsp;&nbsp; **\<> System. identityModel. Services**</span><span class="sxs-lookup"><span data-stu-id="bec11-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bec11-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bec11-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bec11-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bec11-107">Attributes and Elements</span></span>  
 <span data-ttu-id="bec11-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bec11-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bec11-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bec11-109">Attributes</span></span>  
 <span data-ttu-id="bec11-110">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="bec11-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="bec11-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bec11-111">Child Elements</span></span>  
  
|<span data-ttu-id="bec11-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="bec11-112">Element</span></span>|<span data-ttu-id="bec11-113">Описание</span><span class="sxs-lookup"><span data-stu-id="bec11-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bec11-114">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="bec11-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="bec11-115">Содержит параметры, которые настраивают <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (всфам) <xref:System.IdentityModel.Services.SessionAuthenticationModule> и HTTP-модули (SAM).</span><span class="sxs-lookup"><span data-stu-id="bec11-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bec11-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bec11-116">Parent Elements</span></span>  
 <span data-ttu-id="bec11-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="bec11-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bec11-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="bec11-118">Remarks</span></span>  
 <span data-ttu-id="bec11-119">`<system.identityModel.services>` Добавьте раздел в файл конфигурации приложения, чтобы указать параметры для SAM и всфам.</span><span class="sxs-lookup"><span data-stu-id="bec11-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bec11-120"><xref:System.IdentityModel.Services.ClaimsPrincipalPermission> При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде Диспетчер авторизации утверждений (<xref:System.Security.Claims.ClaimsAuthorizationManager>) и политика, используемые `<identityConfiguration>` для принятия решений об авторизации, настраиваются с помощью элемент, который неявно или явно указан из `<federationConfiguration>` элемента в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bec11-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="bec11-121">Дополнительные сведения см. в разделе **"Примечания** " в [ \<элементе > federationConfiguration](federationconfiguration.md) .</span><span class="sxs-lookup"><span data-stu-id="bec11-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="bec11-122">`<system.identityModel.services>` Раздел представлен<xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> классом.</span><span class="sxs-lookup"><span data-stu-id="bec11-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="bec11-123">Коллекция дочерних `<federationConfiguration>` элементов, настроенных в разделе, представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="bec11-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bec11-124">Пример</span><span class="sxs-lookup"><span data-stu-id="bec11-124">Example</span></span>  
 <span data-ttu-id="bec11-125">В следующем коде XML показано, как добавить `<system.identityModel.services>` раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bec11-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="bec11-126">Сначала необходимо добавить объявления разделов как для `<system.identityModel.services>` раздела `<system.identityModel>` , так и для разделов.</span><span class="sxs-lookup"><span data-stu-id="bec11-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="bec11-127">(При добавлении `<system.identityModel.services>` раздела необходимо также добавить объявление `<system.identityModel>` для раздела, чтобы гарантировать, что при необходимости раздел по умолчанию `<identityConfiguration>` может быть создан средой выполнения.) После добавления объявлений разделов можно настроить параметры федеративной проверки подлинности в `<system.identityModel.services>` элементе.</span><span class="sxs-lookup"><span data-stu-id="bec11-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
```xml  
<configuration>  
  <configSections>  
    <section name="system.identityModel" type="System.IdentityModel.Configuration.SystemIdentityModelSection, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
    <section name="system.identityModel.services" type="System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection, System.IdentityModel.Services, Version=4.0.0.0, Culture=neutral, PublicKeyToken=B77A5C561934E089" />  
  </configSections>  
  
  <!-- Additional elements (not shown) -->  
  
  <system.identityModel.services>  
    <federationConfiguration>  
      <wsFederation passiveRedirectEnabled="true"   
        issuer="http://localhost:15839/wsFederationSTS/Issue"   
        realm="http://localhost:50969/" reply="http://localhost:50969/"   
        requireHttps="false"   
        signOutReply="http://localhost:50969/SignedOutPage.html"   
        signOutQueryString="Param1=value2&Param2=value2"   
        persistentCookiesOnPassiveRedirects="true" />  
      <cookieHandler requireSsl="false" />  
    </federationConfiguration>  
  </system.identityModel.services>  
  
</configuration>  
```
