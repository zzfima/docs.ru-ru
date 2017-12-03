---
title: "Практическое руководство. Установка и настройка компонентов активации WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: HTTP activation [WCF]
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ee57276efda7edcc464c300e2f1d100b6a7c9109
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-install-and-configure-wcf-activation-components"></a>Практическое руководство. Установка и настройка компонентов активации WCF
В этом разделе описывается настройка службы активации Windows (WAS) в [!INCLUDE[wv](../../../../includes/wv-md.md)] для размещения служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], обменивающихся данными не по сетевым протоколам HTTP. Настройка предполагает следующие шаги.  
  
-   Установите или проверьте, установлены ли компоненты активации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Настройте WAS на поддержку отличных от HTTP протоколов. Выполнение описанных ниже действий позволяет настроить [!INCLUDE[wv](../../../../includes/wv-md.md)] для активации TCP.  
  
 После установки и настройки WAS, в разделе [как: размещение службы WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md) для процедуры создания [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы, предоставляющей конечную точку отличные от HTTP, которая использует WAS.  
  
### <a name="to-install-the-wcf-non-http-activation-components"></a>Установка компонентов активации WCF, работающих по отличному от HTTP протоколу  
  
1.  Нажмите кнопку **запустить** , а затем нажмите **панели управления**.  
  
2.  Нажмите кнопку **программы**, а затем нажмите кнопку **программы и компоненты**.  
  
3.  На **задачи** меню, нажмите кнопку **Включение или отключение компонентов**.  
  
4.  Найдите узел [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], затем выберите и разверните его.  
  
5.  Выберите **компоненты активации WCF не-Http** и сохраните параметр.  
  
### <a name="to-configure-the-was-to-support-tcp-activation"></a>Настройка WAS на поддержку протокола TCP  
  
1.  Для поддержки активации по net.tcp веб-узел по умолчанию необходимо сначала привязать к порту net.tcp. Сделать это позволяет файл Appcmd.exe, который устанавливается с помощью набора инструментов управления [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. В окне командной строки с правами администратора выполните следующую команду.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста. Она добавляет привязку узла к протоколу net.tcp в веб-узел по умолчанию, ожидающему передачи данных по протоколу TCP на порту 808 с любым именем узла.  
  
2.  Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно. Для включения протокола net.tcp для данного приложения необходимо выполнить следующую команду из командной строки с правами администратора.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста. Эта команда включает /\<*приложения WCF*> приложение было доступно с помощью обоих http://localhost*/\<приложения WCF >* и net.tcp:// localhost /*\<приложения WCF >*.  
  
     Удалите привязку сайта к протоколу net.tcp, добавленную ранее для данного образца.  
  
     Для удобства два нижеописанных действия выполняются в пакетом файле RemoveNetTcpSiteBinding.cmd, расположенном в каталоге с образцами.  
  
    1.  Удалите протокол net.tcp из списка разрешенных протоколов, выполнив следующую команду в окне командной строки с правами администратора.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Эта команда представляет собой одну строку текста.  
  
    2.  Удалите привязку узла к протоколу net.tcp, выполнив следующую команду в окне командной строки с повышенными привилегиями:  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  Эта команда представляет собой одну строку текста.  
  
### <a name="to-remove-nettcp-from-the-list-of-enabled-protocols"></a>Удаление протокола net.tcp из списка разрешенных протоколов  
  
1.  Для того чтобы удалить протокол net.tcp из списка разрешенных протоколов, необходимо выполнить следующую команду в окне командной строки с правами администратора.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.  
  
### <a name="to-remove-the-nettcp-site-binding"></a>Удаление привязки узла к протоколу net.tcp  
  
1.  Для того чтобы удалить привязку узла к протоколу net.tcp, необходимо выполнить следующую команду в окне командной строки с правами администратора:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.  
  
## <a name="see-also"></a>См. также  
 [Активация TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)  
 [Активация MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)  
 [Активация NamedPipe](../../../../docs/framework/wcf/samples/namedpipe-activation.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
