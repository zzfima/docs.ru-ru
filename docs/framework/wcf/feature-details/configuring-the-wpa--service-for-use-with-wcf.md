---
title: "Настройка службы активации процессов Windows для использования с Windows Communication Foundation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a63f9a4e982e4065f55b15ec28be5afbf2d89fcc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Настройка службы активации процессов Windows для использования с Windows Communication Foundation
В этом разделе описывается настройка службы активации Windows (WAS) в [!INCLUDE[wv](../../../../includes/wv-md.md)] для размещения служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], обменивающихся данными не по сетевым протоколам HTTP. Настройка предполагает следующие шаги.  
  
-   Установите или проверьте, установлены ли требуемые компоненты активации [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Создайте узел WAS с привязками сетевых протоколов, которые планируется использовать, или добавьте новую привязку протокола в существующий узел.  
  
-   Создайте приложение для размещения служб и разрешите этому приложению использовать требуемые сетевые протоколы.  
  
-   Постройте службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], предоставляющую конечную точку, работающую по отличному от HTTP протоколу.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>Настройка узла с привязками протоколов, отличных от HTTP  
 Для использования в сочетании со службой WAS привязки к протоколу, отличному от HTTP, необходимо добавить привязку узла в конфигурацию WAS. Хранилищем конфигурации для службы WAS является файл applicationHost.config, находящийся в каталоге %windir%\system32\inetsrv\config. Это хранилище конфигурации используется и службой WAS, и службами IIS 7.0.  
  
 applicationHost.config представляет собой текстовый XML-файл, который можно открыть в любом стандартном текстовом редакторе, таком как Блокнот. Тем не менее, для добавления привязок узла к отличным от HTTP протоколам рекомендуется использовать программу настройки [!INCLUDE[iisver](../../../../includes/iisver-md.md)] из командной строки (appcmd.exe).  
  
 Следующая команда добавляет в веб-узел по умолчанию привязку узла к протоколу net.tcp с помощью команды appcmd.exe (вводится как одна строка).  
  
```  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 Эта команда добавляет новую привязку net.tcp в веб-узел по умолчанию путем добавления приведенной ниже строки в файл applicationHost.config.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## <a name="enabling-an-application-to-use-non-http-protocols"></a>Разрешение приложению использовать протоколы, отличные от HTTP  
 Можно включить или отключить отдельные сетевые protocolsat уровне приложения. Следующая команда иллюстрирует включение и протокола HTTP, и протокола net.tcp для приложения, выполняющегося на сайте `Default Web Site`.  
  
```  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 Список разрешенных протоколов также можно задать в \<applicationDefaults > элемент XML-конфигурации сайта, хранящейся в файле ApplicationHost.config.  
  
 Следующий XML-код из файла applicationHost.config иллюстрирует сайт, привязанный и к протоколу HTTP, и к протоколу, отличному от HTTP. Дополнительная конфигурация, необходимая для поддержки отличных от HTTP протоколов, выделена комментариями.  
  
```xml  
<sites>  
    <site name="Default Web Site" id="1">  
    <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
    </application>  
       <bindings>  
            //The following two lines are added by the command.  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile   
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging   
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults   
      applicationPool="DefaultAppPool"   
      //The following line is inserted by the command.  
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 При попытке запустить службу с помощью WAS для активации по протоколу, отличному от HTTP, когда службы WAS не установлены и не настроены, может появиться сообщение об ошибке:  
  
```Output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 Если появилось это сообщение об ошибке, убедитесь, что установлены и правильно настроены службы WAS для активации по протоколу, отличному от HTTP. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Как: Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>Построение службы WCF, использующей WAS для активации по протоколу, отличному от HTTP  
 После выполнения действия по установке и настройке WAS (в разделе [как: Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), Настройка службы необходимо использовать WAS для активации похожа на настройку службы, размещенной в IIS.  
  
 Дополнительные сведения о построении активации WAS [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы см. в разделе [как: размещение службы WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="see-also"></a>См. также  
 [Размещение в службе активации процессов Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)  
 [Функции размещения Windows Server App Fabric](http://go.microsoft.com/fwlink/?LinkId=201276)
