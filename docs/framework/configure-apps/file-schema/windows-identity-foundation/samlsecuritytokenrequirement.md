---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: df259398beb242ea95efb248d6b5140b38ca3c45
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942492"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="fcc89-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="fcc89-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="fcc89-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="fcc89-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="fcc89-103">Представляется <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом.</span><span class="sxs-lookup"><span data-stu-id="fcc89-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="fcc89-104">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="fcc89-104">\<system.identityModel></span></span>  
<span data-ttu-id="fcc89-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fcc89-105">\<identityConfiguration></span></span>  
<span data-ttu-id="fcc89-106">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="fcc89-106">\<securityTokenHandlers></span></span>  
<span data-ttu-id="fcc89-107">\<add></span><span class="sxs-lookup"><span data-stu-id="fcc89-107">\<add></span></span>  
<span data-ttu-id="fcc89-108">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="fcc89-108">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fcc89-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fcc89-109">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <add>  
        <samlSecurityTokenRequirement   
            issuerCertificateValidationMode="None||ChainTrust||PeerTrust||PeerOrChainTrust||Custom"  
            issuerCertificateRevocationMode="NoCheck||Offline||Online"  
            issuerCertificateTrustedStoreLocation="CurrentLocation||LocalMachine"  
            issuerCertificateValidator="Namespace.Class Assembly"  
            mapToWindows=xs:boolean  
          <nameClaimType value=xs:string />  
          <roleClaimType value=xs:string />  
        </samlSecurityTokenRequirement>  
      </add>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fcc89-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fcc89-110">Attributes and Elements</span></span>  
 <span data-ttu-id="fcc89-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fcc89-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fcc89-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fcc89-112">Attributes</span></span>  
  
|<span data-ttu-id="fcc89-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fcc89-113">Attribute</span></span>|<span data-ttu-id="fcc89-114">Описание</span><span class="sxs-lookup"><span data-stu-id="fcc89-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fcc89-115">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="fcc89-115">mapToWindows</span></span>|<span data-ttu-id="fcc89-116">Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="fcc89-116">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="fcc89-117">Значение по умолчанию — false.</span><span class="sxs-lookup"><span data-stu-id="fcc89-117">The default is "false".</span></span>|  
|<span data-ttu-id="fcc89-118">иссуерцертификатеревокатионмоде</span><span class="sxs-lookup"><span data-stu-id="fcc89-118">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="fcc89-119">Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="fcc89-119">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="fcc89-120">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="fcc89-120">The default value is "Online".</span></span>|  
|<span data-ttu-id="fcc89-121">иссуерцертификатевалидатионмоде</span><span class="sxs-lookup"><span data-stu-id="fcc89-121">issuerCertificateValidationMode</span></span>|<span data-ttu-id="fcc89-122">Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="fcc89-122">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="fcc89-123">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="fcc89-123">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="fcc89-124">иссуерцертификатетрустедсторелокатион</span><span class="sxs-lookup"><span data-stu-id="fcc89-124">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="fcc89-125">Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="fcc89-125">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="fcc89-126">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="fcc89-126">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="fcc89-127">иссуерцертификатевалидатор</span><span class="sxs-lookup"><span data-stu-id="fcc89-127">issuerCertificateValidator</span></span>|<span data-ttu-id="fcc89-128">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="fcc89-128">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="fcc89-129">`issuerCertificateValidationMode` Если атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="fcc89-129">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fcc89-130">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fcc89-130">Child Elements</span></span>  
  
|<span data-ttu-id="fcc89-131">Элемент</span><span class="sxs-lookup"><span data-stu-id="fcc89-131">Element</span></span>|<span data-ttu-id="fcc89-132">Описание</span><span class="sxs-lookup"><span data-stu-id="fcc89-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcc89-133">\<Намеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="fcc89-133">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="fcc89-134">Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="fcc89-134">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="fcc89-135">\<Ролеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="fcc89-135">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="fcc89-136">Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="fcc89-136">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fcc89-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fcc89-137">Parent Elements</span></span>  
  
|<span data-ttu-id="fcc89-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="fcc89-138">Element</span></span>|<span data-ttu-id="fcc89-139">Описание</span><span class="sxs-lookup"><span data-stu-id="fcc89-139">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fcc89-140">\<add></span><span class="sxs-lookup"><span data-stu-id="fcc89-140">\<add></span></span>](add.md)|<span data-ttu-id="fcc89-141">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="fcc89-141">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fcc89-142">Примечания</span><span class="sxs-lookup"><span data-stu-id="fcc89-142">Remarks</span></span>  
 <span data-ttu-id="fcc89-143"><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> `SamlSecurityTokenRequirement` Элемент представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в объектной модели и используется для настройки свойства в или. `<samlSecurityTokenRequirement>`</span><span class="sxs-lookup"><span data-stu-id="fcc89-143">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fcc89-144">Пример</span><span class="sxs-lookup"><span data-stu-id="fcc89-144">Example</span></span>  
  
```xml  
<add type="System.IdentityModel.Tokens.SamlSecurityTokenHandler, System.IdentityModel">  
    <samlSecurityTokenRequirement issuerCertificateValidationMode="PeerOrChainTrust"  
                                  issuerCertificateRevocationMode="Online"  
                                  issuerCertificateTrustedStoreLocation="LocalMachine"  
                                  mapToWindows="false">  
  
        <nameClaimType value="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/name" />  
        <roleClaimType value="schemas.microsoft.com/ws/2006/04/identity/claims/role" />  
    </samlSecurityTokenRequirement>  
</add>  
```
