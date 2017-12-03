---
title: "Элемент &lt;certificate&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00f1b1f93836f3890a4c3f3797b583a15aeb599f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltcertificategt-element"></a><span data-ttu-id="68536-102">Элемент &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="68536-102">&lt;certificate&gt; Element</span></span>
<span data-ttu-id="68536-103">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="68536-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="68536-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="68536-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="68536-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="68536-105">\<behaviors></span></span>  
<span data-ttu-id="68536-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="68536-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="68536-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="68536-107">\<behavior></span></span>  
<span data-ttu-id="68536-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="68536-108">\<clientCredentials></span></span>  
<span data-ttu-id="68536-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="68536-109">\<peer></span></span>  
<span data-ttu-id="68536-110">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="68536-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68536-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68536-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68536-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="68536-112">Attributes and Elements</span></span>  
 <span data-ttu-id="68536-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="68536-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68536-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="68536-114">Attributes</span></span>  
  
|<span data-ttu-id="68536-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="68536-115">Attribute</span></span>|<span data-ttu-id="68536-116">Описание</span><span class="sxs-lookup"><span data-stu-id="68536-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="68536-117">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="68536-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="68536-118">Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="68536-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="68536-119">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="68536-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="68536-120">Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="68536-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="68536-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="68536-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="68536-122">-LocalMachine: хранилище сертификатов, назначенные на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="68536-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="68536-123">-CurrentUser: хранилище сертификатов, назначенные текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="68536-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="68536-124">Значение по умолчанию - LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="68536-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="68536-125">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="68536-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="68536-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="68536-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="68536-127">-AddressBook: Хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="68536-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="68536-128">-AuthRoot: Хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="68536-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="68536-129">-CertificateAuthority: Хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="68536-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="68536-130">-Disallowed: Хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68536-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="68536-131">-My: Хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="68536-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="68536-132">-Root: Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="68536-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="68536-133">-TrustedPeople: Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="68536-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="68536-134">-TrustedPublisher: Хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="68536-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="68536-135">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="68536-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="68536-136">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="68536-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="68536-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="68536-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="68536-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="68536-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="68536-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="68536-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="68536-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="68536-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="68536-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="68536-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="68536-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="68536-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="68536-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="68536-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="68536-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="68536-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="68536-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="68536-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="68536-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="68536-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="68536-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="68536-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="68536-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="68536-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="68536-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="68536-149">-   FindByExtension</span></span><br /><span data-ttu-id="68536-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="68536-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="68536-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="68536-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="68536-152">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="68536-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="68536-153">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="68536-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="68536-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="68536-154">Child Elements</span></span>  
 <span data-ttu-id="68536-155">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="68536-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="68536-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="68536-156">Parent Elements</span></span>  
  
|<span data-ttu-id="68536-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="68536-157">Element</span></span>|<span data-ttu-id="68536-158">Описание</span><span class="sxs-lookup"><span data-stu-id="68536-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="68536-159">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="68536-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="68536-160">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="68536-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68536-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="68536-161">Remarks</span></span>  
 <span data-ttu-id="68536-162">Этот элемент конфигурации содержит экземпляр X509Certificate2, используемый при проверке подлинности соседей в сетке узлов.</span><span class="sxs-lookup"><span data-stu-id="68536-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="68536-163">Дополнительные сведения о программировании одноранговая сеть см. в разделе [-одноранговые сети](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="68536-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68536-164">Пример</span><span class="sxs-lookup"><span data-stu-id="68536-164">Example</span></span>  
 <span data-ttu-id="68536-165">В следующем примере кода показывается, как найти сертификат, используемый в сценарии с одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="68536-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
```xml  
<behaviors>  
 <endpointBehaviors>  
  <behavior name="MyEndpointBehavior">  
   <clientCredentials>  
    <peer>  
     <certificate findValue="www.contoso.com"   
                   storeLocation="LocalMachine"  
                   x509FindType="FindByIssuerName" />  
    </peer>  
   </clientCredentials>  
  </behavior>  
</endpointBehaviors>  
```  
  
## <a name="see-also"></a><span data-ttu-id="68536-166">См. также</span><span class="sxs-lookup"><span data-stu-id="68536-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 [<span data-ttu-id="68536-167">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="68536-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="68536-168">Одноранговые сети</span><span class="sxs-lookup"><span data-stu-id="68536-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="68536-169">Проверка подлинности сообщения одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="68536-169">Peer Channel Message Authentication</span></span>](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="68536-170">Нестандартная проверка подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="68536-170">Peer Channel Custom Authentication</span></span>](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="68536-171">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="68536-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
