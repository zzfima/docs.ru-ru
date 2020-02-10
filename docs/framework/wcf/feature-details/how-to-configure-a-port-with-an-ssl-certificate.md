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
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Практическое руководство. Настройка порта с использованием SSL-сертификата

При создании автономной службы Windows Communication Foundation (WCF) с классом <xref:System.ServiceModel.WSHttpBinding>, использующим безопасность транспорта, необходимо также настроить порт с помощью сертификата X. 509. При создании нерезидентной службы можно разместить ее в службах IIS. Дополнительные сведения см. в разделе [Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).  
  
 Выбор средства для настройки порта зависит от операционной системы компьютера.  
  
 Если вы используете Windows Server 2003, используйте средство HttpCfg. exe. В Windows Server 2003 это средство установлено. Дополнительные сведения см. в разделе [Общие сведения об HttpCfg](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)). В [документации по средствам поддержки Windows](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) описывается синтаксис средства Httpcfg. exe.  
  
 Если вы используете Windows Vista, используйте уже установленное средство Netsh. exe. 
  
> [!NOTE]
> Для изменения сертификатов, хранящихся на компьютере, требуются права администратора.  
  
## <a name="determine-how-ports-are-configured"></a>Определение настроек портов  
  
1. В Windows Server 2003 или Windows XP используйте средство HttpCfg. exe для просмотра текущей конфигурации порта с помощью **запроса** и коммутаторов **SSL** , как показано в следующем примере.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. В Windows Vista используйте средство Netsh. exe для просмотра текущей конфигурации порта, как показано в следующем примере.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>Получение отпечатка сертификата  
  
1. С помощью оснастки MMC найдите сертификат X.509, который используется для проверки подлинности клиента. Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Получите доступ к отпечатку сертификата. Дополнительные сведения см. в статье [Практическое руководство. Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Скопируйте отпечаток сертификата в текстовый редактор, например "Блокнот".  
  
4. Удалите все пробелы между шестнадцатеричными символами. Эту задачу можно выполнить, в том числе, с помощью функции поиска и замены текстового редактора, заменив каждый пробел символом null.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>Привязка SSL-сертификата к номеру порта  
  
1. В Windows Server 2003 или Windows XP используйте средство HttpCfg. exe в режиме Set в хранилище SSL (SSL), чтобы привязать сертификат к номеру порта. Это средство использует отпечаток для идентификации сертификата, как показано в следующем примере.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - Параметр **-i** имеет синтаксис `IP`:`port` и указывает средству установить сертификат на порт 8012 компьютера. Дополнительно, четыре нуля, предшествующие номеру, можно заменить на фактический IP-адрес компьютера.  
  
    - Параметр **-h** указывает отпечаток сертификата.  
  
2. В Windows Vista используйте средство Netsh. exe, как показано в следующем примере.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    - Параметр **certhash** указывает отпечаток сертификата.  
  
    - Параметр **иппорт** указывает IP-адрес и порт, а также функции, аналогичные параметру **-i** , описанному в средстве HttpCfg. exe.  
  
    - Параметр **AppID** — это идентификатор GUID, который можно использовать для поиска приложения-владельца.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Привязка SSL-сертификата к номеру порта и поддержка клиентских сертификатов  
  
1. В Windows Server 2003 или Windows XP для поддержки клиентов, которые проходят проверку подлинности с помощью сертификатов X. 509 на транспортном уровне, выполните предыдущую процедуру, но передайте дополнительный параметр командной строки в HttpCfg. exe, как показано в следующем примере.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Параметр **-f** имеет синтаксис `n` где n — число от 1 до 7. Как показано в предыдущем примере, значение 2 включает сертификаты клиента на транспортном уровне. Значение 3 включает сертификаты клиента и сопоставляет их учетной записи Windows. Поведение других значений описано в справке средства HttpCfg.exe.  
  
2. В Windows Vista для поддержки клиентов, которые проходят проверку подлинности с помощью сертификатов X. 509 на транспортном уровне, выполните предыдущую процедуру, но с дополнительным параметром, как показано в следующем примере.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>Удаление SSL-сертификата из номера порта  
  
1. Для просмотра портов и отпечатков всех привязок на компьютере следует использовать средство HttpCfg.exe или Netsh.exe. Чтобы напечатать данные на диск, используйте символ перенаправления ">", как показано в следующем примере.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. В Windows Server 2003 или Windows XP используйте средство HttpCfg. exe с ключевыми словами **Delete** и **SSL** . Используйте параметр **-i** , чтобы указать `IP`:`port` Number, и параметр **-h** , чтобы указать отпечаток.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. В Windows Vista используйте средство Netsh. exe, как показано в следующем примере.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Пример  

 В следующем примере кода показано, как создавать резидентную службу с использованием класса <xref:System.ServiceModel.WSHttpBinding>, установленного на безопасность транспорта. При создании приложения необходимо задать номер порта в адресе.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
