---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: b27f337189a7d0b66ffd38e032b5eb864e5094a1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152636"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="fc820-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="fc820-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="fc820-102">Обеспечивает конфигурацию <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> для <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> класса, класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="fc820-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="fc820-103">Представлено классом. <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="fc820-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="fc820-104">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fc820-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fc820-105">&nbsp;&nbsp;[**\<system.identityМодель>**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="fc820-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="fc820-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<идентичностьНастройка>**](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="fc820-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="fc820-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="fc820-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="fc820-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<добавить>**](add.md)</span><span class="sxs-lookup"><span data-stu-id="fc820-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="fc820-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span><span class="sxs-lookup"><span data-stu-id="fc820-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc820-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fc820-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc820-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fc820-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fc820-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fc820-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc820-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fc820-113">Attributes</span></span>  
  
|<span data-ttu-id="fc820-114">attribute</span><span class="sxs-lookup"><span data-stu-id="fc820-114">Attribute</span></span>|<span data-ttu-id="fc820-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fc820-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fc820-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="fc820-116">mapToWindows</span></span>|<span data-ttu-id="fc820-117">Уточняется, следует ли обработчику маркеров отображения токена проверки в учетную запись Windows с помощью входящего требования UPN.</span><span class="sxs-lookup"><span data-stu-id="fc820-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="fc820-118">Значение по умолчанию — «false».</span><span class="sxs-lookup"><span data-stu-id="fc820-118">The default is "false".</span></span>|  
|<span data-ttu-id="fc820-119">эмитентCertificateRevocationMode</span><span class="sxs-lookup"><span data-stu-id="fc820-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="fc820-120">Значение, <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> оговариваев режим отзыва для использования для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="fc820-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="fc820-121">Значение по умолчанию "Онлайн".</span><span class="sxs-lookup"><span data-stu-id="fc820-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="fc820-122">issuerCertificateValidationMode</span><span class="sxs-lookup"><span data-stu-id="fc820-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="fc820-123">Значение, <xref:System.ServiceModel.Security.X509CertificateValidationMode> опознавававававрежим проверки для использования для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="fc820-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="fc820-124">Значение по умолчанию — «PeerOrChainTrust».</span><span class="sxs-lookup"><span data-stu-id="fc820-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="fc820-125">issuerCertificateTrustedStoreLocation</span><span class="sxs-lookup"><span data-stu-id="fc820-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="fc820-126">Значение, <xref:System.Security.Cryptography.X509Certificates.StoreLocation> опоедая магазин сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="fc820-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="fc820-127">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="fc820-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="fc820-128">эмитентCertificateValidator</span><span class="sxs-lookup"><span data-stu-id="fc820-128">issuerCertificateValidator</span></span>|<span data-ttu-id="fc820-129">Пользовательский тип, который <xref:System.IdentityModel.Selectors.X509CertificateValidator>происходит от .</span><span class="sxs-lookup"><span data-stu-id="fc820-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="fc820-130">Если `issuerCertificateValidationMode` атрибут является "Custom", экземпляр этого типа используется для проверки сертификата эмитента.</span><span class="sxs-lookup"><span data-stu-id="fc820-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc820-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fc820-131">Child Elements</span></span>  
  
|<span data-ttu-id="fc820-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc820-132">Element</span></span>|<span data-ttu-id="fc820-133">Описание</span><span class="sxs-lookup"><span data-stu-id="fc820-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc820-134">\<nameClaimType></span><span class="sxs-lookup"><span data-stu-id="fc820-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="fc820-135">Устанавливает тип претензии, который <xref:System.Security.Principal.IIdentity.Name%2A> определяет свойство.</span><span class="sxs-lookup"><span data-stu-id="fc820-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="fc820-136">\<roleClaimType></span><span class="sxs-lookup"><span data-stu-id="fc820-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="fc820-137">Определяет тип претензии, определяющий требования типа роли <xref:System.Security.Claims.ClaimsIdentity> в сборе <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> объектов, возвращенных методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="fc820-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc820-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fc820-138">Parent Elements</span></span>  
  
|<span data-ttu-id="fc820-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="fc820-139">Element</span></span>|<span data-ttu-id="fc820-140">Описание</span><span class="sxs-lookup"><span data-stu-id="fc820-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc820-141">\<добавить></span><span class="sxs-lookup"><span data-stu-id="fc820-141">\<add></span></span>](add.md)|<span data-ttu-id="fc820-142">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="fc820-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc820-143">Remarks</span><span class="sxs-lookup"><span data-stu-id="fc820-143">Remarks</span></span>  
 <span data-ttu-id="fc820-144">Элемент `<samlSecurityTokenRequirement>` представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в модели объекта и используется для `SamlSecurityTokenRequirement` настройки <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> свойства <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>на или .</span><span class="sxs-lookup"><span data-stu-id="fc820-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc820-145">Пример</span><span class="sxs-lookup"><span data-stu-id="fc820-145">Example</span></span>  
  
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
