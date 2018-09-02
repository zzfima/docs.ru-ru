---
title: Практическое руководство. Создание временных сертификатов для использования во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: d3b051c7ea152606721388ea35b6f508eada1c5d
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/01/2018
ms.locfileid: "43385181"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="24abf-102">Практическое руководство. Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="24abf-102">How to: Create Temporary Certificates for Use During Development</span></span>
<span data-ttu-id="24abf-103">При разработке безопасной службы или клиента с помощью Windows Communication Foundation (WCF), часто бывает необходимо предоставить сертификат X.509 для использования в качестве учетных данных.</span><span class="sxs-lookup"><span data-stu-id="24abf-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="24abf-104">Обычно этот сертификат является частью цепи сертификатов, корневой центр которых находится в хранилище «Доверенные корневые центры сертификации» на компьютере.</span><span class="sxs-lookup"><span data-stu-id="24abf-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="24abf-105">Наличие цепи сертификатов позволяет ограничить набор сертификатов, корневой центр которых, как правило, принадлежит организации или подразделению.</span><span class="sxs-lookup"><span data-stu-id="24abf-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="24abf-106">Для эмуляции этого во время разработки можно создать два сертификата, чтобы выполнить требования безопасности.</span><span class="sxs-lookup"><span data-stu-id="24abf-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="24abf-107">Первый сертификат является самозаверяющим и помещается в хранилище «Доверенные корневые центры сертификации». Второй сертификат создается из первого и помещается как в хранилище «Личное» на локальном компьютере, так и в хранилище «Личное» текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="24abf-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="24abf-108">Здесь описаны шаги по созданию этих двух сертификатов с помощью [средство создания сертификатов (MakeCert.exe)](https://go.microsoft.com/fwlink/?LinkId=248185), предоставляемого пакетом [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="24abf-108">This topic walks through the steps to create these two certificates using the [Certificate Creation Tool (MakeCert.exe)](https://go.microsoft.com/fwlink/?LinkId=248185), which is provided by the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] SDK.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24abf-109">Сертификаты, создаваемые средством для создания сертификатов, предоставляются только для проверки.</span><span class="sxs-lookup"><span data-stu-id="24abf-109">The certificates the Certification Creation tool generates are provided for testing purposes only.</span></span> <span data-ttu-id="24abf-110">При развертывании службы или клиента убедитесь, что используется соответствующий сертификат, предоставленный центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="24abf-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="24abf-111">Этот сертификат может предоставляться сервером сертификации [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] организации или третьей стороны.</span><span class="sxs-lookup"><span data-stu-id="24abf-111">This could either be from a [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] certificate server in your organization or a third party.</span></span>  
>   
>  <span data-ttu-id="24abf-112">По умолчанию [Makecert.exe (средство создания сертификатов)](https://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) создает сертификаты, корневой центр которых называется «корневое агентство **.»**</span><span class="sxs-lookup"><span data-stu-id="24abf-112">By default, the [Makecert.exe (Certificate Creation Tool)](https://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) creates certificates whose root authority is called "Root Agency **."**</span></span> <span data-ttu-id="24abf-113">Поскольку «Корневое агентство» не является хранилищем «Доверенные корневые центры сертификации», сертификаты не защищены.</span><span class="sxs-lookup"><span data-stu-id="24abf-113">Because the "Root Agency" is not in the Trusted Root Certification Authorities store, this makes these certificates insecure.</span></span> <span data-ttu-id="24abf-114">Создание самозаверяющего сертификата, помещенного в хранилище «Доверенные корневые центры сертификации», позволяет создать среду разработки, более точно моделирующую среду развертывания.</span><span class="sxs-lookup"><span data-stu-id="24abf-114">Creating a self-signed certificate that is placed in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>  
  
 <span data-ttu-id="24abf-115">Дополнительные сведения о создании и использовании сертификатов см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="24abf-115">For more information about creating and using certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="24abf-116">Дополнительные сведения об использовании сертификата в качестве учетных данных см. в разделе [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="24abf-116">For more information about using a certificate as a credential, see [Securing Services and Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="24abf-117">Руководство по использованию технологии Microsoft Authenticode см. в разделе [и учебникам по Authenticode](https://go.microsoft.com/fwlink/?LinkId=88919).</span><span class="sxs-lookup"><span data-stu-id="24abf-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://go.microsoft.com/fwlink/?LinkId=88919).</span></span>  
  
### <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="24abf-118">Создание самозаверяющего сертификата корневого центра и экспорт закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="24abf-118">To create a self-signed root authority certificate and export the private key</span></span>  
  
1.  <span data-ttu-id="24abf-119">Используйте средство MakeCert.exe со следующими коммутаторами.</span><span class="sxs-lookup"><span data-stu-id="24abf-119">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="24abf-120">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="24abf-120">`-n` `subjectName`.</span></span> <span data-ttu-id="24abf-121">Задает имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="24abf-121">Specifies the subject name.</span></span> <span data-ttu-id="24abf-122">Согласно правилам, к имени субъекта добавляется префикс "CN = " для "Common Name".</span><span class="sxs-lookup"><span data-stu-id="24abf-122">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    2.  <span data-ttu-id="24abf-123">`-r`.</span><span class="sxs-lookup"><span data-stu-id="24abf-123">`-r`.</span></span> <span data-ttu-id="24abf-124">Указывает, что сертификат самозаверяющий.</span><span class="sxs-lookup"><span data-stu-id="24abf-124">Specifies that the certificate will be self-signed.</span></span>  
  
    3.  <span data-ttu-id="24abf-125">`-sv` `privateKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="24abf-125">`-sv` `privateKeyFile`.</span></span> <span data-ttu-id="24abf-126">Указывает файл, содержащий контейнер закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="24abf-126">Specifies the file that contains the private key container.</span></span>  
  
     <span data-ttu-id="24abf-127">Например, следующая команда создает самозаверяющий сертификат с именем субъекта "CN=TempCA".</span><span class="sxs-lookup"><span data-stu-id="24abf-127">For example, the following command creates a self-signed certificate with a subject name of "CN=TempCA."</span></span>  
  
    ```  
    makecert -n "CN=TempCA" -r -sv TempCA.pvk TempCA.cer  
    ```  
  
     <span data-ttu-id="24abf-128">Будет предложено указать пароль для защиты закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="24abf-128">You will be prompted to provide a password to protect the private key.</span></span> <span data-ttu-id="24abf-129">Этот пароль необходим при создании сертификата, подписанного этим корневым сертификатом.</span><span class="sxs-lookup"><span data-stu-id="24abf-129">This password is required when creating a certificate signed by this root certificate.</span></span>  
  
### <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="24abf-130">Создание нового сертификата, подписанного сертификатом корневого центра</span><span class="sxs-lookup"><span data-stu-id="24abf-130">To create a new certificate signed by a root authority certificate</span></span>  
  
1.  <span data-ttu-id="24abf-131">Используйте средство MakeCert.exe со следующими коммутаторами.</span><span class="sxs-lookup"><span data-stu-id="24abf-131">Use the MakeCert.exe tool with the following switches:</span></span>  
  
    1.  <span data-ttu-id="24abf-132">`-sk` `subjectKey`.</span><span class="sxs-lookup"><span data-stu-id="24abf-132">`-sk` `subjectKey`.</span></span> <span data-ttu-id="24abf-133">Расположение контейнера ключей субъекта, содержащего закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="24abf-133">The location of the subject's key container that holds the private key.</span></span> <span data-ttu-id="24abf-134">Если контейнер ключей не существует, он будет создан.</span><span class="sxs-lookup"><span data-stu-id="24abf-134">If a key container does not exist, one is created.</span></span> <span data-ttu-id="24abf-135">Если ни один из параметров (-sk и sv) не используется, контейнер ключей с именем JoeSoft создается по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="24abf-135">If neither of the -sk or -sv options is used, a key container called JoeSoft is created by default.</span></span>  
  
    2.  <span data-ttu-id="24abf-136">`-n` `subjectName`.</span><span class="sxs-lookup"><span data-stu-id="24abf-136">`-n` `subjectName`.</span></span> <span data-ttu-id="24abf-137">Задает имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="24abf-137">Specifies the subject name.</span></span> <span data-ttu-id="24abf-138">Согласно правилам, к имени субъекта добавляется префикс "CN = " для "Common Name".</span><span class="sxs-lookup"><span data-stu-id="24abf-138">The convention is to prefix the subject name with "CN = " for "Common Name".</span></span>  
  
    3.  <span data-ttu-id="24abf-139">`-iv` `issuerKeyFile`.</span><span class="sxs-lookup"><span data-stu-id="24abf-139">`-iv` `issuerKeyFile`.</span></span> <span data-ttu-id="24abf-140">Задает файл закрытого ключа издателя.</span><span class="sxs-lookup"><span data-stu-id="24abf-140">Specifies the issuer's private key file.</span></span>  
  
    4.  <span data-ttu-id="24abf-141">`-ic` `issuerCertFile`.</span><span class="sxs-lookup"><span data-stu-id="24abf-141">`-ic` `issuerCertFile`.</span></span> <span data-ttu-id="24abf-142">Задает расположение сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="24abf-142">Specifies the location of the issuer's certificate.</span></span>  
  
     <span data-ttu-id="24abf-143">Например, следующая команда создает сертификат, подписанный сертификатом корневого центра `TempCA` , с именем субъекта `"CN=SignedByCA"` , используя закрытый ключ издателя.</span><span class="sxs-lookup"><span data-stu-id="24abf-143">For example, the following command creates a certificate signed by the `TempCA` root authority certificate with a subject name of `"CN=SignedByCA"` using the private key of the issuer.</span></span>  
  
    ```  
    makecert -sk SignedByCA -iv TempCA.pvk -n "CN=SignedByCA" -ic TempCA.cer SignedByCA.cer -sr currentuser -ss My  
    ```  
  
## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="24abf-144">Установка сертификата в хранилище «Доверенные корневые центры сертификации»</span><span class="sxs-lookup"><span data-stu-id="24abf-144">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>  
 <span data-ttu-id="24abf-145">После создания самозаверяющего сертификата его можно установить в хранилище «Доверенные корневые центры сертификации».</span><span class="sxs-lookup"><span data-stu-id="24abf-145">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="24abf-146">Компьютер доверяет любым сертификатам, подписанным этим сертификатом в этой точке.</span><span class="sxs-lookup"><span data-stu-id="24abf-146">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="24abf-147">Поэтому удалите сертификат из хранилища, если он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="24abf-147">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="24abf-148">При удалении этого сертификата корневого центра все другие сертификаты, подписанные им, становятся неавторизованными.</span><span class="sxs-lookup"><span data-stu-id="24abf-148">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="24abf-149">Сертификаты корневого центра представляют собой лишь механизм, с помощью которого при необходимости можно ограничить группу сертификатов.</span><span class="sxs-lookup"><span data-stu-id="24abf-149">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="24abf-150">Например, в одноранговых приложениях обычно нет необходимости использовать корневой центр, поскольку идентификация отдельного элемента просто доверяется в предоставленном с ним сертификате.</span><span class="sxs-lookup"><span data-stu-id="24abf-150">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>  
  
#### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="24abf-151">Установка самозаверяющего сертификата в хранилище «Доверенные корневые центры сертификации»</span><span class="sxs-lookup"><span data-stu-id="24abf-151">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>  
  
1.  <span data-ttu-id="24abf-152">Откройте оснастку сертификата.</span><span class="sxs-lookup"><span data-stu-id="24abf-152">Open the certificate snap-in.</span></span> <span data-ttu-id="24abf-153">(Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span><span class="sxs-lookup"><span data-stu-id="24abf-153">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2.  <span data-ttu-id="24abf-154">Откройте папку, чтобы сохранить сертификат: **Локальный компьютер** либо **Текущий пользователь**.</span><span class="sxs-lookup"><span data-stu-id="24abf-154">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>  
  
3.  <span data-ttu-id="24abf-155">Откройте папку **Доверенные корневые центры сертификации** .</span><span class="sxs-lookup"><span data-stu-id="24abf-155">Open the **Trusted Root Certification Authorities** folder.</span></span>  
  
4.  <span data-ttu-id="24abf-156">Щелкните правой кнопкой мыши папку **Сертификаты** , выберите пункт **Все задачи**, а затем выберите **Импортировать**.</span><span class="sxs-lookup"><span data-stu-id="24abf-156">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>  
  
5.  <span data-ttu-id="24abf-157">Следуйте инструкциям мастера на экране, чтобы импортировать TempCa.cer в хранилище.</span><span class="sxs-lookup"><span data-stu-id="24abf-157">Follow the on-screen wizard instructions to import the TempCa.cer into the store.</span></span>  
  
## <a name="using-certificates-with-wcf"></a><span data-ttu-id="24abf-158">Использование сертификатов с WCF</span><span class="sxs-lookup"><span data-stu-id="24abf-158">Using Certificates With WCF</span></span>  
 <span data-ttu-id="24abf-159">После настройки временных сертификатов их можно использовать для разработки решений WCF, задающих сертификаты как тип учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="24abf-159">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="24abf-160">Например, в следующей конфигурации XML в качестве типа учетных данных клиента задается безопасность сообщения и сертификат.</span><span class="sxs-lookup"><span data-stu-id="24abf-160">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>  
  
#### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="24abf-161">Задание сертификата как типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="24abf-161">To specify a certificate as the client credential type</span></span>  
  
-   <span data-ttu-id="24abf-162">В файле конфигурации для службы используйте следующий XML, чтобы настроить режим безопасности сообщения и задать тип учетных данных клиента для сертификата.</span><span class="sxs-lookup"><span data-stu-id="24abf-162">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>  
  
    ```xml  
    <bindings>       
      <wsHttpBinding>  
        <binding name="CertificateForClient">  
          <security>  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    ```  
  
 <span data-ttu-id="24abf-163">В файле конфигурации для клиента используйте следующий XML, чтобы указать, что сертификат найден в хранилище и можно найти путем поиска в поле SubjectName для значения «CohoWinery».</span><span class="sxs-lookup"><span data-stu-id="24abf-163">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>  
  
```xml  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="CertForClient">  
      <clientCredentials>  
        <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />  
       </clientCredentials>  
     </behavior>  
   </endpointBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="24abf-164">Дополнительные сведения об использовании сертификатов в WCF см. в разделе [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="24abf-164">For more information about using certificates in WCF, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="24abf-165">Безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="24abf-165">.NET Framework Security</span></span>  
 <span data-ttu-id="24abf-166">Не забудьте удалить любые временные сертификаты корневого центра из папки **Доверенные корневые центры сертификации** и папки **Личное** , щелкнув правой кнопкой мыши сертификат и выбрав **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="24abf-166">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24abf-167">См. также</span><span class="sxs-lookup"><span data-stu-id="24abf-167">See Also</span></span>  
 [<span data-ttu-id="24abf-168">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="24abf-168">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="24abf-169">Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC</span><span class="sxs-lookup"><span data-stu-id="24abf-169">How to: View Certificates with the MMC Snap-in</span></span>](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)  
 [<span data-ttu-id="24abf-170">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="24abf-170">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
