---
title: Практическое руководство. Предоставление доступа к сертификатам X.509 для WCF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
ms.openlocfilehash: 71dbf395f43c8028a703a342c032f2b8d022a61c
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "76921292"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="d0718-102">Практическое руководство. Предоставление доступа к сертификатам X.509 для WCF</span><span class="sxs-lookup"><span data-stu-id="d0718-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="d0718-103">Чтобы сделать сертификат X. 509 доступным для Windows Communication Foundation (WCF), код приложения должен указать имя и расположение хранилища сертификатов.</span><span class="sxs-lookup"><span data-stu-id="d0718-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="d0718-104">В некоторых случаях идентификатор процесса должен иметь доступ к файлу, который содержит закрытый ключ, связанный с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="d0718-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="d0718-105">Чтобы получить закрытый ключ, связанный с сертификатом X. 509 в хранилище сертификатов, WCF должен иметь разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="d0718-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="d0718-106">По умолчанию доступ к закрытому ключу сертификата имеют только владелец и системная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="d0718-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="d0718-107">Предоставление доступа к сертификатам X.509 для WCF</span><span class="sxs-lookup"><span data-stu-id="d0718-107">To make X.509 certificates accessible to WCF</span></span>  
  
1. <span data-ttu-id="d0718-108">Предоставьте учетной записи, под которой выполняется служба WCF, доступ на чтение к файлу, содержащему закрытый ключ, связанный с сертификатом X. 509.</span><span class="sxs-lookup"><span data-stu-id="d0718-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1. <span data-ttu-id="d0718-109">Определите, требует ли WCF доступ на чтение закрытого ключа для сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="d0718-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="d0718-110">В следующей таблице приводятся сведения о том, должен ли закрытый ключ быть доступным при использовании сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="d0718-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="d0718-111">Использование сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="d0718-111">X.509 certificate use</span></span>|<span data-ttu-id="d0718-112">Закрытый ключ</span><span class="sxs-lookup"><span data-stu-id="d0718-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="d0718-113">Цифровая подпись исходящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="d0718-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="d0718-114">Да</span><span class="sxs-lookup"><span data-stu-id="d0718-114">Yes</span></span>|  
        |<span data-ttu-id="d0718-115">Проверка подписи входящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="d0718-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="d0718-116">Нет</span><span class="sxs-lookup"><span data-stu-id="d0718-116">No</span></span>|  
        |<span data-ttu-id="d0718-117">Шифрование исходящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="d0718-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="d0718-118">Нет</span><span class="sxs-lookup"><span data-stu-id="d0718-118">No</span></span>|  
        |<span data-ttu-id="d0718-119">Расшифровка входящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="d0718-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="d0718-120">Да</span><span class="sxs-lookup"><span data-stu-id="d0718-120">Yes</span></span>|  
  
    2. <span data-ttu-id="d0718-121">Определите расположение и имя хранилища сертификатов, в котором хранится сертификат.</span><span class="sxs-lookup"><span data-stu-id="d0718-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="d0718-122">Хранилище сертификатов, в котором хранится сертификат, задается в коде приложения или конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d0718-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="d0718-123">Например, в следующем примере задано, что сертификат расположен в хранилище сертификатов `CurrentUser` с именем `My`.</span><span class="sxs-lookup"><span data-stu-id="d0718-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. <span data-ttu-id="d0718-124">Определите, где закрытый ключ сертификата находится на компьютере с помощью средства [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) .</span><span class="sxs-lookup"><span data-stu-id="d0718-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="d0718-125">Для средства [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) требуется имя хранилища сертификатов, расположение хранилища сертификатов и что-то, уникально идентифицирующее сертификат.</span><span class="sxs-lookup"><span data-stu-id="d0718-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="d0718-126">Средство принимает имя субъекта сертификата или его отпечаток в качестве уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="d0718-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="d0718-127">Дополнительные сведения о том, как определить отпечаток для сертификата, см. в разделе [как получить отпечаток сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="d0718-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="d0718-128">В следующем примере кода используется средство [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) для определения расположения закрытого ключа для сертификата в хранилище `My` в `CurrentUser` с отпечатком `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="d0718-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. <span data-ttu-id="d0718-129">Определите учетную запись, под которой выполняется WCF.</span><span class="sxs-lookup"><span data-stu-id="d0718-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="d0718-130">В следующей таблице подробно описана учетная запись, под которой выполняется WCF для данного сценария.</span><span class="sxs-lookup"><span data-stu-id="d0718-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="d0718-131">Сценарий</span><span class="sxs-lookup"><span data-stu-id="d0718-131">Scenario</span></span>|<span data-ttu-id="d0718-132">Идентификатор процесса</span><span class="sxs-lookup"><span data-stu-id="d0718-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="d0718-133">Клиент (консоль или приложение WinForms).</span><span class="sxs-lookup"><span data-stu-id="d0718-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="d0718-134">Текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="d0718-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="d0718-135">Служба, являющаяся резидентной.</span><span class="sxs-lookup"><span data-stu-id="d0718-135">Service that is self-hosted.</span></span>|<span data-ttu-id="d0718-136">Текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="d0718-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="d0718-137">Служба, размещенная в IIS 6,0 (Windows Server 2003) или IIS 7,0 (Windows Vista).</span><span class="sxs-lookup"><span data-stu-id="d0718-137">Service that is hosted in IIS 6.0 (Windows Server 2003) or IIS 7.0 (Windows Vista).</span></span>|<span data-ttu-id="d0718-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="d0718-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="d0718-139">Служба, размещенная в IIS 5. X (Windows XP).</span><span class="sxs-lookup"><span data-stu-id="d0718-139">Service that is hosted in IIS 5.X (Windows XP).</span></span>|<span data-ttu-id="d0718-140">Управляется с помощью элемента `<processModel>` в файле Machine.config.</span><span class="sxs-lookup"><span data-stu-id="d0718-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="d0718-141">По умолчанию используется учетная запись ASPNET.</span><span class="sxs-lookup"><span data-stu-id="d0718-141">The default account is ASPNET.</span></span>|  
  
    5. <span data-ttu-id="d0718-142">Предоставьте доступ на чтение к файлу, содержащему закрытый ключ, для учетной записи, от имени которой выполняется WCF, используя такой инструмент, как icacls. exe.</span><span class="sxs-lookup"><span data-stu-id="d0718-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="d0718-143">В следующем примере кода изменяется список управления доступом на уровне пользователей (DACL) для указанного файла, чтобы предоставить учетной записи сетевой службы доступ на чтение (: R) к файлу.</span><span class="sxs-lookup"><span data-stu-id="d0718-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```console 
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="d0718-144">См. также:</span><span class="sxs-lookup"><span data-stu-id="d0718-144">See also</span></span>

- [<span data-ttu-id="d0718-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="d0718-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [<span data-ttu-id="d0718-146">Практическое руководство. Извлечение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="d0718-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [<span data-ttu-id="d0718-147">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="d0718-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
