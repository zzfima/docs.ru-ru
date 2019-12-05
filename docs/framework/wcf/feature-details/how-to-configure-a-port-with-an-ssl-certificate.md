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
ms.openlocfilehash: d2fe9a73f79408db08ef48d380940fcf6bb831c0
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838004"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="43186-102">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="43186-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="43186-103">При создании автономной службы Windows Communication Foundation (WCF) с классом <xref:System.ServiceModel.WSHttpBinding>, использующим безопасность транспорта, необходимо также настроить порт с помощью сертификата X. 509.</span><span class="sxs-lookup"><span data-stu-id="43186-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="43186-104">При создании нерезидентной службы можно разместить ее в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="43186-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="43186-105">Дополнительные сведения см. в разделе [Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="43186-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="43186-106">Выбор средства для настройки порта зависит от операционной системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="43186-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="43186-107">При работе в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)] следует использовать средство HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="43186-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="43186-108">Это средство установлено в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43186-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="43186-109">С [!INCLUDE[wxp](../../../../includes/wxp-md.md)]можно загрузить средство в [средствах поддержки Windows XP с пакетом обновления 2](https://go.microsoft.com/fwlink/?LinkId=88606)(SP2).</span><span class="sxs-lookup"><span data-stu-id="43186-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="43186-110">Дополнительные сведения см. в разделе [Общие сведения об HttpCfg](https://go.microsoft.com/fwlink/?LinkId=88605).</span><span class="sxs-lookup"><span data-stu-id="43186-110">For more information, see [Httpcfg Overview](https://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="43186-111">В [документации по средствам поддержки Windows](https://go.microsoft.com/fwlink/?LinkId=94840) описывается синтаксис средства Httpcfg. exe.</span><span class="sxs-lookup"><span data-stu-id="43186-111">The [Windows Support Tools documentation](https://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="43186-112">Если вы используете Windows Vista, используйте уже установленное средство Netsh. exe.</span><span class="sxs-lookup"><span data-stu-id="43186-112">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="43186-113">В этом разделе описывается выполнение нескольких процедур.</span><span class="sxs-lookup"><span data-stu-id="43186-113">This topic describes how to accomplish several procedures:</span></span>  
  
- <span data-ttu-id="43186-114">Определение текущей конфигурации портов компьютера.</span><span class="sxs-lookup"><span data-stu-id="43186-114">Determining a computer's current port configuration.</span></span>  
  
- <span data-ttu-id="43186-115">Возвращение отпечатка сертификата (необходимо для выполнения следующих двух процедур).</span><span class="sxs-lookup"><span data-stu-id="43186-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
- <span data-ttu-id="43186-116">Выполнение привязки SSL-сертификата к конфигурации порта.</span><span class="sxs-lookup"><span data-stu-id="43186-116">Binding an SSL certificate to a port configuration.</span></span>  
  
- <span data-ttu-id="43186-117">Выполнение привязки SSL-сертификата к конфигурации порта и поддержка сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="43186-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
- <span data-ttu-id="43186-118">Удаление SSL-сертификата из номера порта.</span><span class="sxs-lookup"><span data-stu-id="43186-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="43186-119">Обратите внимание, что для изменения сертификатов, хранящихся на компьютере, требуются привилегии администратора.</span><span class="sxs-lookup"><span data-stu-id="43186-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="43186-120">Определение конфигурации портов</span><span class="sxs-lookup"><span data-stu-id="43186-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="43186-121">В [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)]используйте средство HttpCfg. exe для просмотра текущей конфигурации порта с помощью **запроса** и коммутаторов **SSL** , как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="43186-122">В Windows Vista используйте средство Netsh. exe для просмотра текущей конфигурации порта, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-122">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="43186-123">Возвращение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="43186-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="43186-124">С помощью оснастки MMC найдите сертификат X.509, который используется для проверки подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="43186-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="43186-125">(Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки консоли MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).)</span><span class="sxs-lookup"><span data-stu-id="43186-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="43186-126">Получите доступ к отпечатку сертификата.</span><span class="sxs-lookup"><span data-stu-id="43186-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="43186-127">Дополнительные сведения см. в статье [Практическое руководство. Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="43186-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="43186-128">Скопируйте отпечаток сертификата в текстовый редактор, например "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="43186-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="43186-129">Удалите все пробелы между шестнадцатеричными символами.</span><span class="sxs-lookup"><span data-stu-id="43186-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="43186-130">Эту задачу можно выполнить, в том числе, с помощью функции поиска и замены текстового редактора, заменив каждый пробел символом null.</span><span class="sxs-lookup"><span data-stu-id="43186-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="43186-131">Выполнение привязки SSL-сертификата к номеру порта</span><span class="sxs-lookup"><span data-stu-id="43186-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="43186-132">Для выполнения привязки сертификата к номеру порта в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)] следует использовать средство HttpCfg.exe в режиме "set" в хранилище SSL.</span><span class="sxs-lookup"><span data-stu-id="43186-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="43186-133">Это средство использует отпечаток для идентификации сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="43186-134">Параметр **-i** имеет синтаксис `IP`:`port` и указывает средству установить сертификат на порт 8012 компьютера.</span><span class="sxs-lookup"><span data-stu-id="43186-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="43186-135">Дополнительно, четыре нуля, предшествующие номеру, можно заменить на фактический IP-адрес компьютера.</span><span class="sxs-lookup"><span data-stu-id="43186-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="43186-136">Параметр **-h** указывает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="43186-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="43186-137">В Windows Vista используйте средство Netsh. exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-137">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - <span data-ttu-id="43186-138">Параметр **certhash** указывает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="43186-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="43186-139">Параметр **иппорт** указывает IP-адрес и порт, а также функции, аналогичные параметру **-i** , описанному в средстве HttpCfg. exe.</span><span class="sxs-lookup"><span data-stu-id="43186-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="43186-140">Параметр **AppID** — это идентификатор GUID, который можно использовать для поиска приложения-владельца.</span><span class="sxs-lookup"><span data-stu-id="43186-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="43186-141">Выполнение привязки SSL-сертификата к номеру порта и поддержка сертификатов клиента</span><span class="sxs-lookup"><span data-stu-id="43186-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="43186-142">В [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)] для поддержки клиентов, проходящих проверку подлинности с сертификатами X.509 на транспортном уровне, необходимо выполнить вышеописанные процедуры и передать дополнительный параметр командной строки средству HttpCfg.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="43186-143">Параметр **-f** имеет синтаксис `n` где n — число от 1 до 7.</span><span class="sxs-lookup"><span data-stu-id="43186-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="43186-144">Как показано в предыдущем примере, значение 2 включает сертификаты клиента на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="43186-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="43186-145">Значение 3 включает сертификаты клиента и сопоставляет их учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="43186-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="43186-146">Поведение других значений описано в справке средства HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="43186-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="43186-147">В Windows Vista для поддержки клиентов, которые проходят проверку подлинности с помощью сертификатов X. 509 на транспортном уровне, выполните предыдущую процедуру, но с дополнительным параметром, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-147">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="43186-148">Удаление SSL-сертификата из номера порта</span><span class="sxs-lookup"><span data-stu-id="43186-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="43186-149">Для просмотра портов и отпечатков всех привязок на компьютере следует использовать средство HttpCfg.exe или Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="43186-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="43186-150">Чтобы напечатать данные на диск, используйте символ перенаправления ">", как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="43186-151">В [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)]используйте средство HttpCfg. exe с ключевыми словами **Delete** и **SSL** .</span><span class="sxs-lookup"><span data-stu-id="43186-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="43186-152">Используйте параметр **-i** , чтобы указать `IP`:`port` Number, и параметр **-h** , чтобы указать отпечаток.</span><span class="sxs-lookup"><span data-stu-id="43186-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="43186-153">В Windows Vista используйте средство Netsh. exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="43186-153">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="43186-154">Пример</span><span class="sxs-lookup"><span data-stu-id="43186-154">Example</span></span>  
 <span data-ttu-id="43186-155">В следующем примере кода показано, как создавать резидентную службу с использованием класса <xref:System.ServiceModel.WSHttpBinding>, установленного на безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="43186-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="43186-156">При создании приложения необходимо задать номер порта в адресе.</span><span class="sxs-lookup"><span data-stu-id="43186-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="43186-157">См. также:</span><span class="sxs-lookup"><span data-stu-id="43186-157">See also</span></span>

- [<span data-ttu-id="43186-158">Безопасность транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="43186-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
