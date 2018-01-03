---
title: '&lt;system.identityModel.services&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa1624dd-2d74-4ae3-942e-498cee261ac5
caps.latest.revision: "6"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 03c2fa7fe65650b760937ef06b848152893e023b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemidentitymodelservicesgt"></a><span data-ttu-id="0b1df-102">&lt;system.identityModel.services&gt;</span><span class="sxs-lookup"><span data-stu-id="0b1df-102">&lt;system.identityModel.services&gt;</span></span>
<span data-ttu-id="0b1df-103">Раздел конфигурации для проверки подлинности с помощью протокола WS-Federation.</span><span class="sxs-lookup"><span data-stu-id="0b1df-103">Configuration section for authentication using the WS-Federation protocol.</span></span>  
  
 <span data-ttu-id="0b1df-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="0b1df-104">\<system.identityModel.services></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b1df-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b1df-105">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration name=xs:string identityConfigurationName=xs:string>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b1df-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0b1df-106">Attributes and Elements</span></span>  
 <span data-ttu-id="0b1df-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0b1df-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b1df-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0b1df-108">Attributes</span></span>  
 <span data-ttu-id="0b1df-109">Нет</span><span class="sxs-lookup"><span data-stu-id="0b1df-109">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="0b1df-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0b1df-110">Child Elements</span></span>  
  
|<span data-ttu-id="0b1df-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="0b1df-111">Element</span></span>|<span data-ttu-id="0b1df-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="0b1df-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b1df-113">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="0b1df-113">\<federationConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md)|<span data-ttu-id="0b1df-114">Содержит параметры, настроенные <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) и <xref:System.IdentityModel.Services.SessionAuthenticationModule> модули HTTP (SAM).</span><span class="sxs-lookup"><span data-stu-id="0b1df-114">Contains the settings that configure the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule> (WSFAM) and the <xref:System.IdentityModel.Services.SessionAuthenticationModule> (SAM) HTTP modules.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0b1df-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0b1df-115">Parent Elements</span></span>  
 <span data-ttu-id="0b1df-116">Нет</span><span class="sxs-lookup"><span data-stu-id="0b1df-116">None</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b1df-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="0b1df-117">Remarks</span></span>  
 <span data-ttu-id="0b1df-118">Добавить `<system.identityModel.services>` раздел в файле конфигурации приложения для предоставления параметров для диспетчера учетных записей безопасности и WSFAM.</span><span class="sxs-lookup"><span data-stu-id="0b1df-118">Add a `<system.identityModel.services>` section to your application’s configuration file to provide settings for the SAM and WSFAM.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0b1df-119">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде диспетчера авторизации утверждений (<xref:System.Security.Claims.ClaimsAuthorizationManager>) и политики, которая используется для принятия решения об авторизации, настраиваются через `<identityConfiguration>` элемент, который явно или неявно ссылается `<federationConfiguration>` элемент в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0b1df-119">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the claims authorization manager (<xref:System.Security.Claims.ClaimsAuthorizationManager>) and policy that is used to make authorization decisions are configured through an `<identityConfiguration>` element that is implicitly or explicitly referenced from a `<federationConfiguration>` element in this section.</span></span> <span data-ttu-id="0b1df-120">Дополнительные сведения см. в разделе **примечания** под [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="0b1df-120">For more information, see the **Remarks** under the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="0b1df-121">`<system.identityModel.services>` Разделе представлен <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> класса.</span><span class="sxs-lookup"><span data-stu-id="0b1df-121">The `<system.identityModel.services>` section is represented by the <xref:System.IdentityModel.Services.Configuration.SystemIdentityModelServicesSection> class.</span></span> <span data-ttu-id="0b1df-122">Коллекция дочерних `<federationConfiguration>` элементы, настроенные в разделе представлен <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> класса.</span><span class="sxs-lookup"><span data-stu-id="0b1df-122">The collection of child `<federationConfiguration>` elements configured in the section is represented by the <xref:System.IdentityModel.Services.Configuration.FederationConfigurationElementCollection> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b1df-123">Пример</span><span class="sxs-lookup"><span data-stu-id="0b1df-123">Example</span></span>  
 <span data-ttu-id="0b1df-124">Следующий код XML показывает, как добавить `<system.identityModel.services>` раздел в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0b1df-124">The following XML shows how to add a `<system.identityModel.services>` section to a configuration file.</span></span> <span data-ttu-id="0b1df-125">Сначала необходимо добавить раздел объявлений для обоих `<system.identityModel.services>` раздел и `<system.identityModel>` разделы.</span><span class="sxs-lookup"><span data-stu-id="0b1df-125">You must first add section declarations for both the `<system.identityModel.services>` section and the `<system.identityModel>` sections.</span></span> <span data-ttu-id="0b1df-126">(При добавлении `<system.identityModel.services>` раздела, следует также добавить объявление для `<system.identityModel>` раздел, чтобы убедиться, что значение по умолчанию `<identityConfiguration>` раздел, создаваемых средой выполнения при необходимости.) После добавления объявления разделов, можно настроить параметры федеративной проверки подлинности в разделе `<system.identityModel.services>` элемента.</span><span class="sxs-lookup"><span data-stu-id="0b1df-126">(When you add a `<system.identityModel.services>` section, you should also add a declaration for the `<system.identityModel>` section to ensure that a default `<identityConfiguration>` section can be created by the runtime if necessary.) After the section declarations have been added, you can configure federated authentication settings under the `<system.identityModel.services>` element.</span></span>  
  
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
