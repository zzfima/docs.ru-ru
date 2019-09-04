---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 782ca3344774b8412a18e3cf13bff5f969751ea3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252144"
---
# <a name="certificatereference"></a><span data-ttu-id="1def0-101">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="1def0-101">\<certificateReference></span></span>
<span data-ttu-id="1def0-102">Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1def0-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
<span data-ttu-id="1def0-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1def0-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1def0-104">&nbsp;&nbsp;[ **\<> System. identityModel. Services**](system-identitymodel-services.md)</span><span class="sxs-lookup"><span data-stu-id="1def0-104">&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)</span></span>\
<span data-ttu-id="1def0-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<federationConfiguration >** ](federationconfiguration.md)</span><span class="sxs-lookup"><span data-stu-id="1def0-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)</span></span>\
<span data-ttu-id="1def0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCertificate >** ](servicecertificate.md)</span><span class="sxs-lookup"><span data-stu-id="1def0-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCertificate>**](servicecertificate.md)</span></span>\
<span data-ttu-id="1def0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<certificateReference >**</span><span class="sxs-lookup"><span data-stu-id="1def0-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificateReference>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1def0-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1def0-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1def0-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="1def0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="1def0-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="1def0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1def0-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="1def0-111">Attributes</span></span>  
  
|<span data-ttu-id="1def0-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="1def0-112">Attribute</span></span>|<span data-ttu-id="1def0-113">Описание</span><span class="sxs-lookup"><span data-stu-id="1def0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1def0-114">storeName</span><span class="sxs-lookup"><span data-stu-id="1def0-114">storeName</span></span>|<span data-ttu-id="1def0-115">Имя хранилища сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="1def0-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="1def0-116">Значение по умолчанию — "My".</span><span class="sxs-lookup"><span data-stu-id="1def0-116">The default is "My".</span></span> <span data-ttu-id="1def0-117">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1def0-117">Optional.</span></span>|  
|<span data-ttu-id="1def0-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="1def0-118">storeLocation</span></span>|<span data-ttu-id="1def0-119"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Значение, указывающее расположение хранилища сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="1def0-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="1def0-120">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="1def0-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="1def0-121">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1def0-121">Optional.</span></span>|  
|<span data-ttu-id="1def0-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="1def0-122">x509FindType</span></span>|<span data-ttu-id="1def0-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение типа, указывающее тип выполняемого поиска.</span><span class="sxs-lookup"><span data-stu-id="1def0-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="1def0-124">Значение по умолчанию — "Финдбисубжектдистингуишеднаме".</span><span class="sxs-lookup"><span data-stu-id="1def0-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="1def0-125">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1def0-125">Optional.</span></span>|  
|<span data-ttu-id="1def0-126">findValue</span><span class="sxs-lookup"><span data-stu-id="1def0-126">findValue</span></span>|<span data-ttu-id="1def0-127">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="1def0-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="1def0-128">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1def0-128">Optional.</span></span>|  
|<span data-ttu-id="1def0-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="1def0-129">isChainIncluded</span></span>|<span data-ttu-id="1def0-130">Указывает, следует ли выполнять проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1def0-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="1def0-131">Значение по умолчанию — true; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1def0-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="1def0-132">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="1def0-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1def0-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="1def0-133">Child Elements</span></span>  
 <span data-ttu-id="1def0-134">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="1def0-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1def0-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="1def0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="1def0-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="1def0-136">Element</span></span>|<span data-ttu-id="1def0-137">Описание</span><span class="sxs-lookup"><span data-stu-id="1def0-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1def0-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="1def0-138">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="1def0-139">Настраивает сертификат, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="1def0-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1def0-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="1def0-140">Remarks</span></span>  
 <span data-ttu-id="1def0-141">`<certificateReference>` Элемент задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1def0-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="1def0-142">Если он указан как дочерний элемент `<serviceCertificate>` , он указывает параметры расположения и проверки сертификата X. 509, который используется для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="1def0-142">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="1def0-143">`<certificateReference>` Элемент представлен<xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.</span><span class="sxs-lookup"><span data-stu-id="1def0-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
