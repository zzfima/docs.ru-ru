---
title: "Дуплекс | Microsoft Docs"
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
  - "дуплексный контракт службы"
ms.assetid: bc5de6b6-1a63-42a3-919a-67d21bae24e0
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Дуплекс
Этот образец демонстрирует, как определить и реализовать дуплексный контракт.  Дуплексная связь имеет место, когда клиент устанавливает сеанс со службой и предоставляет службе канал, по которому служба может отправлять сообщения обратно клиенту.  Этот образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).  Дуплексный контракт определяется в виде пары интерфейсов \- основной интерфейс от клиента к службе и интерфейс обратного вызова от службы к клиенту.  В этом образце интерфейс `ICalculatorDuplex` позволяет клиенту выполнять математические операции, вычисляя результат в ходе сеанса.  Служба возвращает результаты в интерфейсе `ICalculatorDuplexCallback`.  Для дуплексного контракта требуется сеанс, поскольку необходимо установить контекст для корреляции набора сообщений, передаваемых между клиентом и службой.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  Дуплексный контракт определяется следующим образом:  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required,  
                 CallbackContract=typeof(ICalculatorDuplexCallback))]  
public interface ICalculatorDuplex  
{  
    [OperationContract(IsOneWay = true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
}  
  
public interface ICalculatorDuplexCallback  
{  
    [OperationContract(IsOneWay = true)]  
    void Result(double result);  
    [OperationContract(IsOneWay = true)]  
    void Equation(string eqn);  
}  
  
```  
  
 Класс `CalculatorService` реализует основной интерфейс `ICalculatorDuplex`.  Служба использует режим экземпляра <xref:System.ServiceModel.InstanceContextMode> для поддержания результата для каждого сеанса.  Закрытое свойство `Callback` используется для доступа к каналу обратного вызова к клиенту.  Служба использует обратный вызов для отправки сообщений обратно клиенту через интерфейс обратного вызова.  
  
```  
[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorDuplex  
{  
    double result = 0.0D;  
    string equation;  
  
    public CalculatorService()  
    {  
        equation = result.ToString();  
    }  
  
    public void Clear()  
    {  
        Callback.Equation(equation + " = " + result.ToString());  
        equation = result.ToString();  
    }  
  
    public void AddTo(double n)  
    {  
        result += n;  
        equation += " + " + n.ToString();  
        Callback.Result(result);  
    }  
    ...  
    ICalculatorDuplexCallback Callback  
    {  
        get  
        {  
            return OperationContext.Current.GetCallbackChannel<ICalculatorDuplexCallback>();  
        }  
    }  
}  
```  
  
 Для получения сообщений от службы клиент обязан предоставить класс, который реализует интерфейс обратного вызова дуплексного контракта.  В этом образце для реализации интерфейса `ICalculatorDuplexCallback` определен класс `CallbackHandler`.  
  
```  
public class CallbackHandler : ICalculatorDuplexCallback  
{  
   public void Result(double result)  
   {  
      Console.WriteLine("Result({0})", result);  
   }  
  
   public void Equation(string equation)  
   {  
      Console.WriteLine("Equation({0}", equation);  
   }  
}  
  
```  
  
 Прокси\-объект, формируемый для дуплексного контракта, при создании требует предоставления объекта <xref:System.ServiceModel.InstanceContext>.  Этот объект <xref:System.ServiceModel.InstanceContext> используется в качестве сайта для объекта, реализующего интерфейс обратного вызова и обрабатывающего сообщения, которые отправляются службой обратно.  Класс <xref:System.ServiceModel.InstanceContext> создается с экземпляром класса `CallbackHandler`.  Этот объект обрабатывает сообщения, отправляемые службой клиенту в интерфейсе обратного вызова.  
  
```  
// Construct InstanceContext to handle messages on callback interface.  
InstanceContext instanceContext = new InstanceContext(new CallbackHandler());  
  
// Create a client.  
CalculatorDuplexClient client = new CalculatorDuplexClient(instanceContext);  
  
Console.WriteLine("Press <ENTER> to terminate client once the output is displayed.");  
Console.WriteLine();  
  
// Call the AddTo service operation.  
double value = 100.00D;  
client.AddTo(value);  
  
// Call the SubtractFrom service operation.  
value = 50.00D;  
client.SubtractFrom(value);  
  
// Call the MultiplyBy service operation.  
value = 17.65D;  
client.MultiplyBy(value);  
  
// Call the DivideBy service operation.  
value = 2.00D;  
client.DivideBy(value);  
  
// Complete equation.  
client.Clear();  
  
Console.ReadLine();  
  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
  
```  
  
 Конфигурация изменена таким образом, чтобы предоставлялась привязка, которая поддерживает как сеансовую, так и дуплексную связь.  Привязка `wsDualHttpBinding` поддерживает сеансовую и дуплексную связь, предоставляя двойные соединения HTTP \(по одному для каждого направления\).  На стороне службы единственным отличием в конфигурации является используемая привязка.  На стороне клиента необходимо настроить адрес, который будет использоваться сервером для подключения к клиенту, как показано в следующем образце конфигурации.  
  
```  
<client>  
  <endpoint name=""  
            address="http://localhost/servicemodelsamples/service.svc"   
            binding="wsDualHttpBinding"   
            bindingConfiguration="DuplexBinding"   
            contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
</client>  
  
<bindings>  
  <!-- Configure a binding that support duplex communication. -->  
  <wsDualHttpBinding>  
    <binding name="DuplexBinding"   
             clientBaseAddress="http://localhost:8000/myClient/">  
    </binding>  
  </wsDualHttpBinding>  
</bindings>  
  
```  
  
 При выполнении образца видны сообщения, возвращаемые клиенту в интерфейсе обратного вызова, отправляемом службой.  Отображается каждый промежуточный результат с последующим отображением всей формулы после завершения всех операций.  Чтобы закрыть клиент, нажмите клавишу ВВОД.  
  
### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы выполнить построение выпуска решения для языка C\#, C\+\+ или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!IMPORTANT]
    >  Если пример выполняется на нескольких компьютерах, обязательно замените "localhost" в атрибуте `address` элемента [endpoint](http://msdn.microsoft.com/ru-ru/13aa23b7-2f08-4add-8dbf-a99f8127c017) и атрибуте `clientBaseAddress` элемента [\<привязка\>](../../../../docs/framework/misc/binding.md), расположенного в элементе [\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md), именем соответствующего компьютера, как показано ниже.  
  
    ```  
    <client>  
    <endpoint name = ""  
    address="http://service_machine_name/servicemodelsamples/service.svc"  
    ... />  
    </client>  
    ...  
    <wsDualHttpBinding>  
    <binding name="DuplexBinding" clientBaseAddress="http://client_machine_name:8000/myClient/">  
    </binding>  
    </wsDualHttpBinding>  
    ```  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Duplex`  
  
## См. также