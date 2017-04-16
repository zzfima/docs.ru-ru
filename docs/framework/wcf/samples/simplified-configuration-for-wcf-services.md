---
title: "Упрощенная конфигурация служб WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Упрощенная конфигурация служб WCF
В этом образце демонстрируется, как реализовать и настроить типизированные службы и клиенты с помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Этот образец является основой для всех остальных базовых образцов технологий.  
  
 Эта служба, которая предоставляет конечную точку для взаимодействия со службой, использует упрощенную конфигурацию в [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].До [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] конечная точка определяется в файле конфигурации \(Web.config\). См. следующий пример кода конфигурации.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
  
```  
  
 В [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] элемент `<service>` является необязательным.Если конечные точки не заданы в службе, то к службе добавляется конечная точка для каждого базового адреса и реализованного контракта.Базовый адрес добавляется к имени контракта для определения конечной точки, и привязка определяется с помощью схемы адреса.В следующем примере кода показан файл упрощенной конфигурации.В соответствии с настройкой служба доступна по адресу http:\/\/localhost\/servicemodelsamples\/service.svc для клиента на этом же компьютере.Чтобы к службе могли получить доступ клиенты на удаленных компьютерах, вместо имени localhost необходимо указать полное имя домена.По умолчанию служба не предоставляет метаданных.При этом служба включает поведение <xref:System.ServiceModel.Description.ServiceMetadataBehavior>.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
  
```  
  
### Использование этого образца  
  
1.  Убедитесь, что выполнены действия, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Для построения решения следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Запустите образец, выполнив следующие шаги.  
  
    1.  Щелкните правой кнопкой мыши проект **Служба** и выберите **Назначить запускаемым проектом**, а затем нажмите **Ctrl\+F5**.  
  
    2.  Дождитесь вывода данных на консоли, подтверждающих запуск и выполнение службы.  
  
    3.  Щелкните правой кнопкой мыши проект **Клиент** и выберите **Назначить запускаемым проектом**, а затем нажмите **Ctrl\+F5**.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## См. также  
 [Образцы управления AppFabric](http://go.microsoft.com/fwlink/?LinkId=193960)   
 [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md)