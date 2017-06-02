---
title: "Несколько контрактов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Несколько контрактов
В образце нескольких контрактов показано, как реализовать для службы более одного контракта и как настроить конечные точки для взаимодействия с каждым из реализованных контрактов.Этот образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Служба была изменена, чтобы в ней было определено два контракта — контракт `ICalculator` и контракт `ICalculatorSession`.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Класс службы реализует контракты `ICalculator` и `ICalculatorSession`.Поскольку одному из контрактов требуется сеанс, служба использует режим экземпляра <xref:System.ServiceModel.InstanceContextMode> для поддержки состояния в течение времени существования сеанса.  
  
 Конфигурация службы была изменена, чтобы в ней определялось две конечных точки для обоих контрактов.Конечная `ICalculator` точка доступна по базовому адресу с использованием привязки `basicHttpBinding`.Конечная точка `ICalculatorSession` доступна по адресу "базовый\_адрес\/сеанс" с использованием привязки `wsHttpBinding`, атрибут `bindingConfiguration` которой имеет значение `BindingWithSession`, как показано в следующем образце конфигурации.  
  
```  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
  
```  
  
 Теперь созданный код клиента содержит клиентский класс как для исходного контракта `ICalculator`, так и для нового контракта `ICalculatorSession`.Конфигурация и код клиента были изменены, чтобы он мог взаимодействовать с каждым из контрактов через соответствующую конечную точку службы.  
  
 Клиент является консольным приложением Windows \(EXE\).Служба размещается в службах IIS.  
  
 В окне консольного приложения клиента отображаются операции, передаваемые в каждую из конечных точек, сначала для базовой конечной точки, а затем для защищенной конечной точки.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
  
## См. также