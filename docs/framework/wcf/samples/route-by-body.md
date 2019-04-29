---
title: Маршрутизация по телу сообщения
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: b8a3f7785d7d59d8ad85d6dddde7fd6a04a12d63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787560"
---
# <a name="route-by-body"></a>Маршрутизация по телу сообщения
В этом образце показано, как реализовать службу, которая принимает объекты сообщений с действием SOAP. Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующем службу калькулятора. Служба реализует одну операцию `Calculate`, которая принимает параметр запроса <xref:System.ServiceModel.Channels.Message> и возвращает ответ <xref:System.ServiceModel.Channels.Message>.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец демонстрирует диспетчеризацию сообщений на основе содержимого тела сообщения. Встроенный механизм диспетчеризации модели службы Windows Communication Foundation (WCF) сообщение зависит от сообщения действия. Однако есть много существующих веб-служб, которые для всех своих операций определяют параметр Action="". Невозможно построить службу на основе кода WSDL, когда диспетчеризация сообщений запросов осуществляется на основе параметра Action. В этом образце показан контракт службы, основанный на коде WSDL (код WSDL содержится в файле Service.wsdl, который входит в этот образец). Контракт службы-Calculator, подобной той, используемых в [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md). Однако контракт `[OperationContract]` задает для всех операций `Action=""`.  
  
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
  
 Чтобы при таком контракте можно было распределять сообщения между операциями, службе требуется пользовательское поведение диспетчеризации `DispatchByBodyBehavior`. Это поведение отправки инициализирует `DispatchByBodyElementOperationSelector` пользовательский селектор операций с таблицей имен операций, обозначенных с помощью значений QName соответствующих элементов оболочек. Операция `DispatchByBodyElementOperationSelector` проверяет начальный тег первого дочернего элемента Body и выбирает операцию, используя упомянутую ранее таблицу.  
  
 Клиент использует прокси-сервера, автоматически создается из кода WSDL, экспортированного службой с помощью [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).  
  
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
  
1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
