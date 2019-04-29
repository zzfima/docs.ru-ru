---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: 6c9c77f96ff6032de43d9b5a257bc0796a19b858
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667383"
---
# <a name="certificatereference"></a><span data-ttu-id="88e57-101">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="88e57-101">\<certificateReference></span></span>
<span data-ttu-id="88e57-102">Задает параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="88e57-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="88e57-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="88e57-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="88e57-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="88e57-104">\<federationConfiguration></span></span>  
<span data-ttu-id="88e57-105">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="88e57-105">\<serviceCertificate></span></span>  
<span data-ttu-id="88e57-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="88e57-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88e57-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88e57-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="88e57-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="88e57-108">Attributes and Elements</span></span>  
 <span data-ttu-id="88e57-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="88e57-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="88e57-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="88e57-110">Attributes</span></span>  
  
|<span data-ttu-id="88e57-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="88e57-111">Attribute</span></span>|<span data-ttu-id="88e57-112">Описание</span><span class="sxs-lookup"><span data-stu-id="88e57-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="88e57-113">storeName</span><span class="sxs-lookup"><span data-stu-id="88e57-113">storeName</span></span>|<span data-ttu-id="88e57-114">Имя хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="88e57-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="88e57-115">Значение по умолчанию — «My».</span><span class="sxs-lookup"><span data-stu-id="88e57-115">The default is "My".</span></span> <span data-ttu-id="88e57-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="88e57-116">Optional.</span></span>|  
|<span data-ttu-id="88e57-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="88e57-117">storeLocation</span></span>|<span data-ttu-id="88e57-118">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="88e57-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="88e57-119">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="88e57-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="88e57-120">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="88e57-120">Optional.</span></span>|  
|<span data-ttu-id="88e57-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="88e57-121">x509FindType</span></span>|<span data-ttu-id="88e57-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, указывающее тип выполняемого поиска, который должен выполняться.</span><span class="sxs-lookup"><span data-stu-id="88e57-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="88e57-123">Значение по умолчанию — «FindBySubjectDistinguishedName».</span><span class="sxs-lookup"><span data-stu-id="88e57-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="88e57-124">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="88e57-124">Optional.</span></span>|  
|<span data-ttu-id="88e57-125">findValue</span><span class="sxs-lookup"><span data-stu-id="88e57-125">findValue</span></span>|<span data-ttu-id="88e57-126">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="88e57-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="88e57-127">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="88e57-127">Optional.</span></span>|  
|<span data-ttu-id="88e57-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="88e57-128">isChainIncluded</span></span>|<span data-ttu-id="88e57-129">Указывает, нужно ли выполнять проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="88e57-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="88e57-130">Значение по умолчанию равно «true»; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="88e57-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="88e57-131">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="88e57-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="88e57-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="88e57-132">Child Elements</span></span>  
 <span data-ttu-id="88e57-133">Нет</span><span class="sxs-lookup"><span data-stu-id="88e57-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="88e57-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="88e57-134">Parent Elements</span></span>  
  
|<span data-ttu-id="88e57-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="88e57-135">Element</span></span>|<span data-ttu-id="88e57-136">Описание</span><span class="sxs-lookup"><span data-stu-id="88e57-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="88e57-137">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="88e57-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="88e57-138">Настраивает сертификат, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="88e57-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="88e57-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="88e57-139">Remarks</span></span>  
 <span data-ttu-id="88e57-140">`<certificateReference>` Элемент определяет параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="88e57-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="88e57-141">Когда он указан как дочерний элемент `<serviceCertficate>` , он указывает расположение и проверки параметров сертификата X.509, который используется для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="88e57-141">When it is specified as the child element of the `<serviceCertficate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="88e57-142">`<certificateReference>` Элемент, представленный объектом <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.</span><span class="sxs-lookup"><span data-stu-id="88e57-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
