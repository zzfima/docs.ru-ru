---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 6e8267f170dbb26381564be7b66df5f617156885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790446"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="098e4-101">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="098e4-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="098e4-102">Предоставляет вариант конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="098e4-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="098e4-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="098e4-103">\<system.identityModel></span></span>  
<span data-ttu-id="098e4-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="098e4-104">\<identityConfiguration></span></span>  
<span data-ttu-id="098e4-105">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="098e4-105">\<securityTokenHandlers></span></span>  
<span data-ttu-id="098e4-106">\<add></span><span class="sxs-lookup"><span data-stu-id="098e4-106">\<add></span></span>  
<span data-ttu-id="098e4-107">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="098e4-107">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="098e4-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="098e4-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="098e4-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="098e4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="098e4-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="098e4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="098e4-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="098e4-111">Attributes</span></span>  
  
|<span data-ttu-id="098e4-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="098e4-112">Attribute</span></span>|<span data-ttu-id="098e4-113">Описание</span><span class="sxs-lookup"><span data-stu-id="098e4-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="098e4-114">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="098e4-114">certificateValidationMode</span></span>|<span data-ttu-id="098e4-115"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="098e4-115">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="098e4-116">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="098e4-116">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="098e4-117">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="098e4-117">mapToWindows</span></span>|<span data-ttu-id="098e4-118">Указывает ли обработчик токенов следует сопоставить маркер проверки в учетную запись Windows с помощью входящего утверждения имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="098e4-118">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="098e4-119">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="098e4-119">The default is "false".</span></span>|  
|<span data-ttu-id="098e4-120">revocationMode</span><span class="sxs-lookup"><span data-stu-id="098e4-120">revocationMode</span></span>|<span data-ttu-id="098e4-121"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="098e4-121">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="098e4-122">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="098e4-122">The default value is "Online".</span></span>|  
|<span data-ttu-id="098e4-123">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="098e4-123">trustedStoreLocation</span></span>|<span data-ttu-id="098e4-124">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="098e4-124">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="098e4-125">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="098e4-125">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="098e4-126">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="098e4-126">certificateValidator</span></span>|<span data-ttu-id="098e4-127">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="098e4-127">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="098e4-128">Если `certificateValidationMode` атрибут «Custom», экземпляр этого типа используется для проверки сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="098e4-128">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="098e4-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="098e4-129">Child Elements</span></span>  
 <span data-ttu-id="098e4-130">Нет</span><span class="sxs-lookup"><span data-stu-id="098e4-130">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="098e4-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="098e4-131">Parent Elements</span></span>  
  
|<span data-ttu-id="098e4-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="098e4-132">Element</span></span>|<span data-ttu-id="098e4-133">Описание</span><span class="sxs-lookup"><span data-stu-id="098e4-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="098e4-134">\<add></span><span class="sxs-lookup"><span data-stu-id="098e4-134">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="098e4-135">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="098e4-135">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="098e4-136">Пример</span><span class="sxs-lookup"><span data-stu-id="098e4-136">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
