---
title: Архитектура активации WAS
ms.date: 03/30/2017
ms.assetid: 58aeffb0-8f3f-4b40-80c8-15f3f1652fd3
ms.openlocfilehash: 67ddcd97ac75ddeb0765c38bb9ce7b5e8f039272
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184242"
---
# <a name="was-activation-architecture"></a>Архитектура активации WAS
В настоящем разделе перечисляются и обсуждаются компоненты службы активации процесса Windows (также известной как WAS).  
  
## <a name="activation-components"></a>Компоненты активации  
 Служба WAS состоит из нескольких архитектурных компонентов.  
  
- Адаптеры прослушивателя. Службы Windows, получающие сообщения по определенным сетевым протоколам и взаимодействующие со службой WAS для маршрутизации входящих сообщений к правильным рабочим процессам.  
  
- WAS. Служба Windows, управляющая созданием и временем существования рабочих процессов.  
  
- Универсальный исполняемый файл рабочего процесса (w3wp.exe).  
  
- Диспетчер приложений. Управляет созданием и временем существования доменов приложений, в которых размещаются приложения внутри рабочих процессов.  
  
- Обработчики протоколов. Специфичные для протоколов компоненты, которые запускаются в рабочем процессе и управляют взаимодействием между рабочим процессом и отдельными адаптерами прослушивателя. Существуют обработчики протоколов двух типов: обработчики протоколов процесса и обработчики протоколов домена приложения.  
  
 Когда служба WAS активирует экземпляр рабочего процесса, она загружает требуемые обработчики протоколов процесса в рабочей процесс и использует диспетчер приложения для создания домена приложения, в котором будет размещено это приложение. Домен приложения загружает код приложения, а также обработчики протоколов домена приложения, которые требуются для используемых приложением сетевых протоколов.  
  
 ![Скриншот, который показывает архитектуру WAS.](./media/was-activation-architecture/windows-process-application-service-architecture.gif)  
  
### <a name="listener-adapters"></a>Адаптеры прослушивателя  
 Адаптеры прослушивателя - это отдельные службы Windows, реализующие логику сетевого взаимодействия, используемую для приема сообщений по сетевому протоколу, по которому они ожидают передачи данных. В следующей таблице перечислены адаптеры слушателя для протоколов Windows Communication Foundation (WCF).  
  
|Имя службы адаптера прослушивателя|Протокол|Примечания|  
|-----------------------------------|--------------|-----------|  
|W3SVC|http|Общий компонент, обеспечивающий активацию HTTP как для IIS 7.0, так и для WCF.|  
|NetTcpActivator|net.tcp|Зависит от службы NetTcpPortSharing.|  
|NetPipeActivator|net.pipe||  
|NetMsmqActivator|net.msmq|Для использования с wCF основе сообщения queuing приложений.|  
|NetMsmqActivator|msmq.formatname|Обеспечивает обратную совместимость с существующими приложениями очереди сообщений.|  
  
 Адаптеры прослушивателя для отдельных протоколов регистрируются во время установки в файле applicationHost.config, как показано в следующем примере XML.  
  
```xml  
<system.applicationHost>  
    <listenerAdapters>  
        <add name="http" />  
        <add name="net.tcp"
          identity="S-1-5-80-3579033775-2824656752-1522793541-1960352512-462907086" />  
         <add name="net.pipe"
           identity="S-1-5-80-2943419899-937267781-4189664001-1229628381-3982115073" />  
          <add name="net.msmq"
            identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
           <add name="msmq.formatname"
             identity="S-1-5-80-89244771-1762554971-1007993102-348796144-2203111529" />  
    </listenerAdapters>  
</system.applicationHost>  
```  
  
### <a name="protocol-handlers"></a>Обработчики протоколов  
 Обработчики протоколов процесса и домена приложения для конкретных протоколов регистрируются в файле Web.config на уровне компьютера.  
  
```xml  
<system.web>  
   <protocols>  
      <add name="net.tcp"
        processHandlerType=  
         "System.ServiceModel.WasHosting.TcpProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.TcpAppDomainProtocolHandler"  
        validate="false" />  
      <add name="net.pipe"
        processHandlerType=  
         "System.ServiceModel.WasHosting.NamedPipeProcessProtocolHandler"  
          appDomainHandlerType=  
           "System.ServiceModel.WasHosting.NamedPipeAppDomainProtocolHandler"/>  
      <add name="net.msmq"  
        processHandlerType=  
         "System.ServiceModel.WasHosting.MsmqProcessProtocolHandler"  
        appDomainHandlerType=  
         "System.ServiceModel.WasHosting.MsmqAppDomainProtocolHandler"  
        validate="false" />  
   </protocols>  
</system.web>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Настройка WAS для использования с WCF](../../../../docs/framework/wcf/feature-details/configuring-the-wpa--service-for-use-with-wcf.md)
- [Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))
