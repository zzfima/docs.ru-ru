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
ms.openlocfilehash: 0917569b556c31413b715d75c83a96f3a4b015d7
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2018
ms.locfileid: "50042731"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="b26f8-102">Практическое руководство. Предоставление доступа к сертификатам X.509 для WCF</span><span class="sxs-lookup"><span data-stu-id="b26f8-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="b26f8-103">Чтобы сделать сертификат X.509, доступной в Windows Communication Foundation (WCF), код приложения необходимо указать имя хранилища сертификатов и расположение.</span><span class="sxs-lookup"><span data-stu-id="b26f8-103">To make an X.509 certificate accessible to Windows Communication Foundation (WCF), application code must specify the certificate store name and location.</span></span> <span data-ttu-id="b26f8-104">В некоторых случаях идентификатор процесса должен иметь доступ к файлу, который содержит закрытый ключ, связанный с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="b26f8-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="b26f8-105">Чтобы получить закрытый ключ, связанный с сертификатом X.509 в хранилище сертификатов, WCF должно иметь разрешение на это.</span><span class="sxs-lookup"><span data-stu-id="b26f8-105">To obtain the private key associated with an X.509 certificate in a certificate store, WCF must have permission to do so.</span></span> <span data-ttu-id="b26f8-106">По умолчанию доступ к закрытому ключу сертификата имеют только владелец и системная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="b26f8-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="b26f8-107">Предоставление доступа к сертификатам X.509 для WCF</span><span class="sxs-lookup"><span data-stu-id="b26f8-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="b26f8-108">Предоставьте учетной записи, под какой WCF выполняется доступ на чтение к файлу, который содержит закрытый ключ, связанный с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="b26f8-108">Give the account under which WCF is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="b26f8-109">Определите, требуется ли WCF доступ на чтение к закрытому ключу для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="b26f8-109">Determine whether WCF requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="b26f8-110">В следующей таблице приводятся сведения о том, должен ли закрытый ключ быть доступным при использовании сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="b26f8-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="b26f8-111">Использование сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="b26f8-111">X.509 certificate use</span></span>|<span data-ttu-id="b26f8-112">Закрытый ключ</span><span class="sxs-lookup"><span data-stu-id="b26f8-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="b26f8-113">Цифровая подпись исходящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="b26f8-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="b26f8-114">Да</span><span class="sxs-lookup"><span data-stu-id="b26f8-114">Yes</span></span>|  
        |<span data-ttu-id="b26f8-115">Проверка подписи входящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="b26f8-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="b26f8-116">Нет</span><span class="sxs-lookup"><span data-stu-id="b26f8-116">No</span></span>|  
        |<span data-ttu-id="b26f8-117">Шифрование исходящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="b26f8-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="b26f8-118">Нет</span><span class="sxs-lookup"><span data-stu-id="b26f8-118">No</span></span>|  
        |<span data-ttu-id="b26f8-119">Расшифровка входящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="b26f8-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="b26f8-120">Да</span><span class="sxs-lookup"><span data-stu-id="b26f8-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="b26f8-121">Определите расположение и имя хранилища сертификатов, в котором хранится сертификат.</span><span class="sxs-lookup"><span data-stu-id="b26f8-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="b26f8-122">Хранилище сертификатов, в котором хранится сертификат, задается в коде приложения или конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b26f8-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="b26f8-123">Например, в следующем примере задано, что сертификат расположен в хранилище сертификатов `CurrentUser` с именем `My`.</span><span class="sxs-lookup"><span data-stu-id="b26f8-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="b26f8-124">Определить, где находится закрытый ключ для сертификата на компьютере с помощью [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) средство.</span><span class="sxs-lookup"><span data-stu-id="b26f8-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="b26f8-125">[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) для средства требуется имя хранилища сертификатов, расположение хранилища сертификатов и что-то, которое однозначно идентифицирует этот сертификат.</span><span class="sxs-lookup"><span data-stu-id="b26f8-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="b26f8-126">Средство принимает имя субъекта сертификата или его отпечаток в качестве уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="b26f8-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="b26f8-127">Дополнительные сведения о том, как определить отпечаток для сертификата см. в разделе [как: извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="b26f8-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="b26f8-128">В следующем примере кода используется [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) средство для определения расположения закрытого ключа для сертификата в `My` хранить в `CurrentUser` с отпечатком `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="b26f8-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="b26f8-129">Определите учетную запись, под которой работает WCF.</span><span class="sxs-lookup"><span data-stu-id="b26f8-129">Determine the account that WCF is running under.</span></span>  
  
         <span data-ttu-id="b26f8-130">В приведенной ниже таблице представлены учетной записи, под которой запущена WCF для данного сценария.</span><span class="sxs-lookup"><span data-stu-id="b26f8-130">The following table details the account under which WCF is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="b26f8-131">Сценарий</span><span class="sxs-lookup"><span data-stu-id="b26f8-131">Scenario</span></span>|<span data-ttu-id="b26f8-132">Идентификатор процесса</span><span class="sxs-lookup"><span data-stu-id="b26f8-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="b26f8-133">Клиент (консоль или приложение WinForms).</span><span class="sxs-lookup"><span data-stu-id="b26f8-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="b26f8-134">Текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="b26f8-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="b26f8-135">Служба, являющаяся резидентной.</span><span class="sxs-lookup"><span data-stu-id="b26f8-135">Service that is self-hosted.</span></span>|<span data-ttu-id="b26f8-136">Текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="b26f8-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="b26f8-137">Служба, размещенная в IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) или IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b26f8-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="b26f8-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="b26f8-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="b26f8-139">Служба, размещенная в IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="b26f8-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="b26f8-140">Управляется с помощью элемента `<processModel>` в файле Machine.config.</span><span class="sxs-lookup"><span data-stu-id="b26f8-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="b26f8-141">По умолчанию используется учетная запись ASPNET.</span><span class="sxs-lookup"><span data-stu-id="b26f8-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="b26f8-142">Предоставьте доступ на чтение к файлу, который содержит закрытый ключ для учетной записи, в которой WCF запущен, с помощью такого средства, как icacls.exe.</span><span class="sxs-lookup"><span data-stu-id="b26f8-142">Grant read access to the file that contains the private key to the account that WCF is running under, using a tool such as icacls.exe.</span></span>  
  
         <span data-ttu-id="b26f8-143">В следующем примере кода изменяет список управления доступом на уровне пользователей (DACL) для указанного файла, чтобы предоставить чтения учетной записи СЕТЕВОЙ службы (: R) доступ к файлу.</span><span class="sxs-lookup"><span data-stu-id="b26f8-143">The following code example edits the discretionary access control list (DACL) for the specified file to grant the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="b26f8-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b26f8-144">See Also</span></span>  
- [<span data-ttu-id="b26f8-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="b26f8-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)  
- [<span data-ttu-id="b26f8-146">Практическое руководство. Извлечение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="b26f8-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
- [<span data-ttu-id="b26f8-147">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="b26f8-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
