---
title: "Фабрика каналов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# Фабрика каналов
В этом образце показано, как клиентское приложение может создать канал с помощью <xref:System.ServiceModel.ChannelFactory>, вместо использования созданного клиента.Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца расположены в конце этого раздела.  
  
 Чтобы создать канал для конечной точки службы, в этом образце используется класс <xref:System.ServiceModel.ChannelFactory%601>.Обычно, чтобы создать канал для конечной точки, с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) создается тип клиента, а затем создается экземпляр этого типа.Кроме того, канал можно создать с помощью класса <xref:System.ServiceModel.ChannelFactory%601>, как показано в этом образце.Создаваемая с помощью следующего образце кода служба идентична службе, описанной в разделе [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  Если этот образец выполняется на нескольких компьютерах, в предыдущем фрагменте кода необходимо заменить localhost на полное имя компьютера, на котором выполняется служба.В этом образце для задания адреса конечной точки конфигурация не используется, поэтому это необходимо сделать в коде.  
  
 После создания канала можно вызывать операции службы, как это можно было бы делать с помощью созданного клиента.  
  
```  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
 Чтобы закрыть канал, его необходимо сначала привести к интерфейсу <xref:System.ServiceModel.IClientChannel>.Это связано с тем, что канал обычно объявляется в клиентском приложении с помощью интерфейса `ICalculator`, имеющего методы `Add` и `Subtract`, но не имеющего метода `Close`.Метод `Close` наследуется от интерфейса <xref:System.ServiceModel.ICommunicationObject>.  
  
```  
// Close the channel.  
 ((IClientChannel)client).Close();  
  
```  
  
 При выполнении образца запросы и отклики операций отображаются в окне консоли клиента.Чтобы закрыть клиентское приложение, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы выполнить построение версии решения для языка C\# или Visual Basic .NET, воспользуйтесь инструкциями в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).Обратите внимание, что этот в этом образце не включается публикация метаданных.Чтобы заново создать тип клиента, необходимо включить в образце публикацию метаданных.  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, выполните инструкции в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### Запуск образца на нескольких компьютерах  
  
1.  В следующем фрагменте кода замените localhost на полное имя компьютера, на котором выполняется служба.  
  
    ```  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
  
## См. также