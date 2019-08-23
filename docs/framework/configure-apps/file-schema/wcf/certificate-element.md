---
title: Элемент <certificate>
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: 0594f04ab17a9561e895efcc92e97c16e77c0a4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926196"
---
# <a name="certificate-element"></a><span data-ttu-id="0498a-102">\<Элемент > сертификата</span><span class="sxs-lookup"><span data-stu-id="0498a-102">\<certificate> Element</span></span>
<span data-ttu-id="0498a-103">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="0498a-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
 <span data-ttu-id="0498a-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0498a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0498a-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="0498a-105">\<behaviors></span></span>  
<span data-ttu-id="0498a-106">\<endpointBehaviors ></span><span class="sxs-lookup"><span data-stu-id="0498a-106">\<endpointBehaviors></span></span>  
<span data-ttu-id="0498a-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="0498a-107">\<behavior></span></span>  
<span data-ttu-id="0498a-108">\<> clientCredentials</span><span class="sxs-lookup"><span data-stu-id="0498a-108">\<clientCredentials></span></span>  
<span data-ttu-id="0498a-109">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="0498a-109">\<peer></span></span>  
<span data-ttu-id="0498a-110">\<> сертификата</span><span class="sxs-lookup"><span data-stu-id="0498a-110">\<certificate></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0498a-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0498a-111">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0498a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="0498a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="0498a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="0498a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0498a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="0498a-114">Attributes</span></span>  
  
|<span data-ttu-id="0498a-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="0498a-115">Attribute</span></span>|<span data-ttu-id="0498a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="0498a-116">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="0498a-117">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="0498a-117">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="0498a-118">Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="0498a-118">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="0498a-119">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="0498a-119">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="0498a-120">Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="0498a-120">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="0498a-121">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0498a-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0498a-122">-LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="0498a-122">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="0498a-123">-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="0498a-123">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="0498a-124">Значение по умолчанию - LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="0498a-124">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="0498a-125">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="0498a-125">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="0498a-126">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0498a-126">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0498a-127">AddressBook Хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="0498a-127">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="0498a-128">-Аусрут: Хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0498a-128">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="0498a-129">CertificateAuthority Хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0498a-129">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="0498a-130">Запрещено Хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0498a-130">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="0498a-131">Мне Хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0498a-131">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="0498a-132">Корневой Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="0498a-132">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="0498a-133">TrustedPeople Хранилище сертификатов для пользователей и ресурсов с прямым доверием.</span><span class="sxs-lookup"><span data-stu-id="0498a-133">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="0498a-134">-Трустедпублишер: Хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="0498a-134">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="0498a-135">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="0498a-135">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="0498a-136">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="0498a-136">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="0498a-137">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0498a-137">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0498a-138">-(FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="0498a-138">-   FindByThumbPrint</span></span><br /><span data-ttu-id="0498a-139">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="0498a-139">-   FindBySubjectName</span></span><br /><span data-ttu-id="0498a-140">-Финдбисубжектдистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="0498a-140">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="0498a-141">-Финдбиссуернаме</span><span class="sxs-lookup"><span data-stu-id="0498a-141">-   FindByIssuerName</span></span><br /><span data-ttu-id="0498a-142">-Финдбиссуердистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="0498a-142">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="0498a-143">-Финдбисериалнумбер</span><span class="sxs-lookup"><span data-stu-id="0498a-143">-   FindBySerialNumber</span></span><br /><span data-ttu-id="0498a-144">-Финдбитимевалид</span><span class="sxs-lookup"><span data-stu-id="0498a-144">-   FindByTimeValid</span></span><br /><span data-ttu-id="0498a-145">-Финдбитименотетвалид</span><span class="sxs-lookup"><span data-stu-id="0498a-145">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="0498a-146">-Финдбитемплатенаме</span><span class="sxs-lookup"><span data-stu-id="0498a-146">-   FindByTemplateName</span></span><br /><span data-ttu-id="0498a-147">-Финдбяппликатионполици</span><span class="sxs-lookup"><span data-stu-id="0498a-147">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="0498a-148">-Финдбицертификатеполици</span><span class="sxs-lookup"><span data-stu-id="0498a-148">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="0498a-149">-Финдбекстенсион</span><span class="sxs-lookup"><span data-stu-id="0498a-149">-   FindByExtension</span></span><br /><span data-ttu-id="0498a-150">-Финдбикэйусаже</span><span class="sxs-lookup"><span data-stu-id="0498a-150">-   FindByKeyUsage</span></span><br /><span data-ttu-id="0498a-151">-Финдбисубжекткэйидентифиер</span><span class="sxs-lookup"><span data-stu-id="0498a-151">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="0498a-152">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="0498a-152">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="0498a-153">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="0498a-153">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0498a-154">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="0498a-154">Child Elements</span></span>  
 <span data-ttu-id="0498a-155">Нет.</span><span class="sxs-lookup"><span data-stu-id="0498a-155">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0498a-156">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="0498a-156">Parent Elements</span></span>  
  
|<span data-ttu-id="0498a-157">Элемент</span><span class="sxs-lookup"><span data-stu-id="0498a-157">Element</span></span>|<span data-ttu-id="0498a-158">Описание</span><span class="sxs-lookup"><span data-stu-id="0498a-158">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0498a-159">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="0498a-159">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="0498a-160">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="0498a-160">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0498a-161">Примечания</span><span class="sxs-lookup"><span data-stu-id="0498a-161">Remarks</span></span>  
 <span data-ttu-id="0498a-162">Этот элемент конфигурации содержит экземпляр X509Certificate2, используемый при проверке подлинности соседей в сетке узлов.</span><span class="sxs-lookup"><span data-stu-id="0498a-162">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="0498a-163">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="0498a-163">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0498a-164">Пример</span><span class="sxs-lookup"><span data-stu-id="0498a-164">Example</span></span>  
 <span data-ttu-id="0498a-165">В следующем примере кода показывается, как найти сертификат, используемый в сценарии с одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="0498a-165">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
</behaviors>
```  
  
## <a name="see-also"></a><span data-ttu-id="0498a-166">См. также</span><span class="sxs-lookup"><span data-stu-id="0498a-166">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="0498a-167">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0498a-167">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="0498a-168">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="0498a-168">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="0498a-169">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0498a-169">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="0498a-170">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0498a-170">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="0498a-171">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="0498a-171">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
