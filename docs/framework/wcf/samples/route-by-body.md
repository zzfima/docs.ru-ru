---
title: "Маршрутизация по тексту сообщения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# Маршрутизация по тексту сообщения
В этом образце показано, как реализовать службу, которая принимает объекты сообщений с действием SOAP.Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.Служба реализует одну операцию `Calculate`, которая принимает параметр запроса <xref:System.ServiceModel.Channels.Message> и возвращает ответ <xref:System.ServiceModel.Channels.Message>.  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца расположены в конце этого раздела.  
  
 Этот образец демонстрирует диспетчеризацию сообщений на основе содержимого тела сообщения.Встроенный механизм диспетчеризации сообщений модели службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] основан на параметрах Action сообщений.Однако есть много существующих веб\-служб, которые для всех своих операций определяют параметр Action\="".Невозможно построить службу на основе кода WSDL, когда диспетчеризация сообщений запросов осуществляется на основе параметра Action.В этом образце показан контракт службы, основанный на коде WSDL \(код WSDL содержится в файле Service.wsdl, который входит в этот образец\).Контракт службы — Calculator, он аналогичен контракту, используемому в образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).Однако контракт `[OperationContract]` задает для всех операций `Action=""`.  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),    
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
  
```  
  
 Чтобы при таком контракте можно было распределять сообщения между операциями, службе требуется пользовательское поведение диспетчеризации `DispatchByBodyBehavior`.Эта характеристика отправки инициализирует пользовательский селектор операций `DispatchByBodyElementOperationSelector`  при помощи таблицы имен операций, обозначенных с помощью значений QName соответствующих элементов оболочек.Операция `DispatchByBodyElementOperationSelector` проверяет начальный тег первого дочернего элемента Body и выбирает операцию, используя ранее упомянутую таблицу.  
  
 Клиент использует прокси, автоматически созданный на базе кода WSDL, экспортированного службой с помощью средства [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 Тот факт, что параметры Action всех операций пусты, не влияет на клиентский код, не считая параметров Action автоматически созданного прокси.  
  
 Клиентский код выполняет несколько вычислений.При выполнении образца запросы и отклики операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы выполнить построение решения, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
  
## См. также