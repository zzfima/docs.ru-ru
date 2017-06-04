---
title: "Регулирование | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "поведения служб, образец регулирования"
  - "образец регулирования [Windows Communication Foundation]"
ms.assetid: 40bb3582-8ae9-4410-96f0-6c515bfaf47c
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Регулирование
В образце регулирования демонстрируется использование элементов управления регулированием.Элементы регулирования ограничивают число одновременных вызовов, экземпляров или сеансов, чтобы предотвратить чрезмерное потребление ресурсов.Поведение регулирования задается параметрами файла конфигурации службы.Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Файл конфигурации службы задает элементы управления регулированием в элементе [\<serviceThrottling\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), как показано в следующем образце конфигурации.  
  
```  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Specify throttling behavior -->  
    <serviceThrottling maxConcurrentCalls="2"  
                       maxConcurrentInstances="10"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 В соответствии с конфигурацией служба ограничивает максимальное число параллельных вызовов двумя, а максимальное число параллельных экземпляров десятью.  
  
 Для демонстрации регулирования в методах службы следующим образом определяется время задержки:  
  
```  
public double Add(double n1, double n2)  
{  
    System.Threading.Thread.Sleep(2000);  
    return n1 + n2;  
}  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Методы Add и Subtract выполняются параллельно и методы Multiply и Divide выполняются параллельно, что подтверждает, что параллельно можно выполнять не более двух методов, и является демонстрацией регулирования.  
  
```  
  
Press <ENTER> to terminate client.  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Add Result: 115.99  
Subtract Result: 68.46  
Multiply Result: 731.25  
Divide Result: 3.14285714285714  
  
Press any key to continue . . .  
```  
  
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
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Throttling`  
  
## См. также