---
title: '&lt;certificateValidation&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 7a5d31bce5f71e644b40b3aa7e7c0c1c8790cab6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="3bee1-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="3bee1-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="3bee1-103">Управляет параметрами обработчиков токенов, используемых для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3bee1-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="3bee1-104">Эти параметры переопределяются, если обработчик конкретного настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="3bee1-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="3bee1-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="3bee1-105">\<system.identityModel></span></span>  
<span data-ttu-id="3bee1-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3bee1-106">\<identityConfiguration></span></span>  
<span data-ttu-id="3bee1-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="3bee1-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bee1-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bee1-108">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <certificateValidation  
      certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
      revocationMode="NoCheck||Offline||Online"  
      trustedStoreLocation="CurrentLocation||LocalMachine" >  
    </certificateValidation>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3bee1-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3bee1-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3bee1-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3bee1-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3bee1-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3bee1-111">Attributes</span></span>  
  
|<span data-ttu-id="3bee1-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3bee1-112">Attribute</span></span>|<span data-ttu-id="3bee1-113">Описание:</span><span class="sxs-lookup"><span data-stu-id="3bee1-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3bee1-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3bee1-114">certificateValidationMode</span></span>|<span data-ttu-id="3bee1-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, указывающее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="3bee1-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="3bee1-116">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="3bee1-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="3bee1-117">Чтобы указать настраиваемый проверяющий элемент управления, присвоить этому атрибуту «Custom» и укажите с помощью проверяющего элемента управления [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="3bee1-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="3bee1-118">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3bee1-118">Optional.</span></span>|  
|<span data-ttu-id="3bee1-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="3bee1-119">revocationMode</span></span>|<span data-ttu-id="3bee1-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, указывающее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="3bee1-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="3bee1-121">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="3bee1-121">The default value is "Online".</span></span> <span data-ttu-id="3bee1-122">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3bee1-122">Optional.</span></span>|  
|<span data-ttu-id="3bee1-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3bee1-123">trustedStoreLocation</span></span>|<span data-ttu-id="3bee1-124">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="3bee1-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="3bee1-125">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="3bee1-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="3bee1-126">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3bee1-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3bee1-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3bee1-127">Child Elements</span></span>  
  
|<span data-ttu-id="3bee1-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="3bee1-128">Element</span></span>|<span data-ttu-id="3bee1-129">Описание:</span><span class="sxs-lookup"><span data-stu-id="3bee1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bee1-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="3bee1-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="3bee1-131">Задает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="3bee1-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="3bee1-132">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="3bee1-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3bee1-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3bee1-133">Parent Elements</span></span>  
  
|<span data-ttu-id="3bee1-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="3bee1-134">Element</span></span>|<span data-ttu-id="3bee1-135">Описание:</span><span class="sxs-lookup"><span data-stu-id="3bee1-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3bee1-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3bee1-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="3bee1-137">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="3bee1-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="3bee1-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3bee1-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="3bee1-139">Обеспечивает настройку для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="3bee1-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bee1-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="3bee1-140">Remarks</span></span>  
 <span data-ttu-id="3bee1-141">A `<certificateValidation>` элемент можно задать на уровне службы под `<identityConfiguration>` элемент, либо на уровне коллекции обработчик маркеров безопасности в разделе `<securityTokenHandlerConfiguration>` элемента.</span><span class="sxs-lookup"><span data-stu-id="3bee1-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="3bee1-142">Параметры в коллекцию обработчика токенов переопределяют алгоритмам, заданным в службе.</span><span class="sxs-lookup"><span data-stu-id="3bee1-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="3bee1-143">Некоторые обработчики маркеров позволяют задать параметры проверки сертификата в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3bee1-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="3bee1-144">Параметры на отдельных обработчиков маркеров переопределить адреса, указанные как на уровне службы, так и в коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="3bee1-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bee1-145">Пример</span><span class="sxs-lookup"><span data-stu-id="3bee1-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
