---
title: <certificateReference>
ms.date: 03/30/2017
ms.assetid: 2ac8bc14-e9f1-48fb-b662-f5991558fbe4
author: BrucePerlerMS
ms.openlocfilehash: c7dc9cfff15e70eff0086cfd98a19f3360ab8bb0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423031"
---
# <a name="certificatereference"></a><span data-ttu-id="df2c4-101">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="df2c4-101">\<certificateReference></span></span>
<span data-ttu-id="df2c4-102">Задает параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="df2c4-102">Specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span>  
  
 <span data-ttu-id="df2c4-103">\<system.identityModel.services></span><span class="sxs-lookup"><span data-stu-id="df2c4-103">\<system.identityModel.services></span></span>  
<span data-ttu-id="df2c4-104">\<federationConfiguration></span><span class="sxs-lookup"><span data-stu-id="df2c4-104">\<federationConfiguration></span></span>  
<span data-ttu-id="df2c4-105">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="df2c4-105">\<serviceCertificate></span></span>  
<span data-ttu-id="df2c4-106">\<certificateReference ></span><span class="sxs-lookup"><span data-stu-id="df2c4-106">\<certificateReference></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2c4-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df2c4-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df2c4-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="df2c4-108">Attributes and Elements</span></span>  
 <span data-ttu-id="df2c4-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="df2c4-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df2c4-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="df2c4-110">Attributes</span></span>  
  
|<span data-ttu-id="df2c4-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="df2c4-111">Attribute</span></span>|<span data-ttu-id="df2c4-112">Описание</span><span class="sxs-lookup"><span data-stu-id="df2c4-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="df2c4-113">storeName</span><span class="sxs-lookup"><span data-stu-id="df2c4-113">storeName</span></span>|<span data-ttu-id="df2c4-114">Имя хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="df2c4-114">The name of the X.509 certificate store.</span></span> <span data-ttu-id="df2c4-115">Значение по умолчанию — «My».</span><span class="sxs-lookup"><span data-stu-id="df2c4-115">The default is "My".</span></span> <span data-ttu-id="df2c4-116">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="df2c4-116">Optional.</span></span>|  
|<span data-ttu-id="df2c4-117">storeLocation</span><span class="sxs-lookup"><span data-stu-id="df2c4-117">storeLocation</span></span>|<span data-ttu-id="df2c4-118">Объект <xref:System.Security.Cryptography.X509Certificates.StoreLocation> значение, указывающее расположение хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="df2c4-118">A <xref:System.Security.Cryptography.X509Certificates.StoreLocation> value that specifies the location of the X.509 certificate store.</span></span> <span data-ttu-id="df2c4-119">Значение по умолчанию — «LocalMachine».</span><span class="sxs-lookup"><span data-stu-id="df2c4-119">The default value is "LocalMachine".</span></span> <span data-ttu-id="df2c4-120">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="df2c4-120">Optional.</span></span>|  
|<span data-ttu-id="df2c4-121">x509FindType</span><span class="sxs-lookup"><span data-stu-id="df2c4-121">x509FindType</span></span>|<span data-ttu-id="df2c4-122"><xref:System.Security.Cryptography.X509Certificates.X509FindType> Значение, указывающее тип выполняемого поиска, который должен выполняться.</span><span class="sxs-lookup"><span data-stu-id="df2c4-122">An <xref:System.Security.Cryptography.X509Certificates.X509FindType> value that specifies the type of search that is to be executed.</span></span> <span data-ttu-id="df2c4-123">Значение по умолчанию — «FindBySubjectDistinguishedName».</span><span class="sxs-lookup"><span data-stu-id="df2c4-123">The default is "FindBySubjectDistinguishedName".</span></span> <span data-ttu-id="df2c4-124">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="df2c4-124">Optional.</span></span>|  
|<span data-ttu-id="df2c4-125">findValue</span><span class="sxs-lookup"><span data-stu-id="df2c4-125">findValue</span></span>|<span data-ttu-id="df2c4-126">Значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="df2c4-126">The value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="df2c4-127">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="df2c4-127">Optional.</span></span>|  
|<span data-ttu-id="df2c4-128">isChainIncluded</span><span class="sxs-lookup"><span data-stu-id="df2c4-128">isChainIncluded</span></span>|<span data-ttu-id="df2c4-129">Указывает, нужно ли выполнять проверку с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="df2c4-129">Specifies whether validation should be performed by using the certificate chain.</span></span> <span data-ttu-id="df2c4-130">Значение по умолчанию равно «true»; Проверка выполняется с помощью цепочки сертификатов.</span><span class="sxs-lookup"><span data-stu-id="df2c4-130">The default is "true"; validation is performed by using the certificate chain.</span></span> <span data-ttu-id="df2c4-131">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="df2c4-131">Optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df2c4-132">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="df2c4-132">Child Elements</span></span>  
 <span data-ttu-id="df2c4-133">Нет</span><span class="sxs-lookup"><span data-stu-id="df2c4-133">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df2c4-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="df2c4-134">Parent Elements</span></span>  
  
|<span data-ttu-id="df2c4-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="df2c4-135">Element</span></span>|<span data-ttu-id="df2c4-136">Описание</span><span class="sxs-lookup"><span data-stu-id="df2c4-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="df2c4-137">\<serviceCertificate ></span><span class="sxs-lookup"><span data-stu-id="df2c4-137">\<serviceCertificate></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/servicecertificate.md)|<span data-ttu-id="df2c4-138">Настраивает сертификат, используемый для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="df2c4-138">Configures the certificate that is used to encrypt and decrypt tokens.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df2c4-139">Примечания</span><span class="sxs-lookup"><span data-stu-id="df2c4-139">Remarks</span></span>  
 <span data-ttu-id="df2c4-140">`<certificateReference>` Элемент определяет параметры, которые используются для поиска и проверки сертификатов X.509 в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="df2c4-140">The `<certificateReference>` element specifies settings that are used to find and validate an X.509 certificate in a certificate store.</span></span> <span data-ttu-id="df2c4-141">Когда он указан как дочерний элемент `<serviceCertificate>` , он указывает расположение и проверки параметров сертификата X.509, который используется для шифрования и расшифровки маркеров.</span><span class="sxs-lookup"><span data-stu-id="df2c4-141">When it is specified as the child element of the `<serviceCertificate>` element, it specifies the location and verification settings of the X.509 certificate that is used to encrypt and decrypt tokens.</span></span> <span data-ttu-id="df2c4-142">`<certificateReference>` Элемент, представленный объектом <xref:System.ServiceModel.Configuration.CertificateReferenceElement> класса.</span><span class="sxs-lookup"><span data-stu-id="df2c4-142">The `<certificateReference>` element is represented by the <xref:System.ServiceModel.Configuration.CertificateReferenceElement> class.</span></span>
