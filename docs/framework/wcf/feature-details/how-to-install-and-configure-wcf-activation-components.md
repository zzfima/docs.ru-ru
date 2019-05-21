---
title: Практическое руководство. Установка и настройка компонентов активации WCF
ms.date: 03/30/2017
helpviewer_keywords:
- HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
ms.openlocfilehash: 953df285d1a439cd8a1a95358915a7a50e98552a
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960103"
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Практическое руководство. Установка и настройка компонентов активации WCF
В этом разделе описываются шаги, необходимые для настройки службы активации Windows (WAS) на [!INCLUDE[wv](../../../../includes/wv-md.md)] для размещения Windows Communication Foundation (WCF) служб, которые не поддерживают связь по протоколу HTTP сетевые протоколы. Настройка предполагает следующие шаги.  
  
- Установите (или подтвердить установку) компонентов активации WCF.  
  
- Настройте WAS на поддержку отличных от HTTP протоколов. Выполнение описанных ниже действий позволяет настроить [!INCLUDE[wv](../../../../includes/wv-md.md)] для активации TCP.  
  
 После установки и настройки WAS, см. в разделе [как: Размещение службы WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) для процедуры создания службы WCF, которая предоставляет конечную точку, отличные от HTTP, использующую WAS.  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a>Установка компонентов активации WCF, работающих по отличному от HTTP протоколу  
  
1. Нажмите кнопку **запустить** , а затем нажмите кнопку **панели управления**.  
  
2. Нажмите кнопку **программы**, а затем нажмите кнопку **программы и компоненты**.  
  
3. На **задачи** меню, щелкните **или отключение компонентов Windows включить**.  
  
4. Найдите узел WinFX, выберите и разверните его.  
  
5. Выберите **компонентов активации WCF не-Http** поле и сохранить настройки.  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a>Настройка WAS на поддержку протокола TCP  
  
1. Для поддержки активации по net.tcp веб-узел по умолчанию необходимо сначала привязать к порту net.tcp. Сделать это позволяет файл Appcmd.exe, который устанавливается с помощью набора инструментов управления [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. В окне командной строки с правами администратора выполните следующую команду.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста. Она добавляет привязку узла к протоколу net.tcp в веб-узел по умолчанию, ожидающему передачи данных по протоколу TCP на порту 808 с любым именем узла.  
  
2. Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно. Для включения протокола net.tcp для данного приложения необходимо выполнить следующую команду из командной строки с правами администратора.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста. Эта команда включает /\<*приложения WCF*> осуществлять доступ к использование обеих `http://localhost/<WCF Application>` и `net.tcp://localhost/<WCF Application>`.
  
     Удалите привязку сайта к протоколу net.tcp, добавленную ранее для данного образца.  
  
     Для удобства два нижеописанных действия выполняются в пакетом файле RemoveNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.  
  
    1. Удалите протокол net.tcp из списка разрешенных протоколов, выполнив следующую команду в окне командной строки с правами администратора.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Эта команда представляет собой одну строку текста.  
  
    2. Удалите привязку узла к протоколу net.tcp, выполнив следующую команду в окне командной строки с повышенными привилегиями:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Эта команда представляет собой одну строку текста.  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>Удаление протокола net.tcp из списка разрешенных протоколов  
  
1. Для того чтобы удалить протокол net.tcp из списка разрешенных протоколов, необходимо выполнить следующую команду в окне командной строки с правами администратора.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.  
  
### <a name="to-remove-the-nettcp-site-binding"></a>Удаление привязки узла к протоколу net.tcp  
  
1. Для того чтобы удалить привязку узла к протоколу net.tcp, необходимо выполнить следующую команду в окне командной строки с правами администратора:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.  
  
## <a name="see-also"></a>См. также

- [Активация TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)
- [Активация MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)
- [Активация NamedPipe](../../../../docs/framework/wcf/samples/namedpipe-activation.md)
- [Функции размещения Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201276)
