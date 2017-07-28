---
title: "Резидентное размещение | Microsoft Docs"
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
  - "образец резидентного размещения [Windows Communication Foundation]"
  - "резидентная служба"
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
caps.latest.revision: 38
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 38
---
# Резидентное размещение
В этом образце показано, как реализовать резидентную службу в консольном приложения.Данный образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Файл конфигурации приложения был переименован из Web.config в App.config, и в нем был указан базовый адрес, используемый основным приложением.Исходный код службы был изменен, чтобы он реализовывал статическую функцию `Main`, которая создает и открывает узел службы, предоставляющее настроенный базовый адрес.Реализация службы была изменена, чтобы для каждой операции выводить результат на консоль.Клиент остался неизменным, но для него был задан правильный конечный адрес службы.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец реализует статическую функцию main для создания объекта <xref:System.ServiceModel.ServiceHost> для заданного типа `CalculatorService`, как показано в следующем образце кода.  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =   
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners   
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
  
```  
  
 Если служба размещается в службах IIS или службе активации Windows \(WAS\), базовый адрес службы предоставляется средой размещения.В случае резидентного размещения базовый адрес необходимо указывать самостоятельно.Это делается с помощью элемента `add`, дочернего элемента [\<baseAddresses\>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), дочернего элемента [\<хост\>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), дочернего элемента [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md), как показано в следующем образце конфигурации.  
  
```  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окнах консоли как службы, так и клиента.Нажмите клавишу ВВОД в каждом окне консоли, чтобы закрыть службу и клиент.  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## См. также  
 [Образцы размещения и сохраняемости AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)