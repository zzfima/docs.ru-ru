---
title: <x509SecurityTokenHandlerRequirement>
ms.date: 03/30/2017
ms.assetid: aca22c2c-5ae7-42af-9bbd-15c2524692ce
author: BrucePerlerMS
ms.openlocfilehash: 76eeea635fd65486a1c16bea15a49018876dae99
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251692"
---
# <a name="x509securitytokenhandlerrequirement"></a><span data-ttu-id="86052-101">\<x509SecurityTokenHandlerRequirement ></span><span class="sxs-lookup"><span data-stu-id="86052-101">\<x509SecurityTokenHandlerRequirement></span></span>
<span data-ttu-id="86052-102">Предоставляет необязательную конфигурацию для <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> класса или производных классов.</span><span class="sxs-lookup"><span data-stu-id="86052-102">Provides optional configuration for the <xref:System.IdentityModel.Tokens.X509SecurityTokenHandler> class or derived classes.</span></span>  
  
<span data-ttu-id="86052-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="86052-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="86052-104">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="86052-104">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="86052-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="86052-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="86052-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="86052-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="86052-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="86052-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="86052-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<x509SecurityTokenHandlerRequirement >**</span><span class="sxs-lookup"><span data-stu-id="86052-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<x509SecurityTokenHandlerRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86052-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86052-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86052-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="86052-110">Attributes and Elements</span></span>  
 <span data-ttu-id="86052-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="86052-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86052-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="86052-112">Attributes</span></span>  
  
|<span data-ttu-id="86052-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="86052-113">Attribute</span></span>|<span data-ttu-id="86052-114">Описание</span><span class="sxs-lookup"><span data-stu-id="86052-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86052-115">certificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="86052-115">certificateValidationMode</span></span>|<span data-ttu-id="86052-116">Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="86052-116">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="86052-117">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="86052-117">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="86052-118">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="86052-118">mapToWindows</span></span>|<span data-ttu-id="86052-119">Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="86052-119">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="86052-120">Значение по умолчанию — false.</span><span class="sxs-lookup"><span data-stu-id="86052-120">The default is "false".</span></span>|  
|<span data-ttu-id="86052-121">revocationMode</span><span class="sxs-lookup"><span data-stu-id="86052-121">revocationMode</span></span>|<span data-ttu-id="86052-122">Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="86052-122">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="86052-123">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="86052-123">The default value is "Online".</span></span>|  
|<span data-ttu-id="86052-124">trustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="86052-124">trustedStoreLocation</span></span>|<span data-ttu-id="86052-125">Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="86052-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="86052-126">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="86052-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="86052-127">цертификатевалидатор</span><span class="sxs-lookup"><span data-stu-id="86052-127">certificateValidator</span></span>|<span data-ttu-id="86052-128">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="86052-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="86052-129">`certificateValidationMode` Если атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="86052-129">If the `certificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86052-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="86052-130">Child Elements</span></span>  
 <span data-ttu-id="86052-131">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="86052-131">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86052-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="86052-132">Parent Elements</span></span>  
  
|<span data-ttu-id="86052-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="86052-133">Element</span></span>|<span data-ttu-id="86052-134">Описание</span><span class="sxs-lookup"><span data-stu-id="86052-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="86052-135">\<add></span><span class="sxs-lookup"><span data-stu-id="86052-135">\<add></span></span>](add.md)|<span data-ttu-id="86052-136">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="86052-136">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="86052-137">Пример</span><span class="sxs-lookup"><span data-stu-id="86052-137">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.X509SecurityTokenHandler, System.IdentityModel">  
    <x509SecurityTokenHandlerRequirement mapToWindows="true"   
                                         certificateValidationMode="PeerOrChainTrust"   
                                         revocationMode="Online"   
                                         trustedStoreLocation="LocalMachine" />  
</add>  
```
