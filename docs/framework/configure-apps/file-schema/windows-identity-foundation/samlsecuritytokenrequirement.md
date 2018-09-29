---
title: '&lt;samlSecurityTokenRequirement&gt;'
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: c9856dae971691baf9dabe845bdecae90cbc8aa5
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2018
ms.locfileid: "47455504"
---
# <a name="ltsamlsecuritytokenrequirementgt"></a><span data-ttu-id="95460-102">&lt;samlSecurityTokenRequirement&gt;</span><span class="sxs-lookup"><span data-stu-id="95460-102">&lt;samlSecurityTokenRequirement&gt;</span></span>
<span data-ttu-id="95460-103">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класс или класс, производный от любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="95460-103">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="95460-104">Представленный <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> класса.</span><span class="sxs-lookup"><span data-stu-id="95460-104">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
 <span data-ttu-id="95460-105">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="95460-105">\<system.identityModel></span></span>  
<span data-ttu-id="95460-106">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="95460-106">\<identityConfiguration></span></span>  
<span data-ttu-id="95460-107">\<securityTokenHandlers ></span><span class="sxs-lookup"><span data-stu-id="95460-107">\<securityTokenHandlers></span></span>  
<span data-ttu-id="95460-108">\<add></span><span class="sxs-lookup"><span data-stu-id="95460-108">\<add></span></span>  
<span data-ttu-id="95460-109">\<samlSecurityTokenRequirement ></span><span class="sxs-lookup"><span data-stu-id="95460-109">\<samlSecurityTokenRequirement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95460-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95460-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95460-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="95460-111">Attributes and Elements</span></span>  
 <span data-ttu-id="95460-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="95460-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95460-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="95460-113">Attributes</span></span>  
  
|<span data-ttu-id="95460-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="95460-114">Attribute</span></span>|<span data-ttu-id="95460-115">Описание</span><span class="sxs-lookup"><span data-stu-id="95460-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="95460-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="95460-116">mapToWindows</span></span>|<span data-ttu-id="95460-117">Указывает ли обработчик токенов следует сопоставить маркер проверки в учетную запись Windows с помощью входящего утверждения имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="95460-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="95460-118">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="95460-118">The default is "false".</span></span>|  
|<span data-ttu-id="95460-119">issuerCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="95460-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="95460-120"><xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> Значение, определяющее режим отзыва для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="95460-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="95460-121">Значение по умолчанию — «В сети».</span><span class="sxs-lookup"><span data-stu-id="95460-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="95460-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="95460-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="95460-123"><xref:System.ServiceModel.Security.X509CertificateValidationMode> Значение, определяющее режим проверки для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="95460-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="95460-124">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="95460-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="95460-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="95460-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="95460-126">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, которое указывает хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="95460-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="95460-127">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="95460-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="95460-128">issuerCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="95460-128">issuerCertificateValidator</span></span>|<span data-ttu-id="95460-129">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="95460-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="95460-130">Если `issuerCertificateValidationMode` атрибут «Custom», экземпляр этого типа используется для проверки сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="95460-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="95460-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="95460-131">Child Elements</span></span>  
  
|<span data-ttu-id="95460-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="95460-132">Element</span></span>|<span data-ttu-id="95460-133">Описание</span><span class="sxs-lookup"><span data-stu-id="95460-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95460-134">\<nameClaimType ></span><span class="sxs-lookup"><span data-stu-id="95460-134">\<nameClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/nameclaimtype.md)|<span data-ttu-id="95460-135">Задает тип утверждения, указывающее <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="95460-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="95460-136">\<roleClaimType ></span><span class="sxs-lookup"><span data-stu-id="95460-136">\<roleClaimType></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/roleclaimtype.md)|<span data-ttu-id="95460-137">Указывает тип утверждения, определяет тип утверждения роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращенных <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> метод из обработчика токенов.</span><span class="sxs-lookup"><span data-stu-id="95460-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95460-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="95460-138">Parent Elements</span></span>  
  
|<span data-ttu-id="95460-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="95460-139">Element</span></span>|<span data-ttu-id="95460-140">Описание</span><span class="sxs-lookup"><span data-stu-id="95460-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95460-141">\<add></span><span class="sxs-lookup"><span data-stu-id="95460-141">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/add.md)|<span data-ttu-id="95460-142">Добавляет обработчик токенов безопасности в коллекцию обработчиков токенов.</span><span class="sxs-lookup"><span data-stu-id="95460-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95460-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="95460-143">Remarks</span></span>  
 <span data-ttu-id="95460-144">`<samlSecurityTokenRequirement>` Элемент, представленный объектом <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> класса в объектной модели и используется для настройки `SamlSecurityTokenRequirement` свойство <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> или <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span><span class="sxs-lookup"><span data-stu-id="95460-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95460-145">Пример</span><span class="sxs-lookup"><span data-stu-id="95460-145">Example</span></span>  
  
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
