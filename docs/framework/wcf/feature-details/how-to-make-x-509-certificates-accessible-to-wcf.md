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
ms.openlocfilehash: 14f2242ab55795c74fa169382fef846bc0e60ace
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184897"
---
# <a name="how-to-make-x509-certificates-accessible-to-wcf"></a>Практическое руководство. Предоставление доступа к сертификатам X.509 для WCF
Чтобы сделать сертификат X.509 доступным для Windows Communication Foundation (WCF), код приложения должен указать имя и местоположение магазина сертификатов. В некоторых случаях идентификатор процесса должен иметь доступ к файлу, который содержит закрытый ключ, связанный с сертификатом X.509. Чтобы получить закрытый ключ, связанный с сертификатом X.509 в магазине сертификатов, WCF должна иметь на это разрешение. По умолчанию доступ к закрытому ключу сертификата имеют только владелец и системная учетная запись.  
  
### <a name="to-make-x509-certificates-accessible-to-wcf"></a>Предоставление доступа к сертификатам X.509 для WCF  
  
1. Предоставь учетную запись, в которой WCF работает читать доступ к файлу, который содержит частный ключ, связанный с сертификатом X.509.  
  
    1. Определите, требует сярприг для чтения частного ключа для сертификата X.509.  
  
         В следующей таблице приводятся сведения о том, должен ли закрытый ключ быть доступным при использовании сертификата X.509.  
  
        |Использование сертификата X.509|Закрытый ключ|  
        |---------------------------|-----------------|  
        |Цифровая подпись исходящего сообщения SOAP.|Да|  
        |Проверка подписи входящего сообщения SOAP.|нет|  
        |Шифрование исходящего сообщения SOAP.|нет|  
        |Расшифровка входящего сообщения SOAP.|Да|  
  
    2. Определите расположение и имя хранилища сертификатов, в котором хранится сертификат.  
  
         Хранилище сертификатов, в котором хранится сертификат, задается в коде приложения или конфигурации. Например, в следующем примере задано, что сертификат расположен в хранилище сертификатов `CurrentUser` с именем `My`.  
  
         [!code-csharp[x509Accessible#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/x509accessible/cs/source.cs#1)]
         [!code-vb[x509Accessible#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/x509accessible/vb/source.vb#1)]  
  
    3. Определите, где частный ключ для сертификата находится на компьютере с помощью инструмента [FindPrivateKey.](../../../../docs/framework/wcf/samples/findprivatekey.md)  
  
         Инструмент [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) требует названия магазина сертификата, местоположения магазина сертификата и чего-то, что однозначно идентифицирует сертификат. Средство принимает имя субъекта сертификата или его отпечаток в качестве уникального идентификатора. Для получения дополнительной [информации](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)о том, как определить отпечаток пальца для сертификата, см.  
  
         Следующий пример кода использует инструмент [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md) для определения местоположения частного ключа для сертификата в `My` `CurrentUser` магазине с отпечатком пальца `46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d`.  
  
        ```console
        findprivatekey.exe My CurrentUser -t "46 dd 0e 7a ed 0b 7a 31 9b 02 a3 a0 43 7a d8 3f 60 40 92 9d" -a  
        ```  
  
    4. Определите учетную запись, под которую работает WCF.  
  
         В следующей таблице подробно описан счет, в соответствии с которым WCF работает для данного сценария.  
  
        |Сценарий|Идентификатор процесса|  
        |--------------|----------------------|  
        |Клиент (консоль или приложение WinForms).|Текущий пользователь.|  
        |Служба, являющаяся резидентной.|Текущий пользователь.|  
        |Служба, размещенная в IIS 6.0 (Windows Server 2003) или IIS 7.0 (Windows Vista).|СЕТЕВАЯ СЛУЖБА|  
        |Служба, размещенная в IIS 5.X (Windows XP).|Управляется с помощью элемента `<processModel>` в файле Machine.config. По умолчанию используется учетная запись ASPNET.|  
  
    5. Грант прочитает доступ к файлу, содержащему закрытый ключ к учетной записи, под которой работает WCF, используя такой инструмент, как icacls.exe.  
  
         Следующий пример кода редотирует дискреционный список управления доступом (DACL) для указанного файла, чтобы предоставить учетной записи NETWORK SERVICE доступ к файлу.  
  
        ```console
        icacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /grant "NETWORK SERVICE":R  
        ```  
  
## <a name="see-also"></a>См. также раздел

- [FindPrivateKey](../../../../docs/framework/wcf/samples/findprivatekey.md)
- [Практическое руководство. Извлечение отпечатка сертификата](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)
- [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
