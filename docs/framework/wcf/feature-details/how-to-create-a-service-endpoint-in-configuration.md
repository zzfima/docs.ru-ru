---
title: Практическое руководство. Создание конечной точки службы в конфигурации
ms.custom: ''
ms.date: 06/16/2016
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f474e25d-2a27-4f31-84c5-395c442b8e70
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ecb7345dbbff04388edb39dae9e5c05f2c40fd75
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-create-a-service-endpoint-in-configuration"></a>Практическое руководство. Создание конечной точки службы в конфигурации
Конечные точки предоставляют клиентам доступ к функциональным возможностям службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Можно определить одну или несколько конечных точек для службы, используя сочетание относительных и абсолютных адресов конечных точек. Если же не определять конечные точки службы, среда выполнения автоматически создаст несколько точек по умолчанию. В этом разделе показано, как добавить конечные точки, используя файл конфигурации, который содержит и относительные, и абсолютные адреса.  
  
## <a name="example"></a>Пример  
 Представленная ниже конфигурация службы задает базовый адрес и пять конечных точек.  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <services>  
    <!-- This section is optional with the default configuration introduced  
         in .NET Framework 4. -->  
      <service  
          name="Microsoft.ServiceModel.Samples.CalculatorService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="/test"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="http://localhost:8001/hello/servicemodelsamples"  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
                  binding="netTcpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is another relative address exposed at   
             http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```  
  
## <a name="example"></a>Пример  
 Базовый адрес задается с помощью элемента `add` в каталоге service/host/baseAddresses, как показано в следующем примере.  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
```  
  
## <a name="example"></a>Пример  
 В первом определении конечной точки, показанном в следующем образце, задается относительный адрес. Это означает, что адрес конечной точки представляет собой сочетание базового и относительного адресов, соответствующее правилам формирования универсального кода ресурса (URI). Относительный адрес пустой (""), поэтому адрес конечной точки совпадает с базовым адресом. Фактический адрес конечной точки http://localhost:8000/servicemodelsamples/service.  
  
```xml  
<endpoint address=""   
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Пример  
 Во втором определении конечной точки также задается относительный адрес, как показано в следующем образце конфигурации. Относительный адрес, "test", присоединяется к базовому адресу. Фактический адрес конечной точки http://localhost:8000/servicemodelsamples/service/test.  
  
```xml  
<endpoint address="/test"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Пример  
 В третьем определении конечной точки задается абсолютный адрес, как показано в следующем образце конфигурации. Базовый адрес не играет никакой роли в этом адресе. Фактический адрес конечной точки http://localhost:8001/hello/servicemodelsamples.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
    binding="wsHttpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Пример  
 В четвертом определении конечной точки задаются абсолютный адрес и другой транспорт - TCP. Базовый адрес не играет никакой роли в этом адресе. Фактический адрес конечной точки — net.tcp://localhost:9000/servicemodelsamples/service.  
  
```xml  
<endpoint address="net.tcp://localhost:9000/servicemodelsamples/service"  
    binding="netTcpBinding"  
    contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
## <a name="example"></a>Пример  
 Чтобы использовать конечные точки по умолчанию, предоставляемые средой выполнения, не указывайте конечные точки службы ни в коде, ни в файле конфигурации. В этом примере среда выполнения при открытии службы создает конечные точки по умолчанию. Дополнительные сведения о конечных точек по умолчанию, привязок и поведений см. в разделе [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md) и [упрощенной конфигурации для служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
```xml  
<configuration>  
  
  <appSettings>  
    <!-- use appSetting to configure base address provided by host -->  
    <add key="baseAddress" value="http://localhost:8000/servicemodelsamples/service" />  
  </appSettings>  
  
  <system.serviceModel>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
  
</configuration>  
```
