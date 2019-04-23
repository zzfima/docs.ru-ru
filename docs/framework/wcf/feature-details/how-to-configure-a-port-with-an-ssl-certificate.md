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
ms.openlocfilehash: d709123895f361c1d2268a218b4163c8d195e1b4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59345590"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="2a692-102">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="2a692-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="2a692-103">При создании резидентной службы Windows Communication Foundation (WCF) с <xref:System.ServiceModel.WSHttpBinding> класса, использующим безопасность транспорта, необходимо также настроить порт с сертификатом X.509.</span><span class="sxs-lookup"><span data-stu-id="2a692-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="2a692-104">При создании нерезидентной службы можно разместить ее в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="2a692-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="2a692-105">Дополнительные сведения см. в разделе [безопасности транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="2a692-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="2a692-106">Выбор средства для настройки порта зависит от операционной системы компьютера.</span><span class="sxs-lookup"><span data-stu-id="2a692-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="2a692-107">При работе в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)] следует использовать средство HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="2a692-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="2a692-108">Это средство установлено в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2a692-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="2a692-109">С помощью [!INCLUDE[wxp](../../../../includes/wxp-md.md)], можно загрузить средство из [средства для поддержки Windows XP Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=88606).</span><span class="sxs-lookup"><span data-stu-id="2a692-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="2a692-110">Дополнительные сведения см. в разделе [Обзор Httpcfg](https://go.microsoft.com/fwlink/?LinkId=88605).</span><span class="sxs-lookup"><span data-stu-id="2a692-110">For more information, see [Httpcfg Overview](https://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="2a692-111">[Документации по средствам поддержки Windows](https://go.microsoft.com/fwlink/?LinkId=94840) описывается синтаксис средства Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="2a692-111">The [Windows Support Tools documentation](https://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="2a692-112">При работе в [!INCLUDE[wv](../../../../includes/wv-md.md)] следует использовать установленное средство Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="2a692-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="2a692-113">В этом разделе описывается выполнение нескольких процедур.</span><span class="sxs-lookup"><span data-stu-id="2a692-113">This topic describes how to accomplish several procedures:</span></span>  
  
-   <span data-ttu-id="2a692-114">Определение текущей конфигурации портов компьютера.</span><span class="sxs-lookup"><span data-stu-id="2a692-114">Determining a computer's current port configuration.</span></span>  
  
-   <span data-ttu-id="2a692-115">Возвращение отпечатка сертификата (необходимо для выполнения следующих двух процедур).</span><span class="sxs-lookup"><span data-stu-id="2a692-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
-   <span data-ttu-id="2a692-116">Выполнение привязки SSL-сертификата к конфигурации порта.</span><span class="sxs-lookup"><span data-stu-id="2a692-116">Binding an SSL certificate to a port configuration.</span></span>  
  
-   <span data-ttu-id="2a692-117">Выполнение привязки SSL-сертификата к конфигурации порта и поддержка сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="2a692-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
-   <span data-ttu-id="2a692-118">Удаление SSL-сертификата из номера порта.</span><span class="sxs-lookup"><span data-stu-id="2a692-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="2a692-119">Обратите внимание, что для изменения сертификатов, хранящихся на компьютере, требуются привилегии администратора.</span><span class="sxs-lookup"><span data-stu-id="2a692-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="2a692-120">Определение конфигурации портов</span><span class="sxs-lookup"><span data-stu-id="2a692-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="2a692-121">В [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)], используйте средство HttpCfg.exe для просмотра текущей конфигурации портов с помощью **запроса** и **ssl** переключается, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="2a692-122">Для просмотра текущей конфигурации портов в [!INCLUDE[wv](../../../../includes/wv-md.md)] следует использовать средство Netsh.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="2a692-123">Возвращение отпечатка сертификата</span><span class="sxs-lookup"><span data-stu-id="2a692-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="2a692-124">С помощью оснастки MMC найдите сертификат X.509, который используется для проверки подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="2a692-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="2a692-125">Дополнительные сведения см. в разделе [Как Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="2a692-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="2a692-126">Получите доступ к отпечатку сертификата.</span><span class="sxs-lookup"><span data-stu-id="2a692-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="2a692-127">Дополнительные сведения см. в разделе [Как Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="2a692-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="2a692-128">Скопируйте отпечаток сертификата в текстовый редактор, например "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="2a692-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="2a692-129">Удалите все пробелы между шестнадцатеричными символами.</span><span class="sxs-lookup"><span data-stu-id="2a692-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="2a692-130">Эту задачу можно выполнить, в том числе, с помощью функции поиска и замены текстового редактора, заменив каждый пробел символом null.</span><span class="sxs-lookup"><span data-stu-id="2a692-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="2a692-131">Выполнение привязки SSL-сертификата к номеру порта</span><span class="sxs-lookup"><span data-stu-id="2a692-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="2a692-132">Для выполнения привязки сертификата к номеру порта в [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)] следует использовать средство HttpCfg.exe в режиме "set" в хранилище SSL.</span><span class="sxs-lookup"><span data-stu-id="2a692-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="2a692-133">Это средство использует отпечаток для идентификации сертификата, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   <span data-ttu-id="2a692-134">**-I** коммутатора имеет синтаксис `IP`:`port` и указывает средству установить сертификат на порт 8012 компьютера.</span><span class="sxs-lookup"><span data-stu-id="2a692-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="2a692-135">Дополнительно, четыре нуля, предшествующие номеру, можно заменить на фактический IP-адрес компьютера.</span><span class="sxs-lookup"><span data-stu-id="2a692-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    -   <span data-ttu-id="2a692-136">**-H** — задает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="2a692-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="2a692-137">В [!INCLUDE[wv](../../../../includes/wv-md.md)] следует использовать средство Netsh.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   <span data-ttu-id="2a692-138">**Certhash** задает отпечаток сертификата.</span><span class="sxs-lookup"><span data-stu-id="2a692-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    -   <span data-ttu-id="2a692-139">**Ipport** параметр указывает IP-адрес и порт, а аналогичен принципу **-i** переключатель средства Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="2a692-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    -   <span data-ttu-id="2a692-140">**Appid** параметр представляет собой идентификатор GUID, который может использоваться для идентификации приложения-владельца.</span><span class="sxs-lookup"><span data-stu-id="2a692-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="2a692-141">Выполнение привязки SSL-сертификата к номеру порта и поддержка сертификатов клиента</span><span class="sxs-lookup"><span data-stu-id="2a692-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="2a692-142">В [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)] для поддержки клиентов, проходящих проверку подлинности с сертификатами X.509 на транспортном уровне, необходимо выполнить вышеописанные процедуры и передать дополнительный параметр командной строки средству HttpCfg.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="2a692-143">**-F** коммутатора имеет синтаксис `n` где n — число от 1 до 7.</span><span class="sxs-lookup"><span data-stu-id="2a692-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="2a692-144">Как показано в предыдущем примере, значение 2 включает сертификаты клиента на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="2a692-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="2a692-145">Значение 3 включает сертификаты клиента и сопоставляет их учетной записи Windows.</span><span class="sxs-lookup"><span data-stu-id="2a692-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="2a692-146">Поведение других значений описано в справке средства HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="2a692-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="2a692-147">В [!INCLUDE[wv](../../../../includes/wv-md.md)] для поддержки клиентов, проходящих проверку подлинности с сертификатами X.509 на транспортном уровне, необходимо выполнить вышеописанные процедуры, используя дополнительный параметр, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="2a692-148">Удаление SSL-сертификата из номера порта</span><span class="sxs-lookup"><span data-stu-id="2a692-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="2a692-149">Для просмотра портов и отпечатков всех привязок на компьютере следует использовать средство HttpCfg.exe или Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="2a692-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="2a692-150">Для вывода информации на диск, используйте символ перенаправления «>», как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2. <span data-ttu-id="2a692-151">В [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] или [!INCLUDE[wxp](../../../../includes/wxp-md.md)], используйте средство HttpCfg.exe с **удалить** и **ssl** ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="2a692-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="2a692-152">Используйте **-i** для указания `IP`:`port` номер и **-h** коммутатора для задания отпечатка.</span><span class="sxs-lookup"><span data-stu-id="2a692-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="2a692-153">В [!INCLUDE[wv](../../../../includes/wv-md.md)] следует использовать средство Netsh.exe, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2a692-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="2a692-154">Пример</span><span class="sxs-lookup"><span data-stu-id="2a692-154">Example</span></span>  
 <span data-ttu-id="2a692-155">В следующем примере кода показано, как создавать резидентную службу с использованием класса <xref:System.ServiceModel.WSHttpBinding>, установленного на безопасность транспорта.</span><span class="sxs-lookup"><span data-stu-id="2a692-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="2a692-156">При создании приложения необходимо задать номер порта в адресе.</span><span class="sxs-lookup"><span data-stu-id="2a692-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2a692-157">См. также</span><span class="sxs-lookup"><span data-stu-id="2a692-157">See also</span></span>

- [<span data-ttu-id="2a692-158">Безопасность транспорта HTTP</span><span class="sxs-lookup"><span data-stu-id="2a692-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
