---
title: Схема конфигурации Windows Identity Foundation
ms.date: 03/30/2017
ms.assetid: 4d4f6d76-49a5-4bad-b345-097b2e2844e9
author: BrucePerlerMS
ms.openlocfilehash: 14d596ae77019932d169e1a84732fb8522bfc46c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152727"
---
# <a name="windows-identity-foundation-configuration-schema"></a><span data-ttu-id="ec5a9-102">Схема конфигурации Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="ec5a9-102">Windows Identity Foundation Configuration Schema</span></span>

<span data-ttu-id="ec5a9-103">В представленных в этом разделе статьях приводятся сведения о схеме конфигурации Windows Identity Foundation (WIF).</span><span class="sxs-lookup"><span data-stu-id="ec5a9-103">The topics in this section provide information about the Windows Identity Foundation (WIF) configuration schema.</span></span> <span data-ttu-id="ec5a9-104">Можно также настроить приложение для использования WIF через классы, подверженные фрейму.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-104">You can also configure an application to use WIF through classes exposed by the framework.</span></span> <span data-ttu-id="ec5a9-105">Эти классы указываются в разделах, посвященных соответствующим элементам схемы.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-105">These classes are noted in the sections that treat relevant elements in the schema.</span></span> <span data-ttu-id="ec5a9-106">Ниже показана базовая структура тегов XML, предоставляемая схемой конфигурации WIF.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-106">The following shows the basic XML tag structure exposed by the WIF configuration schema.</span></span> <span data-ttu-id="ec5a9-107">Атрибуты не приводятся.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-107">Attributes are omitted.</span></span> <span data-ttu-id="ec5a9-108">Выделенные комментарии указывают на основные компоненты схемы.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-108">Highlighted comments indicate major components of the schema.</span></span>  
  
```xml  
<configuration>  
    <system.identityModel>  
        <!-- Service Configuration -->  
        <identityConfiguration>  
            <caches>  
                <sessionSecurityTokenCache />  
                <tokenReplayCache />  
            </caches>  

            <certificateValidation>  
                <certificateValidator />
            </certificateValidation>  

            <claimsAuthenticationManager />  

            <claimsAuthorizationManager>  
                <optionalConfigurationElement>  
            </claimsAuthorizationManager>  

            <claimTypeRequired>  
                <claimType />
            </claimTypeRequired>  

            <tokenReplayDetection />  

            <!-- Security Token Handler Collection Configuration -->  
            <securityTokenHandlers>  
                <add>  
                    <!-- Can take an optional configuration element which can be one of  
                         the following or a custom element -->  
                    <samlSecurityTokenHandlerRequirement>  
                        <nameClaimType>  
                        <roleClaimType>
                    </samlSecurityTokenHandlerRequirement>  

                    <sessionSecurityTokenHandlerRequirement />  
                    <x509SecurityTokenHandlerRequirement />  
                    <userNameSecurityTokenHandlerRequirement />  
                </add>  
                <clear />  
                <remove />  
                <securityTokenHandlerConfiguration>  
                    <audienceUris>  
                        <add>  
                        <clear>  
                        <remove>  
                    </audienceUris>  

                    <caches>  
                        <sessionSecurityTokenCache />  
                        <tokenReplayCache />  
                    </caches>  

                    <certificateValidation>  
                        <certificateValidator>
                    </certificateValidation>  

                    <issuerNameRegistry>  
                        <!-- Can take an optional configuration element which can be   
                             the <trustedIssuers> element to configure a configuration-based  
                             issuer name registry or can be a custom element -->  
                        <trustedIssuers>  
                            <add>  
                            <clear>  
                            <remove>  
                        </trustedIssuers>  
                    </issuerNameRegistry>  

                    <issuerTokenResolver />  
                    <serviceTokenResolver />  
                    <tokenReplayDetection />  
                </securityTokenHandlerConfiguration>  
            </securityTokenHandlers>  
        </identityConfiguration>  
    </system.identityModel>  

    <system.identityModel.services>  
        <!-- Federation Authentication Configuration -->  
        <federatedAuthentication>  
            <cookieHandler>  
                <chunkedCookieHandler />  
                <customCookieHandler />  
            </cookieHandler>  

            <serviceCertificate>  
                <certificateReference>  
            </serviceCertificate>  

            <wsFederation />  
        </federatedAuthentication>  
    </system.identityModel.services>  
</configuration>  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="ec5a9-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="ec5a9-109">In This Section</span></span>  

<span data-ttu-id="ec5a9-110">[ \<system.identityМодель>](system-identitymodel.md) Обеспечивает конфигурацию для включения параметров WIF в приложениях.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-110">[\<system.identityModel>](system-identitymodel.md) Provides configuration for enabling WIF options in applications.</span></span>  
  
<span data-ttu-id="ec5a9-111">[ \<system.identityModel.services>](system-identitymodel-services.md) Обеспечивает конфигурацию для пассивной федерации с помощью WIF.</span><span class="sxs-lookup"><span data-stu-id="ec5a9-111">[\<system.identityModel.services>](system-identitymodel-services.md) Provides configuration for passive federation using WIF.</span></span> <span data-ttu-id="ec5a9-112">Настраивает модуль проверки подлинности сеансов (SAM) и модуль федеративной проверки подлинности (WSFAM).</span><span class="sxs-lookup"><span data-stu-id="ec5a9-112">Configures the Session Authentication Module (SAM) and the Federated Authentication Module (WSFAM).</span></span>
