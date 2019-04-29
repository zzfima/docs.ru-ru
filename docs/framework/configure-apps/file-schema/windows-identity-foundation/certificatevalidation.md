---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 7b8823d792e3f15846a9483d670994be4b368980
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667357"
---
# <a name="certificatevalidation"></a><span data-ttu-id="0d256-101">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="0d256-101">\<certificateValidation></span></span>
<span data-ttu-id="0d256-102">Управляет параметрами, используемых обработчиками токена для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0d256-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="0d256-103">Эти параметры переопределяются в том случае, если настроен собственный проверяющий элемент управления указанным обработчиком.</span><span class="sxs-lookup"><span data-stu-id="0d256-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="0d256-104">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="0d256-104">\<system.identityModel></span></span>  
<span data-ttu-id="0d256-105">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="0d256-105">\<identityConfiguration></span></span>  
<span data-ttu-id="0d256-106">\<certificateValidation ></span><span class="sxs-lookup"><span data-stu-id="0d256-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d256-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d256-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d256-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0d256-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0d256-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0d256-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d256-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0d256-110">Attributes</span></span>  
  
|<span data-ttu-id="0d256-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0d256-111">Attribute</span></span>|<span data-ttu-id="0d256-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0d256-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d256-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="0d256-113">certificateValidationMode</span></span>|<span data-ttu-id="0d256-114"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="0d256-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="0d256-115">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="0d256-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="0d256-116">Чтобы указать настраиваемый проверяющий элемент управления, установите этому атрибуту значение «Custom» и укажите проверяющего элемента управления с помощью [ \<certificateValidator >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="0d256-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md) element.</span></span> <span data-ttu-id="0d256-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="0d256-117">Optional.</span></span>|  
|<span data-ttu-id="0d256-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="0d256-118">revocationMode</span></span>|<span data-ttu-id="0d256-119"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="0d256-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="0d256-120">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="0d256-120">The default value is "Online".</span></span> <span data-ttu-id="0d256-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="0d256-121">Optional.</span></span>|  
|<span data-ttu-id="0d256-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="0d256-122">trustedStoreLocation</span></span>|<span data-ttu-id="0d256-123">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="0d256-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="0d256-124">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="0d256-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="0d256-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="0d256-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d256-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0d256-126">Child Elements</span></span>  
  
|<span data-ttu-id="0d256-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d256-127">Element</span></span>|<span data-ttu-id="0d256-128">Описание</span><span class="sxs-lookup"><span data-stu-id="0d256-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d256-129">\<certificateValidator ></span><span class="sxs-lookup"><span data-stu-id="0d256-129">\<certificateValidator></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidator.md)|<span data-ttu-id="0d256-130">Задает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="0d256-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="0d256-131">Этот тип используется только в том случае, если `certificateValidationMode` атрибут [ \<certificateValidation >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) имеет значение «Custom».</span><span class="sxs-lookup"><span data-stu-id="0d256-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0d256-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0d256-132">Parent Elements</span></span>  
  
|<span data-ttu-id="0d256-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="0d256-133">Element</span></span>|<span data-ttu-id="0d256-134">Описание</span><span class="sxs-lookup"><span data-stu-id="0d256-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0d256-135">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="0d256-135">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="0d256-136">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="0d256-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="0d256-137">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="0d256-137">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="0d256-138">Предоставляет конфигурацию для коллекции безопасности обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="0d256-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d256-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d256-139">Remarks</span></span>  
 <span data-ttu-id="0d256-140">Объект `<certificateValidation>` на уровне службы может быть задан элемент `<identityConfiguration>` элемент или на уровне коллекции обработчиков токенов безопасности в разделе `<securityTokenHandlerConfiguration>` элемент.</span><span class="sxs-lookup"><span data-stu-id="0d256-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="0d256-141">Переопределить параметры на коллекцию обработчиков токенов, теми, которые указаны в службе.</span><span class="sxs-lookup"><span data-stu-id="0d256-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="0d256-142">Некоторые обработчики маркеров позволяют задать параметры проверки сертификата в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="0d256-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="0d256-143">Параметры на отдельных обработчиков маркеров переопределить указанные как на уровне службы, так и на коллекцию обработчиков токенов безопасности.</span><span class="sxs-lookup"><span data-stu-id="0d256-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d256-144">Пример</span><span class="sxs-lookup"><span data-stu-id="0d256-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
