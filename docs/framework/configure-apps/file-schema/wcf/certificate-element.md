---
title: Элемент &lt;certificate&gt;
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 5329fb276766ca2bd24f0fd3aef793fbb3b1f8b8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515399"
---
# <a name="ltcertificategt-element"></a><span data-ttu-id="dab8a-102">Элемент &lt;certificate&gt;</span><span class="sxs-lookup"><span data-stu-id="dab8a-102">&lt;certificate&gt; Element</span></span>
<span data-ttu-id="dab8a-103">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="dab8a-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="dab8a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="dab8a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="dab8a-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="dab8a-105">\<behaviors></span></span>  
<span data-ttu-id="dab8a-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dab8a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="dab8a-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dab8a-107">\<behavior></span></span>  
<span data-ttu-id="dab8a-108">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="dab8a-108">\<clientCredentials></span></span>  
<span data-ttu-id="dab8a-109">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="dab8a-109">\<peer></span></span>  
<span data-ttu-id="dab8a-110">\<сертификат ></span><span class="sxs-lookup"><span data-stu-id="dab8a-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dab8a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dab8a-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"   
  
storeLocation="LocalMachine/CurrentUser"  
      storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"  
      X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dab8a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dab8a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dab8a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dab8a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dab8a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dab8a-114">Attributes</span></span>  
  
|<span data-ttu-id="dab8a-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dab8a-115">Attribute</span></span>|<span data-ttu-id="dab8a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dab8a-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="dab8a-117">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="dab8a-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="dab8a-118">Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="dab8a-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="dab8a-119">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="dab8a-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="dab8a-120">Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="dab8a-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="dab8a-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dab8a-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dab8a-122">-LocalMachine: хранилище сертификатов, назначенное локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="dab8a-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="dab8a-123">-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="dab8a-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="dab8a-124">Значение по умолчанию - LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="dab8a-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="dab8a-125">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="dab8a-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="dab8a-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dab8a-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dab8a-127">-AddressBook: Хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="dab8a-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="dab8a-128">-AuthRoot: Хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="dab8a-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="dab8a-129">-CertificateAuthority: Хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="dab8a-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="dab8a-130">-Disallowed: Хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="dab8a-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="dab8a-131">-My: Хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="dab8a-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="dab8a-132">-Root: Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="dab8a-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="dab8a-133">-TrustedPeople: Хранилище сертификатов для непосредственно доверенных лиц и ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dab8a-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="dab8a-134">-TrustedPublisher: Хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="dab8a-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="dab8a-135">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="dab8a-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="dab8a-136">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="dab8a-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="dab8a-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="dab8a-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="dab8a-138">-FindByThumbPrint</span><span class="sxs-lookup"><span data-stu-id="dab8a-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="dab8a-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="dab8a-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="dab8a-140">-FindBySubjectDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="dab8a-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="dab8a-141">-FindByIssuerName</span><span class="sxs-lookup"><span data-stu-id="dab8a-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="dab8a-142">-FindByIssuerDistinguishedName</span><span class="sxs-lookup"><span data-stu-id="dab8a-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="dab8a-143">-FindBySerialNumber</span><span class="sxs-lookup"><span data-stu-id="dab8a-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="dab8a-144">-FindByTimeValid</span><span class="sxs-lookup"><span data-stu-id="dab8a-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="dab8a-145">-FindByTimeNotYetValid</span><span class="sxs-lookup"><span data-stu-id="dab8a-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="dab8a-146">-FindByTemplateName</span><span class="sxs-lookup"><span data-stu-id="dab8a-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="dab8a-147">-FindByApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="dab8a-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="dab8a-148">-FindByCertificatePolicy</span><span class="sxs-lookup"><span data-stu-id="dab8a-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="dab8a-149">-FindByExtension</span><span class="sxs-lookup"><span data-stu-id="dab8a-149">-   FindByExtension</span></span><br /><span data-ttu-id="dab8a-150">-FindByKeyUsage</span><span class="sxs-lookup"><span data-stu-id="dab8a-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="dab8a-151">-FindBySubjectKeyIdentifier</span><span class="sxs-lookup"><span data-stu-id="dab8a-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="dab8a-152">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="dab8a-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="dab8a-153">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="dab8a-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dab8a-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dab8a-154">Child Elements</span></span>  
 <span data-ttu-id="dab8a-155">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dab8a-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dab8a-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dab8a-156">Parent Elements</span></span>  
  
|<span data-ttu-id="dab8a-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="dab8a-157">Element</span></span>|<span data-ttu-id="dab8a-158">Описание</span><span class="sxs-lookup"><span data-stu-id="dab8a-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dab8a-159">\<Одноранговый ></span><span class="sxs-lookup"><span data-stu-id="dab8a-159">\<peer></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|<span data-ttu-id="dab8a-160">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="dab8a-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dab8a-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="dab8a-161">Remarks</span></span>  
 <span data-ttu-id="dab8a-162">Этот элемент конфигурации содержит экземпляр X509Certificate2, используемый при проверке подлинности соседей в сетке узлов.</span><span class="sxs-lookup"><span data-stu-id="dab8a-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="dab8a-163">Дополнительные сведения о программировании peer-to-peer см. в разделе [сети Peer-to-Peer](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="dab8a-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dab8a-164">Пример</span><span class="sxs-lookup"><span data-stu-id="dab8a-164">Example</span></span>  
 <span data-ttu-id="dab8a-165">В следующем примере кода показывается, как найти сертификат, используемый в сценарии с одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="dab8a-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dab8a-166">См. также</span><span class="sxs-lookup"><span data-stu-id="dab8a-166">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>  
 <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>  
 <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>  
 [<span data-ttu-id="dab8a-167">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="dab8a-167">Working with Certificates</span></span>](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="dab8a-168">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="dab8a-168">Peer-to-Peer Networking</span></span>](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [<span data-ttu-id="dab8a-169">Проверка подлинности сообщений однорангового канала</span><span class="sxs-lookup"><span data-stu-id="dab8a-169">Peer Channel Message Authentication</span></span>](https://msdn.microsoft.com/library/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [<span data-ttu-id="dab8a-170">Нестандартной проверки подлинности одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="dab8a-170">Peer Channel Custom Authentication</span></span>](https://msdn.microsoft.com/library/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [<span data-ttu-id="dab8a-171">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="dab8a-171">Securing Peer Channel Applications</span></span>](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)
