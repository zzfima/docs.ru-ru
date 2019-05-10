---
title: Настройка службы активации процессов Windows для использования с Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
ms.openlocfilehash: 9fead93fcb8982f4f69af5d4bb401aa731bf887f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654569"
---
# <a name="configuring-the-windows-process-activation-service-for-use-with-windows-communication-foundation"></a>Настройка службы активации процессов Windows для использования с Windows Communication Foundation
В этом разделе описываются шаги, необходимые для настройки службы активации Windows (WAS) в [!INCLUDE[wv](../../../../includes/wv-md.md)] для размещения Windows Communication Foundation (WCF) служб, которые не поддерживают связь по протоколу HTTP сетевые протоколы. Настройка предполагает следующие шаги.  
  
- Установите (или подтвердить установку) требуемые компоненты активации WCF.  
  
- Создайте узел WAS с привязками сетевых протоколов, которые планируется использовать, или добавьте новую привязку протокола в существующий узел.  
  
- Создайте приложение для размещения служб и разрешите этому приложению использовать требуемые сетевые протоколы.  
  
- Создание службы WCF, которая предоставляет конечную точку, отличные от HTTP.  
  
## <a name="configuring-a-site-with-non-http-bindings"></a>Настройка узла с привязками протоколов, отличных от HTTP  
 Для использования в сочетании со службой WAS привязки к протоколу, отличному от HTTP, необходимо добавить привязку узла в конфигурацию WAS. Хранилищем конфигурации для службы WAS является файл applicationHost.config, находящийся в каталоге %windir%\system32\inetsrv\config. Это хранилище конфигурации используется и службой WAS, и службами IIS 7.0.  
  
 applicationHost.config представляет собой текстовый XML-файл, который можно открыть в любом стандартном текстовом редакторе, таком как Блокнот. Тем не менее, для добавления привязок узла к отличным от HTTP протоколам рекомендуется использовать программу настройки [!INCLUDE[iisver](../../../../includes/iisver-md.md)] из командной строки (appcmd.exe).  
  
 Следующая команда добавляет в веб-узел по умолчанию привязку узла к протоколу net.tcp с помощью команды appcmd.exe (вводится как одна строка).  
  
```console  
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
  
```console  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 Список разрешенных протоколов также может задаваться в \<applicationDefaults > элемент конфигурации XML сайта, хранящейся в файле ApplicationHost.config.  
  
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
  
```output  
[InvalidOperationException: The protocol 'net.tcp' does not have an implementation of HostedTransportConfiguration type registered.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult result) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 Если появилось это сообщение об ошибке, убедитесь, что установлены и правильно настроены службы WAS для активации по протоколу, отличному от HTTP. Дополнительные сведения см. в разделе [Как Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
## <a name="building-a-wcf-service-that-uses-was-for-non-http-activation"></a>Построение службы WCF, использующей WAS для активации по протоколу, отличному от HTTP  
 После выполнения действия по установке и настройке WAS (см. в разделе [как: Установка и настройка компонентов активации WCF](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md)), Настройка службы для использования WAS для активации производится аналогично настройке службы, размещенной в IIS.  
  
 Подробные инструкции по построению службы WCF активации WAS см. в разделе [как: Размещение службы WCF в WAS](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md).  
  
## <a name="see-also"></a>См. также

- [Размещение в службе активации процессов Windows](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)
- [Функции размещения Windows Server App Fabric](https://go.microsoft.com/fwlink/?LinkId=201276)
