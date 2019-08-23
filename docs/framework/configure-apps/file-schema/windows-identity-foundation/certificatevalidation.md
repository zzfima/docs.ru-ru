---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: 8185153eb02c5794b0f6ac02a6837806f2073c07
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941919"
---
# <a name="certificatevalidation"></a><span data-ttu-id="27807-101">\<Цертификатевалидатион ></span><span class="sxs-lookup"><span data-stu-id="27807-101">\<certificateValidation></span></span>
<span data-ttu-id="27807-102">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="27807-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="27807-103">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="27807-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
 <span data-ttu-id="27807-104">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="27807-104">\<system.identityModel></span></span>  
<span data-ttu-id="27807-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="27807-105">\<identityConfiguration></span></span>  
<span data-ttu-id="27807-106">\<Цертификатевалидатион ></span><span class="sxs-lookup"><span data-stu-id="27807-106">\<certificateValidation></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27807-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27807-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27807-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27807-108">Attributes and Elements</span></span>  
 <span data-ttu-id="27807-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27807-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27807-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27807-110">Attributes</span></span>  
  
|<span data-ttu-id="27807-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27807-111">Attribute</span></span>|<span data-ttu-id="27807-112">Описание</span><span class="sxs-lookup"><span data-stu-id="27807-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27807-113">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="27807-113">certificateValidationMode</span></span>|<span data-ttu-id="27807-114">Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="27807-114">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="27807-115">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="27807-115">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="27807-116">Чтобы указать настраиваемый проверяющий элемент управления, установите для этого атрибута значение "Custom" и укажите проверяющий элемент управления с помощью [ \<элемента цертификатевалидатор >](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="27807-116">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="27807-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="27807-117">Optional.</span></span>|  
|<span data-ttu-id="27807-118">revocationMode</span><span class="sxs-lookup"><span data-stu-id="27807-118">revocationMode</span></span>|<span data-ttu-id="27807-119">Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="27807-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="27807-120">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="27807-120">The default value is "Online".</span></span> <span data-ttu-id="27807-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="27807-121">Optional.</span></span>|  
|<span data-ttu-id="27807-122">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="27807-122">trustedStoreLocation</span></span>|<span data-ttu-id="27807-123">Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="27807-123">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="27807-124">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="27807-124">The default value is "LocalMachine".</span></span> <span data-ttu-id="27807-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="27807-125">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27807-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27807-126">Child Elements</span></span>  
  
|<span data-ttu-id="27807-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="27807-127">Element</span></span>|<span data-ttu-id="27807-128">Описание</span><span class="sxs-lookup"><span data-stu-id="27807-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27807-129">\<Цертификатевалидатор ></span><span class="sxs-lookup"><span data-stu-id="27807-129">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="27807-130">Указывает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="27807-130">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="27807-131">Этот тип используется только в том случае `certificateValidationMode` , если атрибуту [ \<элемента цертификатевалидатион >](certificatevalidation.md) присвоено значение Custom.</span><span class="sxs-lookup"><span data-stu-id="27807-131">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="27807-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27807-132">Parent Elements</span></span>  
  
|<span data-ttu-id="27807-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="27807-133">Element</span></span>|<span data-ttu-id="27807-134">Описание</span><span class="sxs-lookup"><span data-stu-id="27807-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27807-135">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="27807-135">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="27807-136">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="27807-136">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="27807-137">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="27807-137">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="27807-138">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="27807-138">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27807-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="27807-139">Remarks</span></span>  
 <span data-ttu-id="27807-140">Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="27807-140">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="27807-141">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="27807-141">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="27807-142">Некоторые обработчики маркеров позволяют указать параметры проверки сертификата в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="27807-142">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="27807-143">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны как на уровне службы, так и в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="27807-143">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="27807-144">Пример</span><span class="sxs-lookup"><span data-stu-id="27807-144">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
