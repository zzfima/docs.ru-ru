---
title: Инструкции по установке сертификата сервера в службах IIS
ms.date: 03/30/2017
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
ms.openlocfilehash: a89d907b9be25c83a74f0c5d60d184637552f297
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54221106"
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a>Инструкции по установке сертификата сервера в службах IIS
Чтобы запускать примеры, которые безопасным образом взаимодействуют со службами IIS, необходимо создать и установить сертификат сервера.  
  
## <a name="step-1-creating-certificates"></a>Шаг 1. Создание сертификатов  
 Чтобы создать сертификат для компьютера, откройте командную строку разработчика для Visual Studio с правами администратора и запустите файл Setup.bat, входящий в состав каждого из образцов, которые используют безопасное взаимодействие со службами IIS. Перед запуском пакетного файла убедитесь, что путь включает папку, содержащую программу Makecert.exe. Следующая команда служит для создания сертификата в файле Setup.bat.  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a>Шаг 2. Установка сертификатов  
 Шаги, необходимые для установки созданных сертификатов, зависят от используемой версии IIS.  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a>Установка IIS в IIS 5.1 (Windows XP) и IIS 6.0 (Windows Server 2003)  
  
1.  Откройте оснастку консоли MMC диспетчера служб IIS.  
  
2.  Щелкните правой кнопкой мыши веб-сайта по умолчанию и выберите **свойства**.  
  
3.  Выберите **Безопасность каталога** вкладки.  
  
4.  Нажмите кнопку **сертификат сервера** кнопки. Будет запущен мастер сертификатов веб-сервера.  
  
5.  Завершите работу мастера. Выберите назначение сертификата. Из отображаемого списка сертификатов выберите сертификат ServiceModelSamples-HTTPS-Server.  
  
     ![Мастер сертификатов IIS](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")  
  
6.  Тестирование доступа к службе в браузере с помощью HTTPS-адрес `https://localhost/servicemodelsamples/service.svc`.  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a>Если до этого был настроен протокол SSL с помощью Httpcfg.exe  
  
1.  С помощью программы Makecert.exe (или запустив файл Setup.bat) создайте сертификат сервера.  
  
2.  Запустите диспетчер IIS и установите сертификат в соответствии с описанными выше действиями.  
  
3.  Добавьте следующую строку кода в клиентскую программу.  
  
> [!IMPORTANT]
>  Этот код необходим только для тестовых сертификатов, наподобие созданных с помощью Makecert.exe. Для кода производственного назначения это делать не рекомендуется.  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a>Установка IIS в IIS 7.0 (Windows Vista и Windows Server 2008)  
  
1.  Из **запустить** меню, нажмите кнопку **запуска**, затем введите **inetmgr** чтобы открыть оснастку MMC Internet Information Services (IIS).  
  
2.  Щелкните правой кнопкой мыши **Default Web Site** и выберите **изменить привязки...**  
  
3.  Нажмите кнопку **добавить** кнопки **привязки сайта** диалоговое окно.  
  
4.  Выберите **HTTPS** из **тип** стрелку раскрывающегося списка.  
  
5.  Выберите **ServiceModelSamples-HTTPS-Server** из **SSL-сертификат** стрелку раскрывающегося списка и нажмите кнопку **ОК**.  
  
6.  Тестирование доступа к службе в браузере с помощью HTTPS-адрес `https://localhost/servicemodelsamples/service.svc`.  
  
> [!NOTE]
>  Поскольку только что установленный тестовый сертификат не является доверенным сертификатом, при переходе по локальным веб-адресам, защищенным с помощью этого сертификата, могут появиться дополнительные предупреждения системы безопасности Internet Explorer.  
  
## <a name="removing-certificates"></a>Удаление сертификатов  
  
-   Выполните с помощью диспетчера служб IIS действия, описанные выше, но вместо добавления сертификата или привязки удалите их.  
  
-   Удалите сертификат компьютера с помощью следующей команды.  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
