---
title: Практическое руководство. Предоставление доступа к сертификатам X.509 для WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- X.509 certificates [WCF]
- certificates [WCF], making X.509 certificates accessible to WCF
- X.509 certificates [WCF], making accessible to WCF
ms.assetid: a54e407c-c2b5-4319-a648-60e43413664b
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 77ee21074b6f1bb5a2f5bd4ee653100d3534075d
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="ce044-102">Практическое руководство. Предоставление доступа к сертификатам X.509 для WCF</span><span class="sxs-lookup"><span data-stu-id="ce044-102">How to: Make X.509 Certificates Accessible to WCF</span></span>
<span data-ttu-id="ce044-103">Чтобы сделать сертификат X.509 доступным для [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в коде приложения необходимо указать имя хранилища сертификатов и его расположение.</span><span class="sxs-lookup"><span data-stu-id="ce044-103">To make an X.509 certificate accessible to [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], application code must specify the certificate store name and location.</span></span> <span data-ttu-id="ce044-104">В некоторых случаях идентификатор процесса должен иметь доступ к файлу, который содержит закрытый ключ, связанный с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="ce044-104">In certain circumstances, the process identity must have access to the file that contains the private key associated with the X.509 certificate.</span></span> <span data-ttu-id="ce044-105">Чтобы получить закрытый ключ, связанный с сертификатом X.509 в хранилище сертификатов, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] должен иметь соответствующее разрешение.</span><span class="sxs-lookup"><span data-stu-id="ce044-105">To obtain the private key associated with an X.509 certificate in a certificate store, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must have permission to do so.</span></span> <span data-ttu-id="ce044-106">По умолчанию доступ к закрытому ключу сертификата имеют только владелец и системная учетная запись.</span><span class="sxs-lookup"><span data-stu-id="ce044-106">By default, only the owner and the System account can access the private key of a certificate.</span></span>  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a><span data-ttu-id="ce044-107">Предоставление доступа к сертификатам X.509 для WCF</span><span class="sxs-lookup"><span data-stu-id="ce044-107">To make X.509 certificates accessible to WCF</span></span>  
  
