---
title: '&lt;certificateReference&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: c8acf4b6d6e6e8a0fcf7d73139a1d2c5ea03f063
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="fa9aa-102">&lt;certificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="fa9aa-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="fa9aa-103">Указывает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="fa9aa-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="fa9aa-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="fa9aa-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="fa9aa-105">\<federationConfiguration></span></span>  
<span data-ttu-id="fa9aa-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="fa9aa-106">\<serviceCertificate></span></span>  
<span data-ttu-id="fa9aa-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="fa9aa-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa9aa-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fa9aa-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa9aa-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="fa9aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fa9aa-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa9aa-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="fa9aa-111">Attributes</span></span>  
  
|<span data-ttu-id="fa9aa-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="fa9aa-112">Attribute</span></span>|<span data-ttu-id="fa9aa-113">Описание</span><span class="sxs-lookup"><span data-stu-id="fa9aa-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa9aa-114">storeName</span><span class="sxs-lookup"><span data-stu-id="fa9aa-114">storeName</span></span>|<span data-ttu-id="fa9aa-115">Имя хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="fa9aa-116">Значение по умолчанию — «My».</span><span class="sxs-lookup"><span data-stu-id="fa9aa-116">The default is "My".</span></span> <span data-ttu-id="fa9aa-117">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-117">Optional.</span></span>|  
|<span data-ttu-id="fa9aa-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="fa9aa-118">storeLocation</span></span>|<span data-ttu-id="fa9aa-119">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="fa9aa-120">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="fa9aa-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="fa9aa-121">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-121">Optional.</span></span>|  
|<span data-ttu-id="fa9aa-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="fa9aa-122">x509FindType</span></span>|<span data-ttu-id="fa9aa-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, указывающее тип выполняемого поиска, должно быть выполнено.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="fa9aa-124">Значение по умолчанию — «FindBySubjectDistinguishedName».</span><span class="sxs-lookup"><span data-stu-id="fa9aa-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="fa9aa-125">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-125">Optional.</span></span>|  
|<span data-ttu-id="fa9aa-126">findValue</span><span class="sxs-lookup"><span data-stu-id="fa9aa-126">findValue</span></span>|<span data-ttu-id="fa9aa-127">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="fa9aa-128">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-128">Optional.</span></span>|  
|<span data-ttu-id="fa9aa-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="fa9aa-129">isChainIncluded</span></span>|<span data-ttu-id="fa9aa-130">Указывает, следует ли выполнять проверки с с использованием цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="fa9aa-131">Значение по умолчанию — «true»; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="fa9aa-132">Необязательно.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa9aa-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="fa9aa-133">Child Elements</span></span>  
 <span data-ttu-id="fa9aa-134">Нет</span><span class="sxs-lookup"><span data-stu-id="fa9aa-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa9aa-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="fa9aa-135">Parent Elements</span></span>  
  
|<span data-ttu-id="fa9aa-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="fa9aa-136">Element</span></span>|<span data-ttu-id="fa9aa-137">Описание</span><span class="sxs-lookup"><span data-stu-id="fa9aa-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa9aa-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="fa9aa-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="fa9aa-139">Настраивает сертификат, используемый для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa9aa-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="fa9aa-140">Remarks</span></span>  
 <span data-ttu-id="fa9aa-141">`<certificateReference>` Элемент задает параметры, используемые для поиска и проверки сертификатов в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="fa9aa-142">Когда он указан как дочерний элемент элемента `<serviceCertficate>` элемент задает параметры расположения и проверки сертификата X.509, используемый для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="fa9aa-143">`<certificateReference>` Представлен <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.</span><span class="sxs-lookup"><span data-stu-id="fa9aa-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
