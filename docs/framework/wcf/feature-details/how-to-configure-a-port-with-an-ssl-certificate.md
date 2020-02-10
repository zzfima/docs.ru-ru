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
ms.openlocfilehash: 99a08c9714e8f8cef0c1c96ac7f890d163324b44
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095025"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="7b4a3-102">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="7b4a3-102">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="7b4a3-103">При создании автономной службы Windows Communication Foundation (WCF) с классом <xref:System.ServiceModel.WSHttpBinding>, использующим безопасность транспорта, необходимо также настроить порт с помощью сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="7b4a3-104">При создании нерезидентной службы можно разместить ее в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="7b4a3-105">Дополнительные сведения см. в разделе [Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="7b4a3-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="7b4a3-106">Выбор средства для настройки порта зависит от операционной системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="7b4a3-107">Если вы используете Windows Server 2003, используйте средство HttpCfg. exe.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-107">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="7b4a3-108">В Windows Server 2003 это средство установлено.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-108">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="7b4a3-109">Дополнительные сведения см. в разделе [Общие сведения об HttpCfg](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="7b4a3-109">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="7b4a3-110">В [документации по средствам поддержки Windows](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) описывается синтаксис средства Httpcfg. exe.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-110">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="7b4a3-111">Если вы используете Windows Vista, используйте уже установленное средство Netsh. exe.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-111">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7b4a3-112">Для изменения сертификатов, хранящихся на компьютере, требуются права администратора.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-112">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="7b4a3-113">Определение настроек портов</span><span class="sxs-lookup"><span data-stu-id="7b4a3-113">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="7b4a3-114">В Windows Server 2003 или Windows XP используйте средство HttpCfg. exe для просмотра текущей конфигурации порта с помощью **запроса** и коммутаторов **SSL** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-114">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="7b4a3-115">В Windows Vista используйте средство Netsh. exe для просмотра текущей конфигурации порта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-115">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="7b4a3-116">Получение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="7b4a3-116">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="7b4a3-117">С помощью оснастки MMC найдите сертификат X.509, который используется для проверки подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-117">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="7b4a3-118">Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="7b4a3-118">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="7b4a3-119">Получите доступ к отпечатку сертификата.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-119">Access the certificate's thumbprint.</span></span> <span data-ttu-id="7b4a3-120">Дополнительные сведения см. в статье [Практическое руководство. Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="7b4a3-120">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="7b4a3-121">Скопируйте отпечаток сертификата в текстовый редактор, например "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="7b4a3-121">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="7b4a3-122">Удалите все пробелы между шестнадцатеричными символами.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-122">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="7b4a3-123">Эту задачу можно выполнить, в том числе, с помощью функции поиска и замены текстового редактора, заменив каждый пробел символом null.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-123">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="7b4a3-124">Привязка SSL-сертификата к номеру порта</span><span class="sxs-lookup"><span data-stu-id="7b4a3-124">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="7b4a3-125">В Windows Server 2003 или Windows XP используйте средство HttpCfg. exe в режиме Set в хранилище SSL (SSL), чтобы привязать сертификат к номеру порта.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-125">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="7b4a3-126">Это средство использует отпечаток для идентификации сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-126">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="7b4a3-127">Параметр **-i** имеет синтаксис `IP`:`port` и указывает средству установить сертификат на порт 8012 компьютера.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-127">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="7b4a3-128">Дополнительно, четыре нуля, предшествующие номеру, можно заменить на фактический IP-адрес компьютера.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-128">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="7b4a3-129">Параметр **-h** указывает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-129">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="7b4a3-130">В Windows Vista используйте средство Netsh. exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-130">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - <span data-ttu-id="7b4a3-131">Параметр **certhash** указывает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-131">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="7b4a3-132">Параметр **иппорт** указывает IP-адрес и порт, а также функции, аналогичные параметру **-i** , описанному в средстве HttpCfg. exe.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-132">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="7b4a3-133">Параметр **AppID** — это идентификатор GUID, который можно использовать для поиска приложения-владельца.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-133">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="7b4a3-134">Привязка SSL-сертификата к номеру порта и поддержка клиентских сертификатов</span><span class="sxs-lookup"><span data-stu-id="7b4a3-134">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="7b4a3-135">В Windows Server 2003 или Windows XP для поддержки клиентов, которые проходят проверку подлинности с помощью сертификатов X. 509 на транспортном уровне, выполните предыдущую процедуру, но передайте дополнительный параметр командной строки в HttpCfg. exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-135">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="7b4a3-136">Параметр **-f** имеет синтаксис `n` где n — число от 1 до 7.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-136">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="7b4a3-137">Как показано в предыдущем примере, значение 2 включает сертификаты клиента на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-137">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="7b4a3-138">Значение 3 включает сертификаты клиента и сопоставляет их учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-138">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="7b4a3-139">Поведение других значений описано в справке средства HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-139">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="7b4a3-140">В Windows Vista для поддержки клиентов, которые проходят проверку подлинности с помощью сертификатов X. 509 на транспортном уровне, выполните предыдущую процедуру, но с дополнительным параметром, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-140">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="7b4a3-141">Удаление SSL-сертификата из номера порта</span><span class="sxs-lookup"><span data-stu-id="7b4a3-141">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="7b4a3-142">Для просмотра портов и отпечатков всех привязок на компьютере следует использовать средство HttpCfg.exe или Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-142">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="7b4a3-143">Чтобы напечатать данные на диск, используйте символ перенаправления ">", как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-143">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="7b4a3-144">В Windows Server 2003 или Windows XP используйте средство HttpCfg. exe с ключевыми словами **Delete** и **SSL** .</span><span class="sxs-lookup"><span data-stu-id="7b4a3-144">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="7b4a3-145">Используйте параметр **-i** , чтобы указать `IP`:`port` Number, и параметр **-h** , чтобы указать отпечаток.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-145">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="7b4a3-146">В Windows Vista используйте средство Netsh. exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-146">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="7b4a3-147">Пример</span><span class="sxs-lookup"><span data-stu-id="7b4a3-147">Example</span></span>  

 <span data-ttu-id="7b4a3-148">В следующем примере кода показано, как создавать резидентную службу с использованием класса <xref:System.ServiceModel.WSHttpBinding>, установленного на безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-148">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="7b4a3-149">При создании приложения необходимо задать номер порта в адресе.</span><span class="sxs-lookup"><span data-stu-id="7b4a3-149">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="7b4a3-150">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="7b4a3-150">See also</span></span>

- [<span data-ttu-id="7b4a3-151">Безопасность транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="7b4a3-151">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