1.  <span data-ttu-id="ce044-108">Предоставьте учетной записи, от имени которой выполняется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], доступ для чтения к файлу, содержащему закрытый ключ, который связан с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="ce044-108">Give the account under which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running read access to the file that contains the private key associated with the X.509 certificate.</span></span>  
  
    1.  <span data-ttu-id="ce044-109">Определите, требуется ли для [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] доступ для чтения к закрытому ключу для сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="ce044-109">Determine whether [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires read access to the private key for the X.509 certificate.</span></span>  
  
         <span data-ttu-id="ce044-110">В следующей таблице приводятся сведения о том, должен ли закрытый ключ быть доступным при использовании сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="ce044-110">The following table details whether a private key must be available when using an X.509 certificate.</span></span>  
  
        |<span data-ttu-id="ce044-111">Использование сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="ce044-111">X.509 certificate use</span></span>|<span data-ttu-id="ce044-112">Закрытый ключ</span><span class="sxs-lookup"><span data-stu-id="ce044-112">Private key</span></span>|  
        |---------------------------|-----------------|  
        |<span data-ttu-id="ce044-113">Цифровая подпись исходящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ce044-113">Digitally signing an outbound SOAP message.</span></span>|<span data-ttu-id="ce044-114">Да</span><span class="sxs-lookup"><span data-stu-id="ce044-114">Yes</span></span>|  
        |<span data-ttu-id="ce044-115">Проверка подписи входящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ce044-115">Verifying the signature of an inbound SOAP message.</span></span>|<span data-ttu-id="ce044-116">Нет</span><span class="sxs-lookup"><span data-stu-id="ce044-116">No</span></span>|  
        |<span data-ttu-id="ce044-117">Шифрование исходящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ce044-117">Encrypting an outbound SOAP message.</span></span>|<span data-ttu-id="ce044-118">Нет</span><span class="sxs-lookup"><span data-stu-id="ce044-118">No</span></span>|  
        |<span data-ttu-id="ce044-119">Расшифровка входящего сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ce044-119">Decrypting an inbound SOAP message.</span></span>|<span data-ttu-id="ce044-120">Да</span><span class="sxs-lookup"><span data-stu-id="ce044-120">Yes</span></span>|  
  
    2.  <span data-ttu-id="ce044-121">Определите расположение и имя хранилища сертификатов, в котором хранится сертификат.</span><span class="sxs-lookup"><span data-stu-id="ce044-121">Determine the certificate store location and name in which the certificate is stored.</span></span>  
  
         <span data-ttu-id="ce044-122">Хранилище сертификатов, в котором хранится сертификат, задается в коде приложения или конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ce044-122">The certificate store in which the certificate is stored is specified either in application code or in configuration.</span></span> <span data-ttu-id="ce044-123">Например, в следующем примере задано, что сертификат расположен в хранилище сертификатов `CurrentUser` с именем `My`.</span><span class="sxs-lookup"><span data-stu-id="ce044-123">For example, the following example specifies that the certificate is located in the `CurrentUser` certificate store named `My`.</span></span>  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3.  <span data-ttu-id="ce044-124">Определить, где находится закрытый ключ для сертификата на компьютере с помощью [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) средства.</span><span class="sxs-lookup"><span data-stu-id="ce044-124">Determine where the private key for the certificate is located on the computer by using the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool.</span></span>  
  
         <span data-ttu-id="ce044-125">[FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) имя хранилища сертификатов, расположение хранилища сертификатов и что-то, которое однозначно идентифицирует этот сертификат для запуска этого средства.</span><span class="sxs-lookup"><span data-stu-id="ce044-125">The [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool requires the certificate store name, certificate store location, and something that uniquely identifies the certificate.</span></span> <span data-ttu-id="ce044-126">Средство принимает имя субъекта сертификата или его отпечаток в качестве уникального идентификатора.</span><span class="sxs-lookup"><span data-stu-id="ce044-126">The tool accepts either the certificate's subject name or its thumbprint as a unique identifier.</span></span> <span data-ttu-id="ce044-127">Дополнительные сведения о том, как определить отпечаток для сертификата см. в разделе [как: извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="ce044-127">For more information about how to determine the thumbprint for a certificate, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
         <span data-ttu-id="ce044-128">Следующий пример кода использует [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) , которая позволяет определить расположение файла закрытого ключа для сертификата в `My` хранить в `CurrentUser` с отпечатком `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span><span class="sxs-lookup"><span data-stu-id="ce044-128">The following code example uses the [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) tool to determine the location of the private key for a certificate in the `My` store in `CurrentUser` with a thumbprint of `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.</span></span>  
  
        ```  
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4.  <span data-ttu-id="ce044-129">Определите учетную запись, в которой выполняется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce044-129">Determine the account that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running under.</span></span>  
  
         <span data-ttu-id="ce044-130">В следующей таблице описана учетная запись, в которой выполняется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для данного сценария.</span><span class="sxs-lookup"><span data-stu-id="ce044-130">The following table details the account under which [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running for a given scenario.</span></span>  
  
        |<span data-ttu-id="ce044-131">Сценарий</span><span class="sxs-lookup"><span data-stu-id="ce044-131">Scenario</span></span>|<span data-ttu-id="ce044-132">Идентификатор процесса</span><span class="sxs-lookup"><span data-stu-id="ce044-132">Process identity</span></span>|  
        |--------------|----------------------|  
        |<span data-ttu-id="ce044-133">Клиент (консоль или приложение WinForms).</span><span class="sxs-lookup"><span data-stu-id="ce044-133">Client (console or WinForms application).</span></span>|<span data-ttu-id="ce044-134">Текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="ce044-134">Currently logged in user.</span></span>|  
        |<span data-ttu-id="ce044-135">Служба, являющаяся резидентной.</span><span class="sxs-lookup"><span data-stu-id="ce044-135">Service that is self-hosted.</span></span>|<span data-ttu-id="ce044-136">Текущий пользователь.</span><span class="sxs-lookup"><span data-stu-id="ce044-136">Currently logged in user.</span></span>|  
        |<span data-ttu-id="ce044-137">Служба, размещенная в IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) или IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ce044-137">Service that is hosted in IIS 6.0 ([!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]) or IIS 7.0 ([!INCLUDE[wv](../../../../includes/wv-md.md)]).</span></span>|<span data-ttu-id="ce044-138">NETWORK SERVICE</span><span class="sxs-lookup"><span data-stu-id="ce044-138">NETWORK SERVICE</span></span>|  
        |<span data-ttu-id="ce044-139">Служба, размещенная в IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="ce044-139">Service that is hosted in IIS 5.X ([!INCLUDE[wxp](../../../../includes/wxp-md.md)]).</span></span>|<span data-ttu-id="ce044-140">Управляется с помощью элемента `<processModel>` в файле Machine.config.</span><span class="sxs-lookup"><span data-stu-id="ce044-140">Controlled by the `<processModel>` element in the Machine.config file.</span></span> <span data-ttu-id="ce044-141">По умолчанию используется учетная запись ASPNET.</span><span class="sxs-lookup"><span data-stu-id="ce044-141">The default account is ASPNET.</span></span>|  
  
    5.  <span data-ttu-id="ce044-142">С помощью соответствующего средства (например, cacls.exe) предоставьте учетной записи, в которой выполняется [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], доступ для чтения к файлу, содержащему закрытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ce044-142">Grant read access to the file that contains the private key to the account that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is running under, using a tool such as cacls.exe.</span></span>  
  
         <span data-ttu-id="ce044-143">В следующем примере кода изменяется (/E) список управления доступом (ACL) для заданного файла, чтобы предоставить (/G) учетной записи NETWORK SERVICE доступ для чтения (:R) к файлу.</span><span class="sxs-lookup"><span data-stu-id="ce044-143">The following code example edits (/E) the access control list (ACL) for the specified file to grant (/G) the NETWORK SERVICE account read (:R) access to the file.</span></span>  
  
        ```  
        cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="ce044-144">См. также</span><span class="sxs-lookup"><span data-stu-id="ce044-144">See Also</span></span>  
 [<span data-ttu-id="ce044-145">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="ce044-145">FindPrivateKey</span></span>](../../../../docs/framework/wcf/samples/findprivatekey.md)  
 [<span data-ttu-id="ce044-146">Практическое руководство. Извлечение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="ce044-146">How to: Retrieve the Thumbprint of a Certificate</span></span>](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)  
 [<span data-ttu-id="ce044-147">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="ce044-147">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
