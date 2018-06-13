---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 8af4a718fc9f4ba7f674d98e13424bb443693c6c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755946"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="cd735-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="cd735-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="cd735-103">Предоставляет дополнительной конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="cd735-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="cd735-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="cd735-104">\<system.identityModel></span></span>  
<span data-ttu-id="cd735-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="cd735-105">\<identityConfiguration></span></span>  
<span data-ttu-id="cd735-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="cd735-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="cd735-107">\<add></span><span class="sxs-lookup"><span data-stu-id="cd735-107">\<add></span></span>  
<span data-ttu-id="cd735-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="cd735-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd735-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd735-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
        <x509SecurityTokenHandlerRequirement>  
          mapToWindows=xs:boolean  
          certificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
          certificateValidator="Namespace.Class, Assembly"  
          revocationMode="NoCheck||Offline||Online"  
          trustedStoreLocation="CurrentUser||LocalMachine"  
        </x509SecurityTokenHandlerRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd735-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cd735-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cd735-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cd735-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd735-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd735-112">Attributes</span></span>  
  
|<span data-ttu-id="cd735-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cd735-113">Attribute</span></span>|<span data-ttu-id="cd735-114">Описание</span><span class="sxs-lookup"><span data-stu-id="cd735-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cd735-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="cd735-115">certificateValidationMode</span></span>|<span data-ttu-id="cd735-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, указывающее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="cd735-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cd735-117">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="cd735-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="cd735-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="cd735-118">mapToWindows</span></span>|<span data-ttu-id="cd735-119">Указывает ли обработчик маркеров следует сопоставить проверки токена с учетной записью Windows с помощью входящее утверждение имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="cd735-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="cd735-120">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="cd735-120">The default is "false".</span></span>|  
|<span data-ttu-id="cd735-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="cd735-121">revocationMode</span></span>|<span data-ttu-id="cd735-122"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, указывающее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="cd735-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="cd735-123">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="cd735-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="cd735-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="cd735-124">trustedStoreLocation</span></span>|<span data-ttu-id="cd735-125">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="cd735-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="cd735-126">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="cd735-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="cd735-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="cd735-127">certificateValidator</span></span>|<span data-ttu-id="cd735-128">Пользовательский тип, который является производным от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="cd735-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="cd735-129">Если `certificateValidationMode` атрибут «Custom», экземпляр этого типа используется для проверки сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="cd735-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd735-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd735-130">Child Elements</span></span>  
 <span data-ttu-id="cd735-131">Нет</span><span class="sxs-lookup"><span data-stu-id="cd735-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="cd735-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd735-132">Parent Elements</span></span>  
  
|<span data-ttu-id="cd735-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd735-133">Element</span></span>|<span data-ttu-id="cd735-134">Описание</span><span class="sxs-lookup"><span data-stu-id="cd735-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cd735-135">\<add></span><span class="sxs-lookup"><span data-stu-id="cd735-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="cd735-136">Добавляет обработчик маркеров безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="cd735-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cd735-137">Пример</span><span class="sxs-lookup"><span data-stu-id="cd735-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
