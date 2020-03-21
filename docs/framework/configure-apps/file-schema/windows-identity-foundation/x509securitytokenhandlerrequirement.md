---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 30ce69a35cfdd34e0dfea5c682347eb9187e04ed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152454"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="a294b-101">\<x509SecurityTokenhandlerтребование></span><span class="sxs-lookup"><span data-stu-id="a294b-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="a294b-102">Предоставляет дополнительную <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> конфигурацию для классов или производных классов.</span><span class="sxs-lookup"><span data-stu-id="a294b-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="a294b-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a294b-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a294b-104">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="a294b-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="a294b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="a294b-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="a294b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="a294b-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="a294b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="a294b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="a294b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerтребование>**</span><span class="sxs-lookup"><span data-stu-id="a294b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a294b-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a294b-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a294b-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a294b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a294b-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a294b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a294b-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a294b-112">Attributes</span></span>  
  
|<span data-ttu-id="a294b-113">attribute</span><span class="sxs-lookup"><span data-stu-id="a294b-113">Attribute</span></span>|<span data-ttu-id="a294b-114">Описание</span><span class="sxs-lookup"><span data-stu-id="a294b-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a294b-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="a294b-115">certificateValidationMode</span></span>|<span data-ttu-id="a294b-116">Значение, <xref:System.ServiceModel.Security.X509CertificateValidationMode> опознавававававрежим проверки для использования для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="a294b-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a294b-117">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="a294b-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="a294b-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="a294b-118">mapToWindows</span></span>|<span data-ttu-id="a294b-119">Уточняется, следует ли обработчику маркеров отображения токена проверки в учетную запись Windows с помощью входящего требования UPN.</span><span class="sxs-lookup"><span data-stu-id="a294b-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="a294b-120">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="a294b-120">The default is "false".</span></span>|  
|<span data-ttu-id="a294b-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="a294b-121">revocationMode</span></span>|<span data-ttu-id="a294b-122">Значение, <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> оговариваев режим отзыва для использования для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="a294b-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="a294b-123">Значение по умолчанию "Онлайн".</span><span class="sxs-lookup"><span data-stu-id="a294b-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="a294b-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="a294b-124">trustedStoreLocation</span></span>|<span data-ttu-id="a294b-125">Значение, <xref:System.Security.Cryptography.X509Certificates.StoreLocation> опоедая магазин сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="a294b-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="a294b-126">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="a294b-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="a294b-127">сертификатВалистатор</span><span class="sxs-lookup"><span data-stu-id="a294b-127">certificateValidator</span></span>|<span data-ttu-id="a294b-128">Пользовательский тип, который <xref:System.IdentityModel.Selectors.X509CertificateValidator>происходит от .</span><span class="sxs-lookup"><span data-stu-id="a294b-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="a294b-129">Если `certificateValidationMode` атрибут является "Custom", экземпляр этого типа используется для проверки сертификата эмитента.</span><span class="sxs-lookup"><span data-stu-id="a294b-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a294b-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a294b-130">Child Elements</span></span>  
 <span data-ttu-id="a294b-131">None</span><span class="sxs-lookup"><span data-stu-id="a294b-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a294b-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a294b-132">Parent Elements</span></span>  
  
|<span data-ttu-id="a294b-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="a294b-133">Element</span></span>|<span data-ttu-id="a294b-134">Описание</span><span class="sxs-lookup"><span data-stu-id="a294b-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a294b-135">\<добавить></span><span class="sxs-lookup"><span data-stu-id="a294b-135">\<add></span></span>](add.md)|<span data-ttu-id="a294b-136">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="a294b-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a294b-137">Пример</span><span class="sxs-lookup"><span data-stu-id="a294b-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"
                                         certificateValidationMode="PeerOrChainTrust"
                                         revocationMode="Online"
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
