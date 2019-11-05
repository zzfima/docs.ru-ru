---
title: Поставщик WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: dd24a6d270a0bd9012bbda2a53913167c9697bc5
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424511"
---
# <a name="wmi-provider"></a>Поставщик WMI
В этом примере показано, как собирать данные из служб Windows Communication Foundation (WCF) во время выполнения с помощью поставщика инструментарий управления Windows (WMI) (WMI), встроенного в WCF. Кроме того, в образце показано, как добавлять в службу пользовательский объект инструментария WMI. В примере активируется поставщик WMI для [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и демонстрируется сбор данных из `ICalculator` службы во время выполнения.  
  
 Инструментарий WMI - это реализованный корпорацией Майкрософт стандарт управления предприятием через Интернет (WBEM). Дополнительные сведения о пакете SDK для инструментария WMI см. в разделе [инструментарий управления Windows (WMI)](/windows/desktop/WmiSdk/wmi-start-page). WBEM является отраслевым стандартом предоставления приложениями инструментария управления для внешних средств управления.  
  
 WCF реализует поставщик WMI, компонент, который предоставляет инструментирование во время выполнения через интерфейс, совместимый с WBEM. Средства управления могут подключаться к службам через интерфейс во время выполнения. WCF предоставляет атрибуты служб, такие как адреса, привязки, поведения и прослушиватели.  
  
 Встроенный поставщик инструментария WMI активируется в файле конфигурации приложения. Это выполняется с помощью атрибута `wmiProviderEnabled` [диагностики\<](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) в разделе [\<system. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , как показано в следующем образце конфигурации:  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 Эта запись конфигурации предоставляет интерфейс инструментария WMI. Теперь приложения управления могут подключаться через этот интерфейс и обращаться к инструментарию управления приложения.  
  
## <a name="custom-wmi-object"></a>Пользовательский объект WMI  
 Добавление в службу объектов WMI позволяет предоставлять доступ к пользовательским сведениям, а также к сведениям встроенного поставщика WMI. Для этого необходимо опубликовать схему службы в инструментарии WMI с помощью приложения Installutil.exe. Соответствующие инструкции, а также более подробные сведения, см в инструкция по установке в конце этого раздела.  
  
## <a name="accessing-wmi-information"></a>Доступ к сведениям WMI  
 Доступ к данным инструментария WMI может осуществляться несколькими различными способами. Корпорация Майкрософт предоставляет API-интерфейсы WMI для сценариев, C++ Visual Basic приложений, приложений и .NET Framework (https://docs.microsoft.com/windows/desktop/wmisdk/using-wmi).  
  
 В этом образце используется два скрипта Java: один - для перечисления выполняющихся на компьютере служб и некоторых их свойств, а второй - для просмотра пользовательских данных инструментария WMI. Скрипт открывает подключение к поставщику инструментария WMI, анализирует данные и отображает собранные данные.  
  
 Запустите пример, чтобы создать запущенный экземпляр службы WCF. Во время работы службы выполните каждый из скриптов Java с помощью следующей команды командной строки:  
  
```console  
cscript EnumerateServices.js  
```  
  
 Этот скрипт обращается к хранящемуся в службе инструментированию и создает следующий результат:  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 Затем выполните второй скрипт Java, чтобы отобразить пользовательские данные WMI:  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 Этот скрипт обращается к хранящемуся в службах пользовательскому инструментированию и создает следующий результат:  
  
```console 
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 Сценарий показывает, что на компьютере запущена одна служба. Служба предоставляет одну конечную точку, реализующую контракт `ICalculator`. Параметры поведения и привязки, реализуемых конечной точкой, задаются в виде отдельных элементов стека обмена сообщениями.  
  
 Инструментарий WMI не ограничивается предоставлением инструментария управления инфраструктуры WCF. Приложение может предоставлять собственные относящиеся к домену элементы данных, используя для этого такой же механизм. Инструментарий WMI представляет собой единый механизм для контроля веб-службы и управления ею.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Опубликуйте схему служб в WMI, запустив программу InstallUtil.exe (по умолчанию файл InstallUtil.exe расположен в папке «%WINDIR%\Microsoft.NET\Framework\v4.0.30319») для файла service.dll в каталоге размещения. Эту операцию нужно выполнять только в том случае, если в файл service.dll были внесены изменения.
  
4. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    > Если вы установили WCF после установки ASP.NET, может потребоваться выполнить команду "% WINDIR% \ Microsoft. Net\Framework\v3.0\Windows Communication Фаундатион\сервицемоделрег.ЕКСЕ "-r-x предоставляет учетной записи ASPNET разрешение на публикацию объектов WMI.  
  
5. Для просмотра данных из образцов, доступных через WMI, следует воспользоваться командами: `cscript EnumerateServices.js` или `cscript EnumerateCustomObjects.js`.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a>См. также

- [Примеры мониторинга AppFabric](https://go.microsoft.com/fwlink/?LinkId=193959)
