---
title: <system.identityModel.services>
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
ms.openlocfilehash: 57757aaec39bc5c552e7ba12c9779cb3a92a9025
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152508"
---
# <a name="systemidentitymodelservices"></a><span data-ttu-id="b12cc-102">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="b12cc-102">\<system.identityModel.services></span></span>
<span data-ttu-id="b12cc-103">Раздел конфигурации для проверки подлинности с использованием протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="b12cc-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
<span data-ttu-id="b12cc-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b12cc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b12cc-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span><span class="sxs-lookup"><span data-stu-id="b12cc-105">&nbsp;&nbsp;**\<system.identityModel.services>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12cc-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b12cc-106">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b12cc-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b12cc-107">Attributes and Elements</span></span>  
 <span data-ttu-id="b12cc-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b12cc-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b12cc-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b12cc-109">Attributes</span></span>  
 <span data-ttu-id="b12cc-110">None</span><span class="sxs-lookup"><span data-stu-id="b12cc-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b12cc-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b12cc-111">Child Elements</span></span>  
  
|<span data-ttu-id="b12cc-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="b12cc-112">Element</span></span>|<span data-ttu-id="b12cc-113">Описание</span><span class="sxs-lookup"><span data-stu-id="b12cc-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b12cc-114">\<федерацияКонфигурация></span><span class="sxs-lookup"><span data-stu-id="b12cc-114">\<federationConfiguration></span></span>](federationconfiguration.md)|<span data-ttu-id="b12cc-115">Содержит настройки, настраивающие <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> модули (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP.</span><span class="sxs-lookup"><span data-stu-id="b12cc-115">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b12cc-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b12cc-116">Parent Elements</span></span>  
 <span data-ttu-id="b12cc-117">None</span><span class="sxs-lookup"><span data-stu-id="b12cc-117">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b12cc-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="b12cc-118">Remarks</span></span>  
 <span data-ttu-id="b12cc-119">Добавьте `<system.identityModel.services>` раздел в файл конфигурации приложения, чтобы предоставить настройки для SAM и WSFAM.</span><span class="sxs-lookup"><span data-stu-id="b12cc-119">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b12cc-120">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> или класса для обеспечения элемента доступа на основе<xref:System.Security.Claims.ClaimsAuthorizationManager>утверждений в коде менеджер авторизации претензий () и политика, используемая для принятия решений о авторизации, настраиваются через `<identityConfiguration>` элемент, на который косвенно или явно ссылается `<federationConfiguration>` элемент в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b12cc-120">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="b12cc-121">Для получения дополнительной **информации** см [ \<>.](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="b12cc-121">For more information, see the **Remarks** under the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="b12cc-122">Раздел `<system.identityModel.services>` представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> классом.</span><span class="sxs-lookup"><span data-stu-id="b12cc-122">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="b12cc-123">Коллекция элементов `<federationConfiguration>` ребенка, настроенная в разделе, представлена <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> классом.</span><span class="sxs-lookup"><span data-stu-id="b12cc-123">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b12cc-124">Пример</span><span class="sxs-lookup"><span data-stu-id="b12cc-124">Example</span></span>  
 <span data-ttu-id="b12cc-125">В следующем XML показано, `<system.identityModel.services>` как добавить раздел в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b12cc-125">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="b12cc-126">Сначала необходимо добавить объявления раздела как для раздела, `<system.identityModel.services>` так и для разделов. `<system.identityModel>`</span><span class="sxs-lookup"><span data-stu-id="b12cc-126">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="b12cc-127">(При добавлении раздела `<system.identityModel.services>` следует также добавить декларацию для `<system.identityModel>` раздела, чтобы при необходимости можно было создать раздел по умолчанию `<identityConfiguration>` к времени выполнения.) После добавления объявлений раздела можно настроить настройки федеративной аутентификации под элементом. `<system.identityModel.services>`</span><span class="sxs-lookup"><span data-stu-id="b12cc-127">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
