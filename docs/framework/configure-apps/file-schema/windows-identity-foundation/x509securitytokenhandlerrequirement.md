---
title: '&lt;x509SecurityTokenHandlerRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 994677904cada71dbc7cce4b6ca0de1d4dc65014
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47085667"
---
# <a name="ltx509securitytokenhandlerrequirementgt"></a><span data-ttu-id="aaa7b-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="aaa7b-102">&lt;x509SecurityTokenHandlerRequirement&gt;</span></span>
<span data-ttu-id="aaa7b-103">Предоставляет вариант конфигурации <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> классом или производными классами.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-103">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
 <span data-ttu-id="aaa7b-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="aaa7b-104">\<system.identityModel></span></span>  
<span data-ttu-id="aaa7b-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="aaa7b-105">\<identityConfiguration></span></span>  
<span data-ttu-id="aaa7b-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="aaa7b-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="aaa7b-107">\<add></span><span class="sxs-lookup"><span data-stu-id="aaa7b-107">\<add></span></span>  
<span data-ttu-id="aaa7b-108">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="aaa7b-108">\<x509SecurityTokenHandlerRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa7b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aaa7b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aaa7b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aaa7b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="aaa7b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aaa7b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aaa7b-112">Attributes</span></span>  
  
|<span data-ttu-id="aaa7b-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aaa7b-113">Attribute</span></span>|<span data-ttu-id="aaa7b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="aaa7b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aaa7b-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="aaa7b-115">certificateValidationMode</span></span>|<span data-ttu-id="aaa7b-116"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="aaa7b-117">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="aaa7b-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="aaa7b-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="aaa7b-118">mapToWindows</span></span>|<span data-ttu-id="aaa7b-119">Указывает ли обработчик токенов следует сопоставить маркер проверки в учетную запись Windows с помощью входящего утверждения имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="aaa7b-120">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="aaa7b-120">The default is "false".</span></span>|  
|<span data-ttu-id="aaa7b-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="aaa7b-121">revocationMode</span></span>|<span data-ttu-id="aaa7b-122"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="aaa7b-123">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="aaa7b-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="aaa7b-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="aaa7b-124">trustedStoreLocation</span></span>|<span data-ttu-id="aaa7b-125">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="aaa7b-126">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="aaa7b-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="aaa7b-127">certificateValidator</span><span class="sxs-lookup"><span data-stu-id="aaa7b-127">certificateValidator</span></span>|<span data-ttu-id="aaa7b-128">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="aaa7b-129">Если `certificateValidationMode` атрибут «Custom», экземпляр этого типа используется для проверки сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aaa7b-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aaa7b-130">Child Elements</span></span>  
 <span data-ttu-id="aaa7b-131">Нет</span><span class="sxs-lookup"><span data-stu-id="aaa7b-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aaa7b-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aaa7b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="aaa7b-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="aaa7b-133">Element</span></span>|<span data-ttu-id="aaa7b-134">Описание</span><span class="sxs-lookup"><span data-stu-id="aaa7b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aaa7b-135">\<add></span><span class="sxs-lookup"><span data-stu-id="aaa7b-135">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="aaa7b-136">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="aaa7b-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="aaa7b-137">Пример</span><span class="sxs-lookup"><span data-stu-id="aaa7b-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
