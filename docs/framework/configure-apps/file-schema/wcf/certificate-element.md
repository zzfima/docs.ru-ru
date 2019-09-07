---
title: Элемент <certificate>
ms.date: 03/30/2017
ms.assetid: 9b3d9233-ef35-477a-bf5d-efd1e80a52f4
ms.openlocfilehash: e28e7d16073a56f3b6126439644bfff86c9af18b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400558"
---
# <a name="certificate-element"></a><span data-ttu-id="f4632-102">\<Элемент > сертификата</span><span class="sxs-lookup"><span data-stu-id="f4632-102">\<certificate> Element</span></span>
<span data-ttu-id="f4632-103">Задает сертификат X.509, используемый для подписи и шифрования сообщений для клиентов одноранговых сетей.</span><span class="sxs-lookup"><span data-stu-id="f4632-103">Specifies an X.509 certificate to use for signing and encrypting messages for peer-to-peer clients.</span></span>  
  
<span data-ttu-id="f4632-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="f4632-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="f4632-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="f4632-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)</span></span>\
<span data-ttu-id="f4632-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-endpointbehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)</span></span>\
<span data-ttu-id="f4632-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> clientCredentials**](clientcredentials.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)</span></span>\
<span data-ttu-id="f4632-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Одноранговые >** ](peer-of-clientcredentials-element.md)</span><span class="sxs-lookup"><span data-stu-id="f4632-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)</span></span>\
<span data-ttu-id="f4632-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> сертификата**</span><span class="sxs-lookup"><span data-stu-id="f4632-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4632-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f4632-112">Syntax</span></span>  
  
