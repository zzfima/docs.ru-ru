---
title: <certificateValidation>
ms.date: 03/30/2017
ms.assetid: 6c54c704-b55e-4631-88ff-4d4a5621554c
author: BrucePerlerMS
ms.openlocfilehash: c2d1a5d36cb5616ef06eedc093dd70a68a164a81
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252136"
---
# <a name="certificatevalidation"></a><span data-ttu-id="ee0f8-101">\<Цертификатевалидатион ></span><span class="sxs-lookup"><span data-stu-id="ee0f8-101">\<certificateValidation></span></span>
<span data-ttu-id="ee0f8-102">Управляет параметрами, которые обработчики маркеров используют для проверки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-102">Controls the settings that token handlers use to validate certificates.</span></span> <span data-ttu-id="ee0f8-103">Эти параметры переопределяются, если для определенного обработчика настроен собственный проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-103">These settings are overridden if a specific handler is configured with its own validator.</span></span>  
  
<span data-ttu-id="ee0f8-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ee0f8-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ee0f8-105">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="ee0f8-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="ee0f8-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="ee0f8-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="ee0f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Цертификатевалидатион >**</span><span class="sxs-lookup"><span data-stu-id="ee0f8-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateValidation>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee0f8-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ee0f8-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ee0f8-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ee0f8-109">Attributes and Elements</span></span>  
 <span data-ttu-id="ee0f8-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ee0f8-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ee0f8-111">Attributes</span></span>  
  
|<span data-ttu-id="ee0f8-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ee0f8-112">Attribute</span></span>|<span data-ttu-id="ee0f8-113">Описание</span><span class="sxs-lookup"><span data-stu-id="ee0f8-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ee0f8-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="ee0f8-114">certificateValidationMode</span></span>|<span data-ttu-id="ee0f8-115">Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ee0f8-116">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="ee0f8-116">The default value is "PeerOrChainTrust".</span></span> <span data-ttu-id="ee0f8-117">Чтобы указать настраиваемый проверяющий элемент управления, установите для этого атрибута значение "Custom" и укажите проверяющий элемент управления с помощью [ \<элемента цертификатевалидатор >](certificatevalidator.md) .</span><span class="sxs-lookup"><span data-stu-id="ee0f8-117">To specify a custom validator, set this attribute to "Custom" and specify the validator using the [\<certificateValidator>](certificatevalidator.md) element.</span></span> <span data-ttu-id="ee0f8-118">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-118">Optional.</span></span>|  
|<span data-ttu-id="ee0f8-119">revocationMode</span><span class="sxs-lookup"><span data-stu-id="ee0f8-119">revocationMode</span></span>|<span data-ttu-id="ee0f8-120">Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="ee0f8-121">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="ee0f8-121">The default value is "Online".</span></span> <span data-ttu-id="ee0f8-122">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-122">Optional.</span></span>|  
|<span data-ttu-id="ee0f8-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="ee0f8-123">trustedStoreLocation</span></span>|<span data-ttu-id="ee0f8-124">Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="ee0f8-125">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-125">The default value is "LocalMachine".</span></span> <span data-ttu-id="ee0f8-126">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-126">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ee0f8-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ee0f8-127">Child Elements</span></span>  
  
|<span data-ttu-id="ee0f8-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee0f8-128">Element</span></span>|<span data-ttu-id="ee0f8-129">Описание</span><span class="sxs-lookup"><span data-stu-id="ee0f8-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee0f8-130">\<Цертификатевалидатор ></span><span class="sxs-lookup"><span data-stu-id="ee0f8-130">\<certificateValidator></span></span>](certificatevalidator.md)|<span data-ttu-id="ee0f8-131">Указывает пользовательский тип для проверки сертификата.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-131">Specifies a custom type for certificate validation.</span></span> <span data-ttu-id="ee0f8-132">Этот тип используется только в том случае `certificateValidationMode` , если атрибуту [ \<элемента цертификатевалидатион >](certificatevalidation.md) присвоено значение Custom.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-132">This type is used only if the `certificateValidationMode` attribute of the [\<certificateValidation>](certificatevalidation.md) element is set to "Custom".</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ee0f8-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ee0f8-133">Parent Elements</span></span>  
  
|<span data-ttu-id="ee0f8-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="ee0f8-134">Element</span></span>|<span data-ttu-id="ee0f8-135">Описание</span><span class="sxs-lookup"><span data-stu-id="ee0f8-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ee0f8-136">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="ee0f8-136">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="ee0f8-137">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-137">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="ee0f8-138">\<Секурититокенхандлерконфигуратион ></span><span class="sxs-lookup"><span data-stu-id="ee0f8-138">\<securityTokenHandlerConfiguration></span></span>](securitytokenhandlerconfiguration.md)|<span data-ttu-id="ee0f8-139">Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-139">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ee0f8-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="ee0f8-140">Remarks</span></span>  
 <span data-ttu-id="ee0f8-141">Элемент можно указать на уровне службы `<identityConfiguration>` в элементе или на уровне коллекции `<securityTokenHandlerConfiguration>` обработчика маркеров безопасности под элементом. `<certificateValidation>`</span><span class="sxs-lookup"><span data-stu-id="ee0f8-141">A `<certificateValidation>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="ee0f8-142">Параметры коллекции обработчиков маркеров переопределяют указанные в службе.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-142">Settings on a token handler collection override those specified on the service.</span></span> <span data-ttu-id="ee0f8-143">Некоторые обработчики маркеров позволяют указать параметры проверки сертификата в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-143">Some token handlers allow you to specify certificate validation settings in configuration.</span></span> <span data-ttu-id="ee0f8-144">Параметры отдельных обработчиков маркеров переопределяют те, которые указаны как на уровне службы, так и в коллекции обработчиков маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ee0f8-144">Settings on individual token handlers override those specified both at the service level and on the security token handler collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee0f8-145">Пример</span><span class="sxs-lookup"><span data-stu-id="ee0f8-145">Example</span></span>  
  
```xml  
<certificateValidation certificateValidationMode="PeerOrChainTrust"  
                       revocationMode="Online"  
                       trustedStoreLocation="LocalMachine" />  
```
