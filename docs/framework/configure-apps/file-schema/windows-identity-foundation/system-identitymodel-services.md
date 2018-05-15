---
title: '&lt;system.identityModel.services&gt;'
ms.date: 03/30/2017
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: ca108d7dd0498b0d7c08bb632ab45c7229ff58c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemidentitymodelservicesgt"></a><span data-ttu-id="f6764-102">&lt;system.identityModel.services&gt;</span><span class="sxs-lookup"><span data-stu-id="f6764-102">&lt;system.identityModel.services&gt;</span></span>
<span data-ttu-id="f6764-103">Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="f6764-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="f6764-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="f6764-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6764-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f6764-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f6764-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f6764-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f6764-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f6764-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f6764-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f6764-108">Attributes</span></span>  
 <span data-ttu-id="f6764-109">Нет</span><span class="sxs-lookup"><span data-stu-id="f6764-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f6764-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f6764-110">Child Elements</span></span>  
  
|<span data-ttu-id="f6764-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="f6764-111">Element</span></span>|<span data-ttu-id="f6764-112">Описание</span><span class="sxs-lookup"><span data-stu-id="f6764-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f6764-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="f6764-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="f6764-114">Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> модули HTTP (SAM).</span><span class="sxs-lookup"><span data-stu-id="f6764-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f6764-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f6764-115">Parent Elements</span></span>  
 <span data-ttu-id="f6764-116">Нет</span><span class="sxs-lookup"><span data-stu-id="f6764-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f6764-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="f6764-117">Remarks</span></span>  
 <span data-ttu-id="f6764-118">Добавить `<system.identityModel.services>` раздел в файле конфигурации приложения для предоставления параметров для диспетчера учетных записей безопасности и WSFAM.</span><span class="sxs-lookup"><span data-stu-id="f6764-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f6764-119">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде диспетчера авторизации утверждений (<xref:System.Security.Claims.ClaimsAuthorizationManager>) и политики, которая используется для принятия решения об авторизации, настраиваются через `<identityConfiguration>` элемент, который явно или неявно ссылается `<federationConfiguration>` элемент в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="f6764-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="f6764-120">Дополнительные сведения см. в разделе **примечания** под [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="f6764-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="f6764-121">`<system.identityModel.services>` Разделе представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> класса.</span><span class="sxs-lookup"><span data-stu-id="f6764-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="f6764-122">Коллекция дочерних `<federationConfiguration>` элементы, настроенные в разделе представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="f6764-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6764-123">Пример</span><span class="sxs-lookup"><span data-stu-id="f6764-123">Example</span></span>  
 <span data-ttu-id="f6764-124">Следующий код XML показывает, как добавить `<system.identityModel.services>` раздел в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f6764-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="f6764-125">Сначала необходимо добавить раздел объявлений для обоих `<system.identityModel.services>` раздел и `<system.identityModel>` разделы.</span><span class="sxs-lookup"><span data-stu-id="f6764-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="f6764-126">(При добавлении `<system.identityModel.services>` раздела, следует также добавить объявление для `<system.identityModel>` раздел, чтобы убедиться, что значение по умолчанию `<identityConfiguration>` раздел, создаваемых средой выполнения при необходимости.) После добавления объявления разделов, можно настроить параметры федеративной проверки подлинности в разделе `<system.identityModel.services>` элемента.</span><span class="sxs-lookup"><span data-stu-id="f6764-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
