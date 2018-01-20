---
title: "&lt;certificate&gt; для &lt;peer&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48b69142-c957-4305-a042-c9d0c9a55c0e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1449bab5d585183d73da5ca0d2234857d9d92151
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="ltcertificategt-of-ltpeergt"></a><span data-ttu-id="bc374-102">&lt;certificate&gt; для &lt;peer&gt;</span><span class="sxs-lookup"><span data-stu-id="bc374-102">&lt;certificate&gt; of &lt;peer&gt;</span></span>
<span data-ttu-id="bc374-103">Задает сертификат, используемый одноранговым узлом.</span><span class="sxs-lookup"><span data-stu-id="bc374-103">Specifies a certificate used by a peer.</span></span>  
  
 <span data-ttu-id="bc374-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="bc374-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="bc374-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="bc374-105">\<behaviors></span></span>  
<span data-ttu-id="bc374-106">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="bc374-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="bc374-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="bc374-107">\<behavior></span></span>  
<span data-ttu-id="bc374-108">\<serviceCredentials></span><span class="sxs-lookup"><span data-stu-id="bc374-108">\<serviceCredentials></span></span>  
<span data-ttu-id="bc374-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="bc374-109">\<peer></span></span>  
<span data-ttu-id="bc374-110">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="bc374-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc374-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc374-111">Syntax</span></span>  
  
```xml  
<certificate findValue = "String"   
storeLocation = "CurrentUser/LocalMachine"  
storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc374-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bc374-112">Attributes and Elements</span></span>  
 <span data-ttu-id="bc374-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bc374-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc374-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bc374-114">Attributes</span></span>  
  
|<span data-ttu-id="bc374-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bc374-115">Attribute</span></span>|<span data-ttu-id="bc374-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bc374-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="bc374-117">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="bc374-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="bc374-118">Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="bc374-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="bc374-119">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="bc374-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="bc374-120">Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="bc374-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="bc374-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bc374-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bc374-122">-LocalMachine: хранилище сертификатов, назначенные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="bc374-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="bc374-123">-CurrentUser: хранилище сертификатов, назначенные текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="bc374-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="bc374-124">Значение по умолчанию - LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="bc374-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="bc374-125">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="bc374-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="bc374-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bc374-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bc374-127">-AddressBook: Хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="bc374-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="bc374-128">-AuthRoot: Хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="bc374-128">-   AuthRoot: Certificate store for third-party certificate authorities (CAs).</span></span><br /><span data-ttu-id="bc374-129">-CertificateAuthority: Хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="bc374-129">-   CertificateAuthority: Certificate store for intermediate certificate authorities (CAs).</span></span><br /><span data-ttu-id="bc374-130">-Disallowed: Хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bc374-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="bc374-131">-My: Хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bc374-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="bc374-132">-Root: Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="bc374-132">-   Root: Certificate store for trusted root certificate authorities (CAs).</span></span><br /><span data-ttu-id="bc374-133">-TrustedPeople: Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="bc374-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="bc374-134">-TrustedPublisher: Хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="bc374-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="bc374-135">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="bc374-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="bc374-136">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="bc374-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="bc374-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="bc374-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bc374-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="bc374-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="bc374-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="bc374-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="bc374-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="bc374-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="bc374-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="bc374-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="bc374-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="bc374-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="bc374-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="bc374-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="bc374-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="bc374-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="bc374-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="bc374-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="bc374-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="bc374-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="bc374-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="bc374-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="bc374-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="bc374-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="bc374-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="bc374-149">-   FindByExtension</span></span><br /><span data-ttu-id="bc374-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="bc374-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="bc374-151">-   FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="bc374-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="bc374-152">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="bc374-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="bc374-153">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="bc374-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc374-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bc374-154">Child Elements</span></span>  
 <span data-ttu-id="bc374-155">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bc374-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bc374-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bc374-156">Parent Elements</span></span>  
  
|<span data-ttu-id="bc374-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="bc374-157">Element</span></span>|<span data-ttu-id="bc374-158">Описание:</span><span class="sxs-lookup"><span data-stu-id="bc374-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bc374-159">\<peer></span><span class="sxs-lookup"><span data-stu-id="bc374-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-servicecredentials.md)|<span data-ttu-id="bc374-160">Задает текущие учетные данные для однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="bc374-160">Specifies the current credentials for a peer node.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc374-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="bc374-161">Remarks</span></span>  
 <span data-ttu-id="bc374-162">Этот элемент конфигурации содержит экземпляр `X509Certificate2`, используемый при проверке подлинности соседей в сетке узлов.</span><span class="sxs-lookup"><span data-stu-id="bc374-162">This configuration element contains an `X509Certificate2` instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="bc374-163">Дополнительные сведения о программировании одноранговая сеть см. в разделе [-одноранговые сети](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="bc374-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc374-164">См. также</span><span class="sxs-lookup"><span data-stu-id="bc374-164">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [<span data-ttu-id="bc374-165">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="bc374-165">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="bc374-166">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="bc374-166">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="bc374-167">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="bc374-167">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="bc374-168">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="bc374-168">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="bc374-169">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="bc374-169">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="bc374-170">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="bc374-170">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
