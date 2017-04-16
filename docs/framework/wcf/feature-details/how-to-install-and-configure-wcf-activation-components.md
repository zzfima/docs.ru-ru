---
title: "Как устанавливать и настраивать компоненты активации WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "активация по HTTP [WCF]"
ms.assetid: 33a7054a-73ec-464d-83e5-b203aeded658
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Как устанавливать и настраивать компоненты активации WCF
В этом разделе описывается настройка службы активации Windows \(WAS\) в [!INCLUDE[wv](../../../../includes/wv-md.md)] для размещения служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], обменивающихся данными не по сетевым протоколам HTTP.Настройка предполагает следующие шаги.  
  
-   Установите или проверьте, установлены ли компоненты активации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Настройте WAS на поддержку отличных от HTTP протоколов.Выполнение описанных ниже действий позволяет настроить [!INCLUDE[wv](../../../../includes/wv-md.md)] для активации TCP.  
  
 После установки и настройки WAS см. описание процедуры создания службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], которая предоставляет конечную точку, работающую по отличному от HTTP протоколу и использующую WAS, в разделе [Как разместить службу WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
### Установка компонентов активации WCF, работающих по отличному от HTTP протоколу  
  
1.  Нажмите кнопку **Пуск** и выберите пункт **Панель управления**.  
  
2.  Выберите **Программы**, а затем щелкните **Программы и компоненты**.  
  
3.  В меню **Задачи** щелкните команду **Включение или отключение компонентов Windows**.  
  
4.  Найдите узел [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)], затем выберите и разверните его.  
  
5.  Установите флажок в поле **Компоненты активации WCF, работающие по отличному от Http протоколу** и сохраните параметр.  
  
### Настройка WAS на поддержку протокола TCP  
  
1.  Веб\-узел по умолчанию может поддерживать активацию по net.tcp только в том случае, если он изначально был привязан к порту net.tcp.Сделать это позволяет файл Appcmd.exe, который устанавливается с помощью набора инструментов управления [!INCLUDE[iisver](../../../../includes/iisver-md.md)].В окне командной строки с правами администратора выполните следующую команду.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.Она добавляет привязку узла к протоколу net.tcp в веб\-узел по умолчанию, ожидающему передачи данных по протоколу TCP на порту 808 с любым именем узла.  
  
2.  Несмотря на то что все приложения в узле имеют общую привязку к протоколу net.tcp, включать поддержку net.tcp можно для каждого приложения отдельно.Для включения протокола net.tcp для данного приложения необходимо выполнить следующую команду из командной строки с правами администратора.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app   
    "Default Web Site/<WCF Application>" /enabledProtocols:http,net.tcp  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.Она позволяет осуществлять доступ к \/\<*WCF Application*\> по адресу http:\/\/localhost*\/\<WCF Application\>* или net.tcp:\/\/localhost\/*\<WCF Application\>*.  
  
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
  
### Удаление протокола net.tcp из списка разрешенных протоколов  
  
1.  Для того чтобы удалить протокол net.tcp из списка разрешенных протоколов, необходимо выполнить следующую команду в окне командной строки с правами администратора.  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples<WCF Application>" " /enabledProtocols:http  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.  
  
### Удаление привязки узла к протоколу net.tcp  
  
1.  Для того чтобы удалить привязку узла к протоколу net.tcp, необходимо выполнить следующую команду в окне командной строки с правами администратора:  
  
    ```  
    %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
    -bindings.[protocol='net.tcp',bindingInformation='808:*']  
    ```  
  
    > [!NOTE]
    >  Эта команда представляет собой одну строку текста.  
  
## См. также  
 [Активация TCP](../../../../docs/framework/wcf/samples/tcp-activation.md)   
 [Активация MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md)   
 [Активация NamedPipe](../../../../docs/framework/wcf/samples/namedpipe-activation.md)   
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)