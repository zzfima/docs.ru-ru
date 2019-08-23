---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: da8ea128466457409334cd0b4ee3246a923f969a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69941931"
---
# <a name="certificatereference"></a><span data-ttu-id="3ef58-101">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="3ef58-101">\<certificateReference></span></span>
<span data-ttu-id="3ef58-102">Задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3ef58-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="3ef58-103">\<> System. identityModel. Services</span><span class="sxs-lookup"><span data-stu-id="3ef58-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="3ef58-104">\<federationConfiguration ></span><span class="sxs-lookup"><span data-stu-id="3ef58-104">\<federationConfiguration></span></span>  
<span data-ttu-id="3ef58-105">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3ef58-105">\<serviceCertificate></span></span>  
<span data-ttu-id="3ef58-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="3ef58-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef58-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3ef58-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3ef58-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3ef58-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3ef58-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3ef58-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3ef58-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3ef58-110">Attributes</span></span>  
  
|<span data-ttu-id="3ef58-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3ef58-111">Attribute</span></span>|<span data-ttu-id="3ef58-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3ef58-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3ef58-113">storeName</span><span class="sxs-lookup"><span data-stu-id="3ef58-113">storeName</span></span>|<span data-ttu-id="3ef58-114">Имя хранилища сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="3ef58-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="3ef58-115">Значение по умолчанию — "My".</span><span class="sxs-lookup"><span data-stu-id="3ef58-115">The default is "My".</span></span> <span data-ttu-id="3ef58-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3ef58-116">Optional.</span></span>|  
|<span data-ttu-id="3ef58-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="3ef58-117">storeLocation</span></span>|<span data-ttu-id="3ef58-118"><xref:System.Security.Cryptography.X509Certificates.StoreLocation> Значение, указывающее расположение хранилища сертификатов X. 509.</span><span class="sxs-lookup"><span data-stu-id="3ef58-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="3ef58-119">Значение по умолчанию — LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="3ef58-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="3ef58-120">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3ef58-120">Optional.</span></span>|  
|<span data-ttu-id="3ef58-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="3ef58-121">x509FindType</span></span>|<span data-ttu-id="3ef58-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение типа, указывающее тип выполняемого поиска.</span><span class="sxs-lookup"><span data-stu-id="3ef58-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="3ef58-123">Значение по умолчанию — "Финдбисубжектдистингуишеднаме".</span><span class="sxs-lookup"><span data-stu-id="3ef58-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="3ef58-124">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3ef58-124">Optional.</span></span>|  
|<span data-ttu-id="3ef58-125">findValue</span><span class="sxs-lookup"><span data-stu-id="3ef58-125">findValue</span></span>|<span data-ttu-id="3ef58-126">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="3ef58-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="3ef58-127">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3ef58-127">Optional.</span></span>|  
|<span data-ttu-id="3ef58-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="3ef58-128">isChainIncluded</span></span>|<span data-ttu-id="3ef58-129">Указывает, следует ли выполнять проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3ef58-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="3ef58-130">Значение по умолчанию — true; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3ef58-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="3ef58-131">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="3ef58-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3ef58-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3ef58-132">Child Elements</span></span>  
 <span data-ttu-id="3ef58-133">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="3ef58-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3ef58-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3ef58-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3ef58-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="3ef58-135">Element</span></span>|<span data-ttu-id="3ef58-136">Описание</span><span class="sxs-lookup"><span data-stu-id="3ef58-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3ef58-137">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="3ef58-137">\<serviceCertificate></span></span>](servicecertificate.md)|<span data-ttu-id="3ef58-138">Настраивает сертификат, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="3ef58-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ef58-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="3ef58-139">Remarks</span></span>  
 <span data-ttu-id="3ef58-140">`<certificateReference>` Элемент задает параметры, используемые для поиска и проверки сертификата X. 509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3ef58-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="3ef58-141">Если он указан как дочерний элемент `<serviceCertificate>` , он указывает параметры расположения и проверки сертификата X. 509, который используется для шифрования и расшифровки токенов.</span><span class="sxs-lookup"><span data-stu-id="3ef58-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="3ef58-142">`<certificateReference>` Элемент представлен<xref:System.ServiceModel.Configuration.CertificateReferenceElement> классом.</span><span class="sxs-lookup"><span data-stu-id="3ef58-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