```xml  
<certificate findValue="String"
             storeLocation="LocalMachine/CurrentUser"
             storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"
             X509FindType="FindByThumbPrint/FindBySubjectName/FindBySubjectDistinguishedName/FindByIssuerName/FindByIssuerDistinguishedName/FindBySerialNumber/FindByTimeValid/FindByTimeNotYetValid/FindByTemplateName/FindByApplicationPolicy/FindByCertificatePolicy/FindByExtension/FindByKeyUsage/FindBySubjectKeyIdentifier" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f4632-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f4632-113">Attributes and Elements</span></span>  
 <span data-ttu-id="f4632-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f4632-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f4632-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f4632-115">Attributes</span></span>  
  
|<span data-ttu-id="f4632-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f4632-116">Attribute</span></span>|<span data-ttu-id="f4632-117">Описание</span><span class="sxs-lookup"><span data-stu-id="f4632-117">Description</span></span>|  
|---------------|-----------------|  
|`findValue`|<span data-ttu-id="f4632-118">Строка, содержащая значение для поиска в хранилище сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="f4632-118">A string that contains the value to search for in the X.509 certificate store.</span></span> <span data-ttu-id="f4632-119">Тип, указанный в этом атрибуте, должен отвечать требованиям заданного значения `x509FindType`.</span><span class="sxs-lookup"><span data-stu-id="f4632-119">The type contained in the attribute must satisfy the requirements of the specified `x509FindType`.</span></span> <span data-ttu-id="f4632-120">Значение по умолчанию — пустая строка.</span><span class="sxs-lookup"><span data-stu-id="f4632-120">The default is an empty string.</span></span>|  
|`storeLocation`|<span data-ttu-id="f4632-121">Задает расположение хранилища сертификатов Х.509, которое клиент может использовать для проверки сертификата однорангового узла.</span><span class="sxs-lookup"><span data-stu-id="f4632-121">Specifies the location of the X.509 certificate store that the client uses to validate the peer's certificate against.</span></span> <span data-ttu-id="f4632-122">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f4632-122">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f4632-123">-LocalMachine — хранилище сертификатов, назначенное локальному компьютеру.</span><span class="sxs-lookup"><span data-stu-id="f4632-123">-   LocalMachine: the certificate store assigned to the local machine.</span></span><br /><span data-ttu-id="f4632-124">-CurrentUser: хранилище сертификатов, назначенное текущему пользователю.</span><span class="sxs-lookup"><span data-stu-id="f4632-124">-   CurrentUser: the certificate store assigned to the current user.</span></span><br /><br /> <span data-ttu-id="f4632-125">Значение по умолчанию - LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="f4632-125">The default is LocalMachine.</span></span>|  
|`storeName`|<span data-ttu-id="f4632-126">Задает имя открываемого хранилища сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="f4632-126">Specifies the name of the X.509 certificate store to open.</span></span> <span data-ttu-id="f4632-127">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f4632-127">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f4632-128">AddressBook Хранилище сертификатов для других пользователей.</span><span class="sxs-lookup"><span data-stu-id="f4632-128">-   AddressBook: Certificate store for other users.</span></span><br /><span data-ttu-id="f4632-129">-Аусрут: Хранилище сертификатов для сторонних центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="f4632-129">-   AuthRoot: Certificate store for third-party certification authorities (CAs).</span></span><br /><span data-ttu-id="f4632-130">CertificateAuthority Хранилище сертификатов для промежуточных центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="f4632-130">-   CertificateAuthority: Certificate store for intermediate certification authorities (CAs).</span></span><br /><span data-ttu-id="f4632-131">Запрещено Хранилище сертификатов для отозванных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f4632-131">-   Disallowed: Certificate store for revoked certificates.</span></span><br /><span data-ttu-id="f4632-132">Мне Хранилище сертификатов для личных сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f4632-132">-   My: Certificate store for personal certificates.</span></span><br /><span data-ttu-id="f4632-133">Корневой Хранилище сертификатов для доверенных корневых центров сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="f4632-133">-   Root: Certificate store for trusted root certification authorities (CAs).</span></span><br /><span data-ttu-id="f4632-134">TrustedPeople Хранилище сертификатов для пользователей и ресурсов с прямым доверием.</span><span class="sxs-lookup"><span data-stu-id="f4632-134">-   TrustedPeople: Certificate store for directly-trusted people and resources.</span></span><br /><span data-ttu-id="f4632-135">-Трустедпублишер: Хранилище сертификатов для непосредственно доверенных издателей.</span><span class="sxs-lookup"><span data-stu-id="f4632-135">-   TrustedPublisher: Certificate store for directly-trusted publishers.</span></span><br /><br /> <span data-ttu-id="f4632-136">Значение по умолчанию - My.</span><span class="sxs-lookup"><span data-stu-id="f4632-136">The default is My.</span></span>|  
|`X509FindType`|<span data-ttu-id="f4632-137">Определяет тип поиска сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="f4632-137">Defines the type of X.509 search to be executed.</span></span> <span data-ttu-id="f4632-138">Допустимы следующие значения:</span><span class="sxs-lookup"><span data-stu-id="f4632-138">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="f4632-139">-(FindByThumbprint</span><span class="sxs-lookup"><span data-stu-id="f4632-139">-   FindByThumbPrint</span></span><br /><span data-ttu-id="f4632-140">-FindBySubjectName</span><span class="sxs-lookup"><span data-stu-id="f4632-140">-   FindBySubjectName</span></span><br /><span data-ttu-id="f4632-141">-Финдбисубжектдистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="f4632-141">-   FindBySubjectDistinguishedName</span></span><br /><span data-ttu-id="f4632-142">-Финдбиссуернаме</span><span class="sxs-lookup"><span data-stu-id="f4632-142">-   FindByIssuerName</span></span><br /><span data-ttu-id="f4632-143">-Финдбиссуердистингуишеднаме</span><span class="sxs-lookup"><span data-stu-id="f4632-143">-   FindByIssuerDistinguishedName</span></span><br /><span data-ttu-id="f4632-144">-Финдбисериалнумбер</span><span class="sxs-lookup"><span data-stu-id="f4632-144">-   FindBySerialNumber</span></span><br /><span data-ttu-id="f4632-145">-Финдбитимевалид</span><span class="sxs-lookup"><span data-stu-id="f4632-145">-   FindByTimeValid</span></span><br /><span data-ttu-id="f4632-146">-Финдбитименотетвалид</span><span class="sxs-lookup"><span data-stu-id="f4632-146">-   FindByTimeNotYetValid</span></span><br /><span data-ttu-id="f4632-147">-Финдбитемплатенаме</span><span class="sxs-lookup"><span data-stu-id="f4632-147">-   FindByTemplateName</span></span><br /><span data-ttu-id="f4632-148">-Финдбяппликатионполици</span><span class="sxs-lookup"><span data-stu-id="f4632-148">-   FindByApplicationPolicy</span></span><br /><span data-ttu-id="f4632-149">-Финдбицертификатеполици</span><span class="sxs-lookup"><span data-stu-id="f4632-149">-   FindByCertificatePolicy</span></span><br /><span data-ttu-id="f4632-150">-Финдбекстенсион</span><span class="sxs-lookup"><span data-stu-id="f4632-150">-   FindByExtension</span></span><br /><span data-ttu-id="f4632-151">-Финдбикэйусаже</span><span class="sxs-lookup"><span data-stu-id="f4632-151">-   FindByKeyUsage</span></span><br /><span data-ttu-id="f4632-152">-Финдбисубжекткэйидентифиер</span><span class="sxs-lookup"><span data-stu-id="f4632-152">-   FindBySubjectKeyIdentifier</span></span><br /><br /> <span data-ttu-id="f4632-153">Тип, указанный в атрибуте `findValue`, должен отвечать требованиям заданного значения `X509FindType`.</span><span class="sxs-lookup"><span data-stu-id="f4632-153">The type contained in the `findValue` attribute must satisfy the requirements of the specified `X509FindType`.</span></span><br /><br /> <span data-ttu-id="f4632-154">Значение по умолчанию - FindBySubjectDistinguishedName.</span><span class="sxs-lookup"><span data-stu-id="f4632-154">The default value is FindBySubjectDistinguishedName.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f4632-155">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f4632-155">Child Elements</span></span>  
 <span data-ttu-id="f4632-156">Нет.</span><span class="sxs-lookup"><span data-stu-id="f4632-156">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f4632-157">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f4632-157">Parent Elements</span></span>  
  
|<span data-ttu-id="f4632-158">Элемент</span><span class="sxs-lookup"><span data-stu-id="f4632-158">Element</span></span>|<span data-ttu-id="f4632-159">Описание</span><span class="sxs-lookup"><span data-stu-id="f4632-159">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f4632-160">\<Одноранговые ></span><span class="sxs-lookup"><span data-stu-id="f4632-160">\<peer></span></span>](peer-of-clientcredentials-element.md)|<span data-ttu-id="f4632-161">Задает учетные данные, используемые при проверке подлинности одноранговых клиентов.</span><span class="sxs-lookup"><span data-stu-id="f4632-161">Specifies credentials used when authenticating peer-to-peer clients.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4632-162">Примечания</span><span class="sxs-lookup"><span data-stu-id="f4632-162">Remarks</span></span>  
 <span data-ttu-id="f4632-163">Этот элемент конфигурации содержит экземпляр X509Certificate2, используемый при проверке подлинности соседей в сетке узлов.</span><span class="sxs-lookup"><span data-stu-id="f4632-163">This configuration element contains a X509Certificate2 instance used when authenticating neighbors in the peer mesh.</span></span>  
  
 <span data-ttu-id="f4632-164">Дополнительные сведения о одноранговых программах см. в разделе одноранговая [сеть](../../../wcf/feature-details/peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="f4632-164">For more information about peer-to-peer programming, see [Peer-to-Peer Networking](../../../wcf/feature-details/peer-to-peer-networking.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4632-165">Пример</span><span class="sxs-lookup"><span data-stu-id="f4632-165">Example</span></span>  
 <span data-ttu-id="f4632-166">В следующем примере кода показывается, как найти сертификат, используемый в сценарии с одноранговой сетью.</span><span class="sxs-lookup"><span data-stu-id="f4632-166">The following code specifies how to find the certificate used in a peer-to-peer scenario.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f4632-167">См. также</span><span class="sxs-lookup"><span data-stu-id="f4632-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerCredentialElement>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.Certificate%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateElement>
- <xref:System.ServiceModel.Security.PeerCredential.Certificate%2A>
- [<span data-ttu-id="f4632-168">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="f4632-168">Working with Certificates</span></span>](../../../wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="f4632-169">Одноранговая сеть</span><span class="sxs-lookup"><span data-stu-id="f4632-169">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
- <span data-ttu-id="f4632-170">[Проверка подлинности сообщений однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f4632-170">[Peer Channel Message Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))</span></span>
- <span data-ttu-id="f4632-171">[Пользовательская проверка подлинности однорангового канала](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f4632-171">[Peer Channel Custom Authentication](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))</span></span>
- [<span data-ttu-id="f4632-172">Защита приложений одноранговых каналов</span><span class="sxs-lookup"><span data-stu-id="f4632-172">Securing Peer Channel Applications</span></span>](../../../wcf/feature-details/securing-peer-channel-applications.md)
