---
title: WSHttpBinding
ms.date: 03/30/2017
helpviewer_keywords:
- WS Profile binding
ms.assetid: 22d85b19-0135-4141-9179-a0e9c343ad73
ms.openlocfilehash: 6ea07f206064a389da8af04a4afd292022b8ca44
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714559"
---
# <a name="wshttpbinding"></a>WSHttpBinding
В этом примере демонстрируется реализация типичной службы и стандартного клиента с помощью Windows Communication Foundation (WCF). Этот образец содержит консольную программу клиента (client.exe) и библиотеку службы, размещаемую в службах IIS. Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление). Клиент осуществляет синхронные вызовы заданной математической операции, а служба отправляет в ответ результат. Действия клиента отображаются в окне консоли.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsHttp`  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец предоставляет `ICalculator` контракт с помощью [\<WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). Конфигурация этой привязки была расширена в файле Web.config.  
  
```xml
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
  
 На базе элемента `binding` значение `maxReceivedMessageSize` позволяет задавать максимальный размер входящих сообщений (в байтах). Значение `hostNameComparisonMode` позволяет определить, нужно ли при демультиплексировании сообщений для службы учитывать имя узла. Значение `messageEncoding` позволяет задать кодирование сообщений (текст или MTOM). Значение `textEncoding` позволяет задать кодировку сообщений. Значение `bypassProxyOnLocal` позволяет задать, нужно ли использовать для локального взаимодействия HTTP-прокси. Значение `transactionFlow` определяет, передается ли текущая транзакция через поток (если для операции включен поток транзакций).  
  
 В элементе [\<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) включенное логическое значение определяет, включены ли надежные сеансы. Значение `ordered` определяет, сохраняется ли порядок сообщений. Значение `inactivityTimeout` определяет время, в течение которого сеанс может оставаться в состоянии бездействия, прежде чем он будет прерван.  
  
 В [\<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)`mode` значение определяет режим безопасности, который следует использовать. В этом примере используется безопасность сообщений, поэтому в [\<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)задается [сообщение\<](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) .  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Установите ASP.NET 4,0 с помощью следующей команды.  
  
    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
