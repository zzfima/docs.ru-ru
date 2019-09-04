---
title: <samlSecurityTokenRequirement>
ms.date: 03/30/2017
ms.assetid: 09202d12-88d3-49cc-953b-703bcc1690eb
author: BrucePerlerMS
ms.openlocfilehash: cab7572518a7a6dc26f8bbcf67cd424fa1c01085
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251899"
---
# <a name="samlsecuritytokenrequirement"></a><span data-ttu-id="870d2-101">\<samlSecurityTokenRequirement></span><span class="sxs-lookup"><span data-stu-id="870d2-101">\<samlSecurityTokenRequirement></span></span>
<span data-ttu-id="870d2-102">Предоставляет конфигурацию для <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> класса <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> , класса или производного класса любого из этих классов.</span><span class="sxs-lookup"><span data-stu-id="870d2-102">Provides configuration for the <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> class, the <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> class, or a derived class of either of these classes.</span></span> <span data-ttu-id="870d2-103">Представляется <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом.</span><span class="sxs-lookup"><span data-stu-id="870d2-103">Represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class.</span></span>  
  
<span data-ttu-id="870d2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="870d2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="870d2-105">&nbsp;&nbsp;[ **\<> System. identityModel**](system-identitymodel.md)</span><span class="sxs-lookup"><span data-stu-id="870d2-105">&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)</span></span>\
<span data-ttu-id="870d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<identityConfiguration >** ](identityconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="870d2-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)</span></span>\
<span data-ttu-id="870d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<securityTokenHandlers >** ](securitytokenhandlers.md)</span><span class="sxs-lookup"><span data-stu-id="870d2-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)</span></span>\
<span data-ttu-id="870d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Добавить >** ](add.md)</span><span class="sxs-lookup"><span data-stu-id="870d2-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add.md)</span></span>\
<span data-ttu-id="870d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<samlSecurityTokenRequirement >**</span><span class="sxs-lookup"><span data-stu-id="870d2-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<samlSecurityTokenRequirement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870d2-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="870d2-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="870d2-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="870d2-111">Attributes and Elements</span></span>  
 <span data-ttu-id="870d2-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="870d2-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="870d2-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="870d2-113">Attributes</span></span>  
  
|<span data-ttu-id="870d2-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="870d2-114">Attribute</span></span>|<span data-ttu-id="870d2-115">Описание</span><span class="sxs-lookup"><span data-stu-id="870d2-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="870d2-116">mapToWindows</span><span class="sxs-lookup"><span data-stu-id="870d2-116">mapToWindows</span></span>|<span data-ttu-id="870d2-117">Указывает, должен ли обработчик маркера сопоставлять проверяющий токен с учетной записью Windows, используя входящее утверждение имени участника-пользователя.</span><span class="sxs-lookup"><span data-stu-id="870d2-117">Specifies whether the token handler should map the validating token to a Windows account by using the incoming UPN claim.</span></span> <span data-ttu-id="870d2-118">Значение по умолчанию — false.</span><span class="sxs-lookup"><span data-stu-id="870d2-118">The default is "false".</span></span>|  
|<span data-ttu-id="870d2-119">иссуерцертификатеревокатионмоде</span><span class="sxs-lookup"><span data-stu-id="870d2-119">issuerCertificateRevocationMode</span></span>|<span data-ttu-id="870d2-120">Значение <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> типа, указывающее режим отзыва, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="870d2-120">An <xref:System.Security.Cryptography.X509Certificates.X509RevocationMode> value that specifies the revocation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="870d2-121">Значение по умолчанию — "Online".</span><span class="sxs-lookup"><span data-stu-id="870d2-121">The default value is "Online".</span></span>|  
|<span data-ttu-id="870d2-122">иссуерцертификатевалидатионмоде</span><span class="sxs-lookup"><span data-stu-id="870d2-122">issuerCertificateValidationMode</span></span>|<span data-ttu-id="870d2-123">Значение <xref:System.ServiceModel.Security.X509CertificateValidationMode> типа, указывающее режим проверки, используемый для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="870d2-123">An <xref:System.ServiceModel.Security.X509CertificateValidationMode> value that specifies the validation mode to use for the X.509 certificate.</span></span> <span data-ttu-id="870d2-124">Значение по умолчанию — "PeerOrChainTrust".</span><span class="sxs-lookup"><span data-stu-id="870d2-124">The default value is "PeerOrChainTrust".</span></span>|  
|<span data-ttu-id="870d2-125">иссуерцертификатетрустедсторелокатион</span><span class="sxs-lookup"><span data-stu-id="870d2-125">issuerCertificateTrustedStoreLocation</span></span>|<span data-ttu-id="870d2-126">Значение <xref:System.Security.Cryptography.X509Certificates.StoreLocation> типа, указывающее хранилище сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="870d2-126">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the X.509 certificate store.</span></span> <span data-ttu-id="870d2-127">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="870d2-127">The default value is "LocalMachine".</span></span>|  
|<span data-ttu-id="870d2-128">иссуерцертификатевалидатор</span><span class="sxs-lookup"><span data-stu-id="870d2-128">issuerCertificateValidator</span></span>|<span data-ttu-id="870d2-129">Пользовательский тип, производный от <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="870d2-129">A custom type that derives from <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span></span> <span data-ttu-id="870d2-130">`issuerCertificateValidationMode` Если атрибут имеет значение Custom, для проверки сертификата издателя используется экземпляр этого типа.</span><span class="sxs-lookup"><span data-stu-id="870d2-130">If the `issuerCertificateValidationMode` attribute is "Custom", an instance of this type is used for issuer certificate validation.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="870d2-131">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="870d2-131">Child Elements</span></span>  
  
