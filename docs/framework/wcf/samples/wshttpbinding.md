---
title: "WSHttpBinding | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "привязка WS Profile"
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
caps.latest.revision: 39
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 39
---
# WSHttpBinding
В этом образце показано, как с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] реализовать типовую службу и типовой клиент.Этот образец содержит консольную программу клиента \(client.exe\) и библиотеку службы, размещаемую в службах IIS.Служба реализует контракт, определяющий шаблон взаимодействия "запрос\-ответ".Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции \(сложение, вычитание, умножение и деление\).Клиент осуществляет синхронные вызовы заданной математической операции, а служба отправляет в ответ результат.Действия клиента отображаются в окне консоли.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для этого образца приведены в конце этого раздела.  
  
 Этот образец предоставляет контракт `ICalculator`, используя элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).Конфигурация этой привязки была расширена в файле Web.config.  
  
```  
<bindings>  
  <wsHttpBinding>  
    <!--The following is the expanded configuration section for a-->  
    <!--WSHttpBinding. Each property is configured with the default-->   
    <!--value. See the ReliableSession, TransactionFlow, -->  
    <!--TransportSecurity, and MessageSecurity samples in the WS -->  
    <!--directory to learn how to configure these features. -->  
    <binding name="Binding1"  
              bypassProxyOnLocal="false"   
              transactionFlow="false"   
              hostNameComparisonMode="StrongWildcard"  
              maxBufferPoolSize="524288"   
              maxReceivedMessageSize="65536"  
              messageEncoding="Text"   
              textEncoding="utf-8"   
              useDefaultWebProxy="true"  
              allowCookies="false">  
      <reliableSession ordered="true"   
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Message">  
        <message clientCredentialType="Windows"   
                 negotiateServiceCredential="true"  
                 algorithmSuite="Default"   
                 establishSecurityContext="true" />  
      </security>  
    </binding>  
  </wsHttpBinding>  
</bindings>  
```  
  
 На базе элемента `binding` значение `maxReceivedMessageSize` позволяет задавать максимальный размер входящих сообщений \(в байтах\).Значение `hostNameComparisonMode` позволяет определить, нужно ли при демультиплексировании сообщений для службы учитывать имя узла.Значение `messageEncoding` позволяет задать кодирование сообщений \(текст или MTOM\).Значение `textEncoding` позволяет задать кодировку сообщений.Значение `bypassProxyOnLocal` позволяет задать, нужно ли использовать для локального взаимодействия HTTP\-прокси.Значение `transactionFlow` определяет, передается ли текущая транзакция через поток \(если для операции включен поток транзакций\).  
  
 Логическое значение в элементе [\<reliableSession\>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) определяет, включены ли надежные сеансы.Значение `ordered` определяет, сохраняется ли порядок сообщений.Значение `inactivityTimeout` определяет время, в течение которого сеанс может оставаться в состоянии бездействия, прежде чем он будет прерван.  
  
 В элементе [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) значение `mode` задает используемый режим безопасности.В этом образце используется безопасность сообщений, поэтому задается [\<сообщение\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) в [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md).  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Убедитесь, что выполнена процедура, описанная в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Чтобы создать версию решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также