---
title: Практическое руководство. Создание временных сертификатов для использования во время разработки
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 9e01ccb29ad017a2657ab08b54d7f01ef4564481
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964541"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="0648c-102">Практическое руководство. Создание временных сертификатов для использования во время разработки</span><span class="sxs-lookup"><span data-stu-id="0648c-102">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="0648c-103">При разработке защищенной службы или клиента с помощью Windows Communication Foundation (WCF) часто требуется предоставить сертификат X. 509, который будет использоваться в качестве учетных данных.</span><span class="sxs-lookup"><span data-stu-id="0648c-103">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="0648c-104">Обычно этот сертификат является частью цепи сертификатов, корневой центр которых находится в хранилище «Доверенные корневые центры сертификации» на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0648c-104">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="0648c-105">Наличие цепи сертификатов позволяет ограничить набор сертификатов, корневой центр которых, как правило, принадлежит организации или подразделению.</span><span class="sxs-lookup"><span data-stu-id="0648c-105">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="0648c-106">Для эмуляции этого во время разработки можно создать два сертификата, чтобы выполнить требования безопасности.</span><span class="sxs-lookup"><span data-stu-id="0648c-106">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="0648c-107">Первый сертификат является самозаверяющим и помещается в хранилище «Доверенные корневые центры сертификации». Второй сертификат создается из первого и помещается как в хранилище «Личное» на локальном компьютере, так и в хранилище «Личное» текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="0648c-107">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="0648c-108">В этом разделе описано, как создать эти два сертификата с помощью командлета PowerShell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) .</span><span class="sxs-lookup"><span data-stu-id="0648c-108">This topic walks through the steps to create these two certificates using the Powershell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0648c-109">Сертификаты, создаваемые командлетом New-SelfSignedCertificate, предоставляются только в целях тестирования.</span><span class="sxs-lookup"><span data-stu-id="0648c-109">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="0648c-110">При развертывании службы или клиента убедитесь, что используется соответствующий сертификат, предоставленный центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="0648c-110">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="0648c-111">Это может быть либо на сервере сертификатов Windows Server в Организации, либо в третьей стороне.</span><span class="sxs-lookup"><span data-stu-id="0648c-111">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="0648c-112">По умолчанию командлет [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) создает самозаверяющие сертификаты, и эти сертификаты являются небезопасными.</span><span class="sxs-lookup"><span data-stu-id="0648c-112">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="0648c-113">Размещение самозаверяющих сертификатов в хранилище доверенных корневых центров сертификации позволяет создать среду разработки, которая более точно имитирует среду развертывания.</span><span class="sxs-lookup"><span data-stu-id="0648c-113">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="0648c-114">Дополнительные сведения о создании и использовании сертификатов см. [в разделе Работа с сертификатами](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0648c-114">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="0648c-115">Дополнительные сведения об использовании сертификата в качестве учетных данных см. в разделе [Защита служб и клиентов](securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="0648c-115">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="0648c-116">Руководство по использованию технологии Microsoft Authenticode см. в разделе, посвященном [общим сведениям и учебникам по Authenticode](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span><span class="sxs-lookup"><span data-stu-id="0648c-116">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="0648c-117">Создание самозаверяющего сертификата корневого центра и экспорт закрытого ключа</span><span class="sxs-lookup"><span data-stu-id="0648c-117">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="0648c-118">Следующая команда создает самозаверяющий сертификат с именем субъекта "RootCA" в личном хранилище пользователя.</span><span class="sxs-lookup"><span data-stu-id="0648c-118">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
$rootcert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

<span data-ttu-id="0648c-119">Необходимо экспортировать сертификат в PFX-файл, чтобы его можно было импортировать в нужное место на более позднем этапе.</span><span class="sxs-lookup"><span data-stu-id="0648c-119">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="0648c-120">При экспорте сертификата с закрытым ключом требуется пароль для его защиты.</span><span class="sxs-lookup"><span data-stu-id="0648c-120">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="0648c-121">Пароль сохраняется в `SecureString` и с помощью командлета [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) Экспортируйте сертификат с соответствующим закрытым ключом в PFX-файл.</span><span class="sxs-lookup"><span data-stu-id="0648c-121">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="0648c-122">Мы также сохраняем только открытый сертификат в файле CRT с помощью командлета [Export-Certificate](/powershell/module/pkiclient/export-certificate) .</span><span class="sxs-lookup"><span data-stu-id="0648c-122">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
[System.Security.SecureString]$rootcertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootcert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootcertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="0648c-123">Создание нового сертификата, подписанного сертификатом корневого центра</span><span class="sxs-lookup"><span data-stu-id="0648c-123">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="0648c-124">Следующая команда создает сертификат, подписанный `RootCA` с именем субъекта "Сигнедбирутка" с помощью закрытого ключа издателя.</span><span class="sxs-lookup"><span data-stu-id="0648c-124">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="0648c-125">Аналогичным образом мы сохраняем подписанный сертификат с закрытым ключом в PFX-файл и только открытый ключ в CRT-файле.</span><span class="sxs-lookup"><span data-stu-id="0648c-125">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootcertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="0648c-126">Установка сертификата в хранилище «Доверенные корневые центры сертификации»</span><span class="sxs-lookup"><span data-stu-id="0648c-126">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="0648c-127">После создания самозаверяющего сертификата его можно установить в хранилище «Доверенные корневые центры сертификации».</span><span class="sxs-lookup"><span data-stu-id="0648c-127">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="0648c-128">Компьютер доверяет любым сертификатам, подписанным этим сертификатом в этой точке.</span><span class="sxs-lookup"><span data-stu-id="0648c-128">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="0648c-129">Поэтому удалите сертификат из хранилища, если он больше не требуется.</span><span class="sxs-lookup"><span data-stu-id="0648c-129">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="0648c-130">При удалении этого сертификата корневого центра все другие сертификаты, подписанные им, становятся неавторизованными.</span><span class="sxs-lookup"><span data-stu-id="0648c-130">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="0648c-131">Сертификаты корневого центра представляют собой лишь механизм, с помощью которого при необходимости можно ограничить группу сертификатов.</span><span class="sxs-lookup"><span data-stu-id="0648c-131">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="0648c-132">Например, в одноранговых приложениях обычно нет необходимости использовать корневой центр, поскольку идентификация отдельного элемента просто доверяется в предоставленном с ним сертификате.</span><span class="sxs-lookup"><span data-stu-id="0648c-132">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="0648c-133">Установка самозаверяющего сертификата в хранилище «Доверенные корневые центры сертификации»</span><span class="sxs-lookup"><span data-stu-id="0648c-133">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="0648c-134">Откройте оснастку сертификата.</span><span class="sxs-lookup"><span data-stu-id="0648c-134">Open the certificate snap-in.</span></span> <span data-ttu-id="0648c-135">(Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC](how-to-view-certificates-with-the-mmc-snap-in.md).)</span><span class="sxs-lookup"><span data-stu-id="0648c-135">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="0648c-136">Откройте папку, чтобы сохранить сертификат: **Локальный компьютер** либо **Текущий пользователь**.</span><span class="sxs-lookup"><span data-stu-id="0648c-136">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="0648c-137">Откройте папку **Доверенные корневые центры сертификации** .</span><span class="sxs-lookup"><span data-stu-id="0648c-137">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="0648c-138">Щелкните правой кнопкой мыши папку **Сертификаты** , выберите пункт **Все задачи**, а затем выберите **Импортировать**.</span><span class="sxs-lookup"><span data-stu-id="0648c-138">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="0648c-139">Следуйте инструкциям мастера на экране, чтобы импортировать файл RootCA. pfx в хранилище.</span><span class="sxs-lookup"><span data-stu-id="0648c-139">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="0648c-140">Использование сертификатов с WCF</span><span class="sxs-lookup"><span data-stu-id="0648c-140">Using certificates With WCF</span></span>

<span data-ttu-id="0648c-141">После настройки временных сертификатов их можно использовать для разработки решений WCF, задающих сертификаты как тип учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="0648c-141">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="0648c-142">Например, в следующей конфигурации XML в качестве типа учетных данных клиента задается безопасность сообщения и сертификат.</span><span class="sxs-lookup"><span data-stu-id="0648c-142">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="0648c-143">Задание сертификата как типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="0648c-143">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="0648c-144">В файле конфигурации для службы используйте следующий XML, чтобы настроить режим безопасности сообщения и задать тип учетных данных клиента для сертификата.</span><span class="sxs-lookup"><span data-stu-id="0648c-144">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

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

2. <span data-ttu-id="0648c-145">В файле конфигурации для клиента используйте следующий XML-код, чтобы указать, что сертификат найден в хранилище пользователя, и его можно найти, выполнив поиск по полю SubjectName в значении "CohoWinery".</span><span class="sxs-lookup"><span data-stu-id="0648c-145">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

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

<span data-ttu-id="0648c-146">Дополнительные сведения об использовании сертификатов в WCF см. в разделе [Working with Certificates](working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="0648c-146">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="0648c-147">безопасность платформы .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0648c-147">.NET Framework security</span></span>

<span data-ttu-id="0648c-148">Не забудьте удалить любые временные сертификаты корневого центра из папки **Доверенные корневые центры сертификации** и папки **Личное** , щелкнув правой кнопкой мыши сертификат и выбрав **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="0648c-148">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="0648c-149">См. также:</span><span class="sxs-lookup"><span data-stu-id="0648c-149">See also</span></span>

- [<span data-ttu-id="0648c-150">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="0648c-150">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="0648c-151">Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC</span><span class="sxs-lookup"><span data-stu-id="0648c-151">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="0648c-152">Securing Services and Clients</span><span class="sxs-lookup"><span data-stu-id="0648c-152">Securing Services and Clients</span></span>](securing-services-and-clients.md)
