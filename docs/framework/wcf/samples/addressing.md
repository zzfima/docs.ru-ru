---
title: Адресация
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 4403ac2bf8e0e5193006f6ec19b24a9bcb00bf35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183979"
---
# <a name="addressing"></a>Адресация
В образце адресации показаны различные аспекты и возможности адресов конечных точек. Образец основан на [запущенном.](../../../../docs/framework/wcf/samples/getting-started-sample.md) В этом образце служба является резидентной. Как служба, так и клиент являются консольными приложениями. Служба определяет несколько конечных точек, используя сочетание их относительных и абсолютных адресов.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Представленный ниже файл конфигурации службы задает базовый адрес и четыре конечные точки. Базовый адрес задается с помощью элемента add в каталоге service/host/baseAddresses, как показано в следующем образце конфигурации.  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 В первом определении конечной точки, показанном в следующем образце конфигурации, задается относительный адрес. Это означает, что адрес конечной точки представляет собой сочетание базового и относительного адресов, соответствующее правилам формирования универсального кода ресурса.  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 В этом случае относительный адрес пустой (""), поэтому адрес конечной точки совпадает с базовым адресом. Фактический адрес конечных точек `http://localhost:8000/servicemodelsamples/service`.
  
 Во втором определении конечной точки также задается относительный адрес, как показано в следующем образце конфигурации.  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 Относительный адрес, "test", присоединяется к базовому адресу. Фактический адрес конечных точек `http://localhost:8000/servicemodelsamples/service/test`.
  
 В третьем определении конечной точки задается абсолютный адрес, как показано в следующем образце конфигурации.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 Базовый адрес не играет никакой роли в этом адресе. Фактический адрес конечных точек `http://localhost:8001/hello/servicemodelsamples`.
  
 В четвертом определении конечной точки задаются абсолютный адрес и другой транспорт - TCP. Базовый адрес не играет никакой роли в этом адресе. Фактический адрес конечных точек `net.tcp://localhost:9000/servicemodelsamples/service`.
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</service>  
```  
  
 Клиент связывается только с одной конечной точкой службы из четырех, однако в файле конфигурации заданы все четыре. Клиент выбирает конечную точку при создании объекта `CalculatorProxy`. Изменяя имя файла конфигурации с `CalculatorEndpoint1` по `CalculatorEndpoint4`, можно использовать любую конечную точку.  
  
 При запуске образца служба перечисляет адрес, имя привязки и имя контракта для каждой конечной точки. Конечная точка обмена метаданными (MEX) представляет собой лишь другую конечную точку из перспективы ServiceHost, поэтому она показывается в списке.  
  
```console  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 При запуске клиента запросы и ответы операций отображаются в окнах консоли как службы, так и клиента. Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
    > [!NOTE]
    > Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
