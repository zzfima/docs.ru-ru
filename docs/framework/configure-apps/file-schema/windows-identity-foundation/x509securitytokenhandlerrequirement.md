---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55271954"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="3ee5b-101">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="3ee5b-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="3ee5b-102">Предоставляет вариант конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="3ee5b-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="3ee5b-103">\<system.identityModel></span></span>  
<span data-ttu-id="3ee5b-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="3ee5b-104">\<identityConfiguration></span></span>  
<span data-ttu-id="3ee5b-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="3ee5b-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="3ee5b-106">\<add></span><span class="sxs-lookup"><span data-stu-id="3ee5b-106">\<add></span></span>  
<span data-ttu-id="3ee5b-107">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="3ee5b-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ee5b-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ee5b-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ee5b-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3ee5b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3ee5b-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ee5b-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3ee5b-111">Attributes</span></span>  
  
|<span data-ttu-id="3ee5b-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3ee5b-112">Attribute</span></span>|<span data-ttu-id="3ee5b-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3ee5b-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ee5b-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="3ee5b-114">certificateValidationMode</span></span>|<span data-ttu-id="3ee5b-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="3ee5b-116">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="3ee5b-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="3ee5b-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="3ee5b-117">mapToWindows</span></span>|<span data-ttu-id="3ee5b-118">Указывает ли обработчик токенов следует сопоставить маркер проверки в учетную запись Windows с помощью входящего утверждения имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="3ee5b-119">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="3ee5b-119">The default is "false".</span></span>|  
|<span data-ttu-id="3ee5b-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="3ee5b-120">revocationMode</span></span>|<span data-ttu-id="3ee5b-121"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="3ee5b-122">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="3ee5b-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="3ee5b-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="3ee5b-123">trustedStoreLocation</span></span>|<span data-ttu-id="3ee5b-124">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="3ee5b-125">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="3ee5b-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="3ee5b-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="3ee5b-126">certificateValidator</span></span>|<span data-ttu-id="3ee5b-127">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="3ee5b-128">Если `certificateValidationMode` атрибут «Custom», экземпляр этого типа используется для проверки сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ee5b-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3ee5b-129">Child Elements</span></span>  
 <span data-ttu-id="3ee5b-130">Нет</span><span class="sxs-lookup"><span data-stu-id="3ee5b-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ee5b-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3ee5b-131">Parent Elements</span></span>  
  
|<span data-ttu-id="3ee5b-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ee5b-132">Element</span></span>|<span data-ttu-id="3ee5b-133">Описание</span><span class="sxs-lookup"><span data-stu-id="3ee5b-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ee5b-134">\<add></span><span class="sxs-lookup"><span data-stu-id="3ee5b-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="3ee5b-135">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="3ee5b-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="3ee5b-136">Пример</span><span class="sxs-lookup"><span data-stu-id="3ee5b-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
