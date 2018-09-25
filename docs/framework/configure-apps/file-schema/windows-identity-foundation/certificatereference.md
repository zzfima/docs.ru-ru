---
title: '&lt;CertificateReference&gt;'
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: e04dc90134aadfb8af7b0800c7144963d267f513
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47075087"
---
# <a name="ltcertificatereferencegt"></a><span data-ttu-id="3b028-102">&lt;CertificateReference&gt;</span><span class="sxs-lookup"><span data-stu-id="3b028-102">&lt;certificateReference&gt;</span></span>
<span data-ttu-id="3b028-103">Задает параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3b028-103">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="3b028-104">\<system.identityModel.services ></span><span class="sxs-lookup"><span data-stu-id="3b028-104">\<system.identityModel.services></span></span>  
<span data-ttu-id="3b028-105">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3b028-105">\<federationConfiguration></span></span>  
<span data-ttu-id="3b028-106">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3b028-106">\<serviceCertificate></span></span>  
<span data-ttu-id="3b028-107">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="3b028-107">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b028-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b028-108">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3b028-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3b028-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3b028-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3b028-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3b028-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3b028-111">Attributes</span></span>  
  
|<span data-ttu-id="3b028-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3b028-112">Attribute</span></span>|<span data-ttu-id="3b028-113">Описание</span><span class="sxs-lookup"><span data-stu-id="3b028-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3b028-114">storeName</span><span class="sxs-lookup"><span data-stu-id="3b028-114">storeName</span></span>|<span data-ttu-id="3b028-115">Имя хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="3b028-115">The name of the X.509 certificate store.</span></span> <span data-ttu-id="3b028-116">Значение по умолчанию — «My».</span><span class="sxs-lookup"><span data-stu-id="3b028-116">The default is "My".</span></span> <span data-ttu-id="3b028-117">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3b028-117">Optional.</span></span>|  
|<span data-ttu-id="3b028-118">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3b028-118">storeLocation</span></span>|<span data-ttu-id="3b028-119">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="3b028-119">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="3b028-120">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="3b028-120">The default value is "LocalMachine".</span></span> <span data-ttu-id="3b028-121">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3b028-121">Optional.</span></span>|  
|<span data-ttu-id="3b028-122">x509FindType</span><span class="sxs-lookup"><span data-stu-id="3b028-122">x509FindType</span></span>|<span data-ttu-id="3b028-123"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, указывающее тип выполняемого поиска, который должен выполняться.</span><span class="sxs-lookup"><span data-stu-id="3b028-123">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="3b028-124">Значение по умолчанию — «FindBySubjectDistinguishedName».</span><span class="sxs-lookup"><span data-stu-id="3b028-124">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="3b028-125">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3b028-125">Optional.</span></span>|  
|<span data-ttu-id="3b028-126">findValue</span><span class="sxs-lookup"><span data-stu-id="3b028-126">findValue</span></span>|<span data-ttu-id="3b028-127">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="3b028-127">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="3b028-128">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3b028-128">Optional.</span></span>|  
|<span data-ttu-id="3b028-129">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="3b028-129">isChainIncluded</span></span>|<span data-ttu-id="3b028-130">Указывает, нужно ли выполнять проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3b028-130">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="3b028-131">Значение по умолчанию равно «true»; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3b028-131">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="3b028-132">Необязательный.</span><span class="sxs-lookup"><span data-stu-id="3b028-132">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3b028-133">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3b028-133">Child Elements</span></span>  
 <span data-ttu-id="3b028-134">Нет</span><span class="sxs-lookup"><span data-stu-id="3b028-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3b028-135">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3b028-135">Parent Elements</span></span>  
  
|<span data-ttu-id="3b028-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="3b028-136">Element</span></span>|<span data-ttu-id="3b028-137">Описание</span><span class="sxs-lookup"><span data-stu-id="3b028-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3b028-138">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3b028-138">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="3b028-139">Настраивает сертификат, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="3b028-139">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b028-140">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b028-140">Remarks</span></span>  
 <span data-ttu-id="3b028-141">`<certificateReference>` Элемент определяет параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3b028-141">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="3b028-142">Когда он указан как дочерний элемент `<serviceCertficate>` , он указывает расположение и проверки параметров сертификата X.509, который используется для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="3b028-142">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="3b028-143">`<certificateReference>` Элемент, представленный объектом <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.</span><span class="sxs-lookup"><span data-stu-id="3b028-143">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
