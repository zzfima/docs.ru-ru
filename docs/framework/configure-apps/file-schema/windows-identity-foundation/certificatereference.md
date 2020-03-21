---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 47d432a84d070476ddffd9b98a4ba46d8163bdc3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79152818"
---
# <a name="certificatereference"></a><span data-ttu-id="adae0-101">\<сертификатСправка></span><span class="sxs-lookup"><span data-stu-id="adae0-101">\<certificateReference></span></span>
<span data-ttu-id="adae0-102">Определяет настройки, которые используются для поиска и проверки сертификата X.509 в магазине сертификатов.</span><span class="sxs-lookup"><span data-stu-id="adae0-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="adae0-103">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="adae0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="adae0-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="adae0-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="adae0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<федерацияКонфигурация>**](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="adae0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="adae0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>сервис-сертификат**](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="adae0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="adae0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<сертификатСправка>**</span><span class="sxs-lookup"><span data-stu-id="adae0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="adae0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="adae0-108">Syntax</span></span>  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <serviceCertificate>  
      <certificateReference
        storeName="AddressBook||AuthRoot||CertificateAuthority||Disallowed||My||Root||TrustedPeople||TrustedPublisher"  
        storeLocation="CurrentUser||LocalMachine"  
        x509FindType="FindByThumbprint||FindBySubjectName||FindBySubjectDistinguishedName||FindByIssuerName||FindByIssuerDistinguishedName||FindBySerialNumber||FindByTimeValid||FindByTimeNotYetValid||FindByTimeExpired||FindByTemplateName||FindByApplicationPolicy||FindByCertificatePolicy||FindByExtension||FindByKeyUsage||FindBySubjectKeyIdentifier"  
        findValue=xs:String  
        isChainIncluded=xs:Boolean >  
      </certificateReference>  
    </serviceCertificate>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="adae0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="adae0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="adae0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="adae0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="adae0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="adae0-111">Attributes</span></span>  
  
|<span data-ttu-id="adae0-112">attribute</span><span class="sxs-lookup"><span data-stu-id="adae0-112">Attribute</span></span>|<span data-ttu-id="adae0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="adae0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="adae0-114">storeName</span><span class="sxs-lookup"><span data-stu-id="adae0-114">storeName</span></span>|<span data-ttu-id="adae0-115">Имя хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="adae0-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="adae0-116">По умолчанию "Мой".</span><span class="sxs-lookup"><span data-stu-id="adae0-116">The default is "My".</span></span> <span data-ttu-id="adae0-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="adae0-117">Optional.</span></span>|  
|<span data-ttu-id="adae0-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="adae0-118">storeLocation</span></span>|<span data-ttu-id="adae0-119">Значение, <xref:System.Security.Cryptography.X509Certificates.StoreLocation> опоглавивававаев оместонахождение магазина сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="adae0-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="adae0-120">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="adae0-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="adae0-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="adae0-121">Optional.</span></span>|  
|<span data-ttu-id="adae0-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="adae0-122">x509FindType</span></span>|<span data-ttu-id="adae0-123">Значение, <xref:System.Security.Cryptography.X509Certificates.X509FindType> описавававававаемый тип поиска, который должен быть выполнен.</span><span class="sxs-lookup"><span data-stu-id="adae0-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="adae0-124">По умолчанию является "FindBySubjectDistinguishedName".</span><span class="sxs-lookup"><span data-stu-id="adae0-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="adae0-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="adae0-125">Optional.</span></span>|  
|<span data-ttu-id="adae0-126">findValue</span><span class="sxs-lookup"><span data-stu-id="adae0-126">findValue</span></span>|<span data-ttu-id="adae0-127">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="adae0-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="adae0-128">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="adae0-128">Optional.</span></span>|  
|<span data-ttu-id="adae0-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="adae0-129">isChainIncluded</span></span>|<span data-ttu-id="adae0-130">Уточняется, следует ли проводить проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="adae0-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="adae0-131">По умолчанию является "истинным"; проверка осуществляется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="adae0-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="adae0-132">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="adae0-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="adae0-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="adae0-133">Child Elements</span></span>  
 <span data-ttu-id="adae0-134">None</span><span class="sxs-lookup"><span data-stu-id="adae0-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="adae0-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="adae0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="adae0-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="adae0-136">Element</span></span>|<span data-ttu-id="adae0-137">Описание</span><span class="sxs-lookup"><span data-stu-id="adae0-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="adae0-138">\<>сервис-сертификат</span><span class="sxs-lookup"><span data-stu-id="adae0-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="adae0-139">Настраивает сертификат, который используется для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="adae0-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adae0-140">Remarks</span><span class="sxs-lookup"><span data-stu-id="adae0-140">Remarks</span></span>  
 <span data-ttu-id="adae0-141">Элемент `<certificateReference>` определяет параметры, которые используются для поиска и проверки сертификата X.509 в магазине сертификатов.</span><span class="sxs-lookup"><span data-stu-id="adae0-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="adae0-142">Когда он указан в качестве `<serviceCertificate>` элемента элемента ребенка, он определяет настройки местоположения и проверки сертификата X.509, который используется для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="adae0-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="adae0-143">Элемент `<certificateReference>` представлен <xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.</span><span class="sxs-lookup"><span data-stu-id="adae0-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
