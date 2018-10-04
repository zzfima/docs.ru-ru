---
title: '&lt;certificateValidation&gt;'
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 29881be43f02d275ad135efd97dc8b25a7409beb
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "48778173"
---
# <a name="ltcertificatevalidationgt"></a><span data-ttu-id="67d15-102">&lt;certificateValidation&gt;</span><span class="sxs-lookup"><span data-stu-id="67d15-102">&lt;certificateValidation&gt;</span></span>
<span data-ttu-id="67d15-103">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="67d15-103">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="67d15-104">Эти параметры переопределяются в том случае, если настроен собственный проверяющий элемент управления указанным обработчиком.</span><span class="sxs-lookup"><span data-stu-id="67d15-104">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="67d15-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="67d15-105">\<system.identityModel></span></span>  
<span data-ttu-id="67d15-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="67d15-106">\<identityConfiguration></span></span>  
<span data-ttu-id="67d15-107">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="67d15-107">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d15-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67d15-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67d15-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67d15-109">Attributes and Elements</span></span>  
 <span data-ttu-id="67d15-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67d15-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67d15-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67d15-111">Attributes</span></span>  
  
|<span data-ttu-id="67d15-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="67d15-112">Attribute</span></span>|<span data-ttu-id="67d15-113">Описание</span><span class="sxs-lookup"><span data-stu-id="67d15-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="67d15-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="67d15-114">certificateValidationMode</span></span>|<span data-ttu-id="67d15-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="67d15-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="67d15-116">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="67d15-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="67d15-117">Чтобы указать настраиваемый проверяющий элемент управления, установите этому атрибуту значение «Custom» и укажите проверяющего элемента управления с помощью [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="67d15-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="67d15-118">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="67d15-118">Optional.</span></span>|  
|<span data-ttu-id="67d15-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="67d15-119">revocationMode</span></span>|<span data-ttu-id="67d15-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="67d15-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="67d15-121">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="67d15-121">The default value is "Online".</span></span> <span data-ttu-id="67d15-122">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="67d15-122">Optional.</span></span>|  
|<span data-ttu-id="67d15-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="67d15-123">trustedStoreLocation</span></span>|<span data-ttu-id="67d15-124">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="67d15-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="67d15-125">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="67d15-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="67d15-126">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="67d15-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67d15-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67d15-127">Child Elements</span></span>  
  
|<span data-ttu-id="67d15-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="67d15-128">Element</span></span>|<span data-ttu-id="67d15-129">Описание</span><span class="sxs-lookup"><span data-stu-id="67d15-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67d15-130">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="67d15-130">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="67d15-131">Задает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="67d15-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="67d15-132">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="67d15-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="67d15-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67d15-133">Parent Elements</span></span>  
  
|<span data-ttu-id="67d15-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="67d15-134">Element</span></span>|<span data-ttu-id="67d15-135">Описание</span><span class="sxs-lookup"><span data-stu-id="67d15-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="67d15-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="67d15-136">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="67d15-137">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="67d15-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="67d15-138">\<securityTokenHandlerConfiguration ></span><span class="sxs-lookup"><span data-stu-id="67d15-138">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="67d15-139">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="67d15-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67d15-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="67d15-140">Remarks</span></span>  
 <span data-ttu-id="67d15-141">Объект `<certificateValidation>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="67d15-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="67d15-142">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="67d15-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="67d15-143">Некоторые обработчики маркеров позволяют задать параметры проверки сертификата в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="67d15-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="67d15-144">Параметры на отдельных обработчиков маркеров переопределить указанные как на уровне службы, так и на коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="67d15-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67d15-145">Пример</span><span class="sxs-lookup"><span data-stu-id="67d15-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
