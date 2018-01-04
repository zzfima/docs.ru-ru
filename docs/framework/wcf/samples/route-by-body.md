---
title: "Маршрутизация по телу сообщения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: defd3a3e9df273739aaf3440fd34fad2cad44cd4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="route-by-body"></a>Маршрутизация по телу сообщения
В этом образце показано, как реализовать службу, которая принимает объекты сообщений с действием SOAP. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора. Служба реализует одну операцию `Calculate`, которая принимает параметр запроса <xref:System.ServiceModel.Channels.Message> и возвращает ответ <xref:System.ServiceModel.Channels.Message>.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец демонстрирует диспетчеризацию сообщений на основе содержимого тела сообщения. Встроенный механизм диспетчеризации сообщений модели службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] основан на параметрах Action сообщений. Однако есть много существующих веб-служб, которые для всех своих операций определяют параметр Action="". Невозможно построить службу на основе кода WSDL, когда диспетчеризация сообщений запросов осуществляется на основе параметра Action. В этом образце показан контракт службы, основанный на коде WSDL (код WSDL содержится в файле Service.wsdl, который входит в этот образец). Контракт службы-калькулятора, похожий на тот, который используется в [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md). Однако контракт `[OperationContract]` задает для всех операций `Action=""`.  
  
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
  
 Чтобы при таком контракте можно было распределять сообщения между операциями, службе требуется пользовательское поведение диспетчеризации `DispatchByBodyBehavior`. Это поведение отправки инициализирует `DispatchByBodyElementOperationSelector` настраиваемый селектор операций с помощью таблицы имен операций, ключом которого является QName соответствующих элементов оболочек. Операция `DispatchByBodyElementOperationSelector` проверяет начальный тег первого дочернего элемента Body и выбирает операцию, используя упомянутую ранее таблицу.  
  
 Клиент использует прокси-сервера, автоматически сгенерированный из WSDL, экспортированный с помощью службы [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 Тот факт, что параметры Action всех операций пусты, не влияет на клиентский код, не считая параметров Action автоматически созданного прокси.  
  
 Клиентский код выполняет несколько вычислений. При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
  
## <a name="see-also"></a>См. также
