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
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a>Практическое руководство. Настройка порта с использованием SSL-сертификата

При создании самостоятельно госслужбы Windows Communication Foundation <xref:System.ServiceModel.WSHttpBinding> (WCF) с классом, используюим транспортную безопасность, необходимо также настроить порт с сертификатом X.509. При создании нерезидентной службы можно разместить ее в службах IIS. Для получения дополнительной [информации см.](../../../../docs/framework/wcf/feature-details/http-transport-security.md)  
  
 Выбор средства для настройки порта зависит от операционной системы компьютера.  
  
 Если вы работаете под управлением Windows Server 2003, используйте инструмент HttpCfg.exe. На Windows Server 2003 этот инструмент установлен. Для получения дополнительной информации [см.](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)) [Документация windows Support Tools](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) объясняет синтаксис для инструмента Httpcfg.exe.  
  
 Если вы работаете под управлением Windows Vista, используйте уже установленный инструмент Netsh.exe.
  
> [!NOTE]
> Изменение сертификатов, хранящихся на компьютере, требует административных привилегий.  
  
## <a name="determine-how-ports-are-configured"></a>Определить, как настроены порты  
  
1. В Windows Server 2003 или Windows XP используйте инструмент HttpCfg.exe для просмотра текущей конфигурации порта, используя **переключатели запросов** и **ssl,** как показано в следующем примере.  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. В Windows Vista используйте инструмент Netsh.exe для просмотра текущей конфигурации порта, как показано в следующем примере.  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a>Получите отпечаток пальца сертификата  
  
1. С помощью оснастки MMC найдите сертификат X.509, который используется для проверки подлинности клиента. Дополнительные сведения см. в разделе [Практическое руководство. Просмотр сертификатов с помощью оснастки MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).  
  
2. Получите доступ к отпечатку сертификата. Дополнительные сведения см. в статье [Практическое руководство. Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).  
  
3. Скопируйте отпечаток сертификата в текстовый редактор, например "Блокнот".  
  
4. Удалите все пробелы между шестнадцатеричными символами. Эту задачу можно выполнить, в том числе, с помощью функции поиска и замены текстового редактора, заменив каждый пробел символом null.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a>Привязать сертификат SSL к номеру порта  
  
1. В Windows Server 2003 или Windows XP используйте инструмент HttpCfg.exe в режиме "набор" в магазине Secure Sockets Layer (SSL), чтобы привязать сертификат к номеру порта. Это средство использует отпечаток для идентификации сертификата, как показано в следующем примере.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - Переключатель **-i** имеет `IP`синтаксис:`port` и инструктирует инструмент для установки сертификата на порт 8012 компьютера. Дополнительно, четыре нуля, предшествующие номеру, можно заменить на фактический IP-адрес компьютера.  
  
    - Переключатель **-h** определяет отпечаток пальца сертификата.  
  
2. В Windows Vista используйте инструмент Netsh.exe, как показано в следующем примере.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - Параметр **certhash** определяет отпечаток пальца сертификата.  
  
    - Параметр **ipport** определяет IP-адрес и порт, и функционирует так же, как **-я** переключатель httpcfg.exe инструмент описано.  
  
    - **Аппидный** параметр — это GUID, который может быть использован для идентификации приложения-владеющего.  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a>Привязать сертификат SSL к номеру порта и поддерживать сертификаты клиента  
  
1. В Windows Server 2003 или Windows XP, чтобы поддержать клиентов, которые аутентифицируют сертификаты X.509 на транспортном слое, следуйте предыдущей процедуре, но передают дополнительный параметр командной строки httpcfg.exe, как показано в следующем примере.  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     Переключатель **-f** имеет синтаксис, `n` где n является числом между 1 и 7. Как показано в предыдущем примере, значение 2 включает сертификаты клиента на транспортном уровне. Значение 3 включает сертификаты клиента и сопоставляет их учетной записи Windows. Поведение других значений описано в справке средства HttpCfg.exe.  
  
2. В Windows Vista, чтобы поддержать клиентов, которые аутентифицируют сятвентированные сертификаты X.509 на транспортном слое, следуйте предыдущей процедуре, но с дополнительным параметром, как показано в следующем примере.  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a>Удаление sSL-сертификата с номера порта  
  
1. Для просмотра портов и отпечатков всех привязок на компьютере следует использовать средство HttpCfg.exe или Netsh.exe. Для печати информации на диске используйте символ перенаправления ">", как показано в следующем примере.  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. В Windows Server 2003 или Windows XP используйте инструмент HttpCfg.exe с ключевыми словами **удаления** и **ssl.** Используйте **-i** переключатель,`port` чтобы указать: `IP`число, и **-h** переключатель, чтобы указать отпечаток пальца.  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. В Windows Vista используйте инструмент Netsh.exe, как показано в следующем примере.  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a>Пример  

 В следующем примере кода показано, как создавать резидентную службу с использованием класса <xref:System.ServiceModel.WSHttpBinding>, установленного на безопасность транспорта. При создании приложения необходимо задать номер порта в адресе.  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a>См. также раздел

- [Безопасность транспорта HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