|<span data-ttu-id="870d2-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="870d2-132">Element</span></span>|<span data-ttu-id="870d2-133">Описание</span><span class="sxs-lookup"><span data-stu-id="870d2-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="870d2-134">\<Намеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="870d2-134">\<nameClaimType></span></span>](nameclaimtype.md)|<span data-ttu-id="870d2-135">Задает тип утверждения, указывающий <xref:System.Security.Principal.IIdentity.Name%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="870d2-135">Sets the claim type that specifies the <xref:System.Security.Principal.IIdentity.Name%2A> property.</span></span>|  
|[<span data-ttu-id="870d2-136">\<Ролеклаимтипе ></span><span class="sxs-lookup"><span data-stu-id="870d2-136">\<roleClaimType></span></span>](roleclaimtype.md)|<span data-ttu-id="870d2-137">Указывает тип утверждения, определяющего утверждения типа роли в коллекции <xref:System.Security.Claims.ClaimsIdentity> объектов, возвращаемых <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> методом обработчика маркеров.</span><span class="sxs-lookup"><span data-stu-id="870d2-137">Specifies the claim type that defines the role type claims in the collection of <xref:System.Security.Claims.ClaimsIdentity> objects returned by the <xref:System.IdentityModel.Tokens.SecurityTokenHandler.ValidateToken%2A> method of the token handler.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="870d2-138">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="870d2-138">Parent Elements</span></span>  
  
|<span data-ttu-id="870d2-139">Элемент</span><span class="sxs-lookup"><span data-stu-id="870d2-139">Element</span></span>|<span data-ttu-id="870d2-140">Описание</span><span class="sxs-lookup"><span data-stu-id="870d2-140">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="870d2-141">\<add></span><span class="sxs-lookup"><span data-stu-id="870d2-141">\<add></span></span>](add.md)|<span data-ttu-id="870d2-142">Добавляет указанный обработчик маркеров безопасности в коллекцию обработчиков маркеров.</span><span class="sxs-lookup"><span data-stu-id="870d2-142">Adds the specified security token handler to the token handler collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="870d2-143">Примечания</span><span class="sxs-lookup"><span data-stu-id="870d2-143">Remarks</span></span>  
 <span data-ttu-id="870d2-144"><xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler> <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> `SamlSecurityTokenRequirement` Элемент представлен <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> классом в объектной модели и используется для настройки свойства в или. `<samlSecurityTokenRequirement>`</span><span class="sxs-lookup"><span data-stu-id="870d2-144">The `<samlSecurityTokenRequirement>` element is represented by the <xref:System.IdentityModel.Tokens.SamlSecurityTokenRequirement> class in the object model and is used to configure the `SamlSecurityTokenRequirement` property on a <xref:System.IdentityModel.Tokens.SamlSecurityTokenHandler> or a <xref:System.IdentityModel.Tokens.Saml2SecurityTokenHandler>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="870d2-145">Пример</span><span class="sxs-lookup"><span data-stu-id="870d2-145">Example</span></span>  
  
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
