---
title: Сохраняемый дуплекс
ms.date: 03/30/2017
ms.assetid: 4e76d1a1-f3d8-4a0f-8746-4a322cdff6eb
ms.openlocfilehash: 3df5ba962ef33594df1eaebc20789fa9e2d35244
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="durable-duplex"></a>Сохраняемый дуплекс
В этом примере показано, как установить и настроить устойчивый дуплексный обмен сообщениями с помощью действий обмена сообщениями в Windows Workflow Foundation (WF). Устойчивый дуплексный обмен сообщениями - это двусторонний обмен сообщениями в течение длительного времени. Длительность обмена сообщениями может превышать время существования коммуникационного канала и время существования экземпляров службы в памяти.  
  
## <a name="sample-details"></a>Подробные сведения об образце  
 В этом примере две службы Windows Communication Foundation (WCF), реализованный с помощью Windows Workflow Foundation настраиваются иметь устойчивый дуплексный обмен сообщениями. Устойчивый дуплексный обмен сообщениями состоит из двух односторонних обменов сообщениями по MSMQ, сопоставляются с помощью [обмен контекстом .NET](http://go.microsoft.com/fwlink/?LinkID=166059). Сообщения отправляются посредством действий по обмену сообщениями <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.Receive>. Обмен контекстом .NET используется для указания адреса обратного вызова в отправленных сообщениях. Обе службы размещаются при помощи служб активации процессов Windows WAS и настраиваются на включение сохраняемости экземпляров служб.  
  
 Первая служба (Service1.xamlx) отправляет в службу отправки (Service2.xamlx) запрос на выполнение задания. После выполнения задания служба Service2.xamlx уведомляет об этом службу Service1.xamlx. Приложение командной строки рабочего процесса настраивает прослушиваемые службами очереди и отправляет исходное сообщение "Start", активирующее службу Service1.xamlx. Получив уведомление о выполнения задания от службы Service2.xamlx, служба Service1.xamlx сохраняет результат в виде XML-файла. В ожидании сообщения обратного вызова служба Service1.xamlx сохраняет состояние своего экземпляра при помощи <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> по умолчанию. Служба Service1.xamlx сохраняет состояние своего экземпляра при завершении задания, выполнение которого запрошено службой Service1.xamlx.  
  
 Чтобы обе службы могли использовать обмен контекстом .NET по MSMQ, они настраиваются на использование пользовательской привязки, состоящей из элементов <xref:System.ServiceModel.Channels.ContextBindingElement> и <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>. При помощи элемента <xref:System.ServiceModel.Channels.ContextBindingElement> задается адрес обратного вызова, включаемый в соответствующий заголовок всех сообщений, отправляемых при помощи пользовательской привязки. Пользовательская привязка определяется в следующем примере кода.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          …  
          <bindings>  
               <customBinding>  
                    <binding name="netMsmqContextBinding">  
                         <context clientCallbackAddress="net.msmq://localhost/private/DurableDuplex/Service1.xamlx"/>  
                         <msmqTransport exactlyOnce="False">  
                              <msmqTransportSecurity msmqAuthenticationMode="None" msmqProtectionLevel="None"/>  
                         </msmqTransport>  
                    </binding>  
               </customBinding>  
          </bindings>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  Такая привязка не безопасна. При развертывании приложения следует настроить пользовательскую привязку, исходя из требований к безопасности приложения.  
  
> [!NOTE]
>  Используемые в данном образце очереди не являются транзакционными. Пример, в котором показано, как настроить обмен сообщениями WCF, с использованием очередей транзакции, в разделе [активации MSMQ](../../../../docs/framework/wcf/samples/msmq-activation.md) образца.  
  
 Сообщение от службы Service1.xamlx службе Service2.xamlx отправляется через конечную точку клиента, настроенную на адрес службы Service2.xamlx и на определенную ранее пользовательскую привязку. Обратный вызов от Service2.xamlx службе Service1.xamlx отправляется через конечную точку клиента, не настроенную явно на адрес, так как адрес получается из контекста обратного вызова, отправленного службой Service1.xamlx. Конечные точки клиента определяются в следующем примере кода.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
     <system.serviceModel>  
          …  
          <client>  
               <endpoint address="net.msmq://localhost/private/DurableDuplex/Service2.xamlx" binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="IDoWork"/>  
               <endpoint binding="customBinding" bindingConfiguration="netMsmqContextBinding" contract="INotify"/>  
          </client>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 В следующем примере кода конечные точки, использующие данную пользовательскую привязку, предоставляются посредством изменения стандартного сопоставления протокола для базовых адресов net.msmq, которые будут использовать данную пользовательскую привязку.  
  
```xml  
<configuration>  
     <system.serviceModel>  
          <protocolMapping>  
               <add scheme="net.msmq" binding="customBinding" bindingConfiguration="netMsmqContextBinding"/>  
          </protocolMapping>  
          …  
     </system.serviceModel>  
</configuration>  
```  
  
 В следующем примере кода активируется сохраняемость для обеих служб путем добавления к ним поведения <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> и указания строки подключения к базе данных сохраняемости.  
  
```xml  
<?xml version="1.0"?>  
<configuration>  
    <system.serviceModel>  
          …  
          <behaviors>  
               <serviceBehaviors>  
                    <behavior>  
                         <serviceDebug includeExceptionDetailInFaults="True"/>  
                         <serviceMetadata httpGetEnabled="True"/>  
                         <sqlWorkflowInstanceStore connectionString="Data Source=.\SQLEXPRESS;Initial Catalog=DefaultSampleStore;Integrated Security=True"/>  
                    </behavior>  
               </serviceBehaviors>  
          </behaviors>  
     </system.serviceModel>  
</configuration>  
```  
  
## <a name="system-requirements"></a>Требования к системе  
 Для данного образца требуются следующие компоненты.  
  
1.  Службы IIS.  
  
2.  Службы IIS -> Совместимость управления IIS 6.0 -> Метабаза IIS и совместимость конфигурации IIS 6.0.  
  
3.  Веб-службы -> Компоненты разработки приложений -> ASP.NET.  
  
4.  Сервер очереди сообщений (Майкрософт) (MSMQ).  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Настройте базы данных сохраняемости и каталог результатов.  
  
    1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Перейдите в каталог образцов и запустите команду Setup.cmd.  
  
2.  Настройте виртуальное приложение.  
  
    1.  Введите в командной строке [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] следующую команду, чтобы зарегистрировать ASP.NET.  
  
        ```  
        aspnet_regiis -i  
        ```  
  
    2.  Запустите [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] с разрешениями администратора, щелкнув правой кнопкой мыши [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и выбрав **Запуск от имени администратора**.  
  
    3.  Откройте в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] файл DurableDuplex.sln.  
  
3.  Настройте очереди обслуживания.  
  
    1.  Чтобы запустить клиент DurableDuplex, нажмите кнопку F5.  
  
    2.  Откройте **Управление компьютером** консоли, выполнив `Compmgmt.msc` из командной строки.  
  
    3.  Разверните **службы и приложения**, **очереди сообщений**. **Частные очереди**.  
  
    4.  Щелкните правой кнопкой мыши очереди durableduplex/service1.xamlx и durableduplex/service2.xamlx и выберите **свойства**.  
  
    5.  Выберите **безопасности** вкладку и разрешить **получение сообщения**, **Просмотр сообщения** и **Отправка сообщения** обоим очередям права.  
  
    6.  Откройте диспетчер служб IIS.  
  
    7.  Перейдите к **сервера**, **сайтов**, **по умолчанию веб-сайт**, **закрытый**, **устойчивый дуплекс** и выберите пункт **Дополнительные параметры**.  
  
    8.  Изменение **включенные протоколы** для **http,net.msmq**.  
  
4.  Выполните образец.  
  
    1.  Перейдите к http://localhost/private/durableduplex/service1.xamlx и http://localhost/private/durableduplex/service2.xamlx чтобы убедиться, что оба они работают.  
  
    2.  Чтобы запустить DurableDuplexClient, нажмите кнопку F5.  
  
         По завершению устойчивого дуплексного обмена сообщениями в каталоге C:\Inbox сохраняется файл result.xml с результатами обмена.  
  
#### <a name="to-cleanup-optional"></a>Очистка (необязательно)  
  
1.  Запустите команду Cleanup.cmd.  
  
    1.  Откройте командную строку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Перейдите в каталог образцов и запустите команду Cleanup.cmd.  
  
2.  Удалите виртуальное приложение служб.  
  
    1.  Откройте диспетчер Internet Information Services (IIS), запустив `Inetmgr.exe` из командной строки.  
  
    2.  Перейдите на веб-сайт по умолчанию и удалить **закрытый** виртуального каталога.  
  
3.  Удалите заданные для данного образца очереди.  
  
    1.  Откройте консоль управления компьютером, запустив `Compmgmt.msc` из командной строки.  
  
    2.  Разверните **службы и приложения**, **очереди сообщений**, **частные очереди**.  
  
    3.  Удалите очереди durableduplex/service1.xamlx и durableduplex/service2.xamlx.  
  
4.  Удалите каталог C:\Inbox.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\DurableDuplex`