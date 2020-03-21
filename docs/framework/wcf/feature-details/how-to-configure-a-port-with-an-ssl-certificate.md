---
title: Практическое руководство. Настройка порта с использованием SSL-сертификата
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185108"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="8bb3b-102">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="8bb3b-102">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="8bb3b-103">При создании самостоятельно госслужбы Windows Communication Foundation <xref:System.ServiceModel.WSHttpBinding> (WCF) с классом, используюим транспортную безопасность, необходимо также настроить порт с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="8bb3b-104">При создании нерезидентной службы можно разместить ее в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="8bb3b-105">Для получения дополнительной [информации см.](../../../../docs/framework/wcf/feature-details/http-transport-security.md)</span><span class="sxs-lookup"><span data-stu-id="8bb3b-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="8bb3b-106">Выбор средства для настройки порта зависит от операционной системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="8bb3b-107">Если вы работаете под управлением Windows Server 2003, используйте инструмент HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-107">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="8bb3b-108">На Windows Server 2003 этот инструмент установлен.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-108">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="8bb3b-109">Для получения дополнительной информации [см.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="8bb3b-109">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="8bb3b-110">[Документация windows Support Tools](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) объясняет синтаксис для инструмента Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-110">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="8bb3b-111">Если вы работаете под управлением Windows Vista, используйте уже установленный инструмент Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-111">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8bb3b-112">Изменение сертификатов, хранящихся на компьютере, требует административных привилегий.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-112">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="8bb3b-113">Определить, как настроены порты</span><span class="sxs-lookup"><span data-stu-id="8bb3b-113">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="8bb3b-114">В Windows Server 2003 или Windows XP используйте инструмент HttpCfg.exe для просмотра текущей конфигурации порта, используя **переключатели запросов** и **ssl,** как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-114">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="8bb3b-115">В Windows Vista используйте инструмент Netsh.exe для просмотра текущей конфигурации порта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-115">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="8bb3b-116">Получите отпечаток пальца сертификата</span><span class="sxs-lookup"><span data-stu-id="8bb3b-116">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="8bb3b-117">С помощью оснастки MMC найдите сертификат X.509, который используется для проверки подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-117">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="8bb3b-118">Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="8bb3b-118">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="8bb3b-119">Получите доступ к отпечатку сертификата.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-119">Access the certificate's thumbprint.</span></span> <span data-ttu-id="8bb3b-120">Дополнительные сведения см. в статье [Практическое руководство. Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="8bb3b-120">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="8bb3b-121">Скопируйте отпечаток сертификата в текстовый редактор, например "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="8bb3b-121">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="8bb3b-122">Удалите все пробелы между шестнадцатеричными символами.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-122">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="8bb3b-123">Эту задачу можно выполнить, в том числе, с помощью функции поиска и замены текстового редактора, заменив каждый пробел символом null.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-123">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="8bb3b-124">Привязать сертификат SSL к номеру порта</span><span class="sxs-lookup"><span data-stu-id="8bb3b-124">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="8bb3b-125">В Windows Server 2003 или Windows XP используйте инструмент HttpCfg.exe в режиме "набор" в магазине Secure Sockets Layer (SSL), чтобы привязать сертификат к номеру порта.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-125">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="8bb3b-126">Это средство использует отпечаток для идентификации сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-126">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="8bb3b-127">Переключатель **-i** имеет `IP`синтаксис:`port` и инструктирует инструмент для установки сертификата на порт 8012 компьютера.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-127">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="8bb3b-128">Дополнительно, четыре нуля, предшествующие номеру, можно заменить на фактический IP-адрес компьютера.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-128">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="8bb3b-129">Переключатель **-h** определяет отпечаток пальца сертификата.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-129">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="8bb3b-130">В Windows Vista используйте инструмент Netsh.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-130">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - <span data-ttu-id="8bb3b-131">Параметр **certhash** определяет отпечаток пальца сертификата.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-131">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="8bb3b-132">Параметр **ipport** определяет IP-адрес и порт, и функционирует так же, как **-я** переключатель httpcfg.exe инструмент описано.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-132">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="8bb3b-133">**Аппидный** параметр — это GUID, который может быть использован для идентификации приложения-владеющего.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-133">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="8bb3b-134">Привязать сертификат SSL к номеру порта и поддерживать сертификаты клиента</span><span class="sxs-lookup"><span data-stu-id="8bb3b-134">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="8bb3b-135">В Windows Server 2003 или Windows XP, чтобы поддержать клиентов, которые аутентифицируют сертификаты X.509 на транспортном слое, следуйте предыдущей процедуре, но передают дополнительный параметр командной строки httpcfg.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-135">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="8bb3b-136">Переключатель **-f** имеет синтаксис, `n` где n является числом между 1 и 7.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-136">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="8bb3b-137">Как показано в предыдущем примере, значение 2 включает сертификаты клиента на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-137">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="8bb3b-138">Значение 3 включает сертификаты клиента и сопоставляет их учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-138">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="8bb3b-139">Поведение других значений описано в справке средства HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-139">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="8bb3b-140">В Windows Vista, чтобы поддержать клиентов, которые аутентифицируют сятвентированные сертификаты X.509 на транспортном слое, следуйте предыдущей процедуре, но с дополнительным параметром, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-140">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="8bb3b-141">Удаление sSL-сертификата с номера порта</span><span class="sxs-lookup"><span data-stu-id="8bb3b-141">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="8bb3b-142">Для просмотра портов и отпечатков всех привязок на компьютере следует использовать средство HttpCfg.exe или Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-142">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="8bb3b-143">Для печати информации на диске используйте символ перенаправления ">", как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-143">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="8bb3b-144">В Windows Server 2003 или Windows XP используйте инструмент HttpCfg.exe с ключевыми словами **удаления** и **ssl.**</span><span class="sxs-lookup"><span data-stu-id="8bb3b-144">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="8bb3b-145">Используйте **-i** переключатель,`port` чтобы указать: `IP`число, и **-h** переключатель, чтобы указать отпечаток пальца.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-145">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="8bb3b-146">В Windows Vista используйте инструмент Netsh.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-146">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="8bb3b-147">Пример</span><span class="sxs-lookup"><span data-stu-id="8bb3b-147">Example</span></span>  

 <span data-ttu-id="8bb3b-148">В следующем примере кода показано, как создавать резидентную службу с использованием класса <xref:System.ServiceModel.WSHttpBinding>, установленного на безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-148">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="8bb3b-149">При создании приложения необходимо задать номер порта в адресе.</span><span class="sxs-lookup"><span data-stu-id="8bb3b-149">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="8bb3b-150">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8bb3b-150">See also</span></span>

- [<span data-ttu-id="8bb3b-151">Безопасность транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="8bb3b-151">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
