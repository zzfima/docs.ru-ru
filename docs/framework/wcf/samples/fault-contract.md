---
title: "Контракт ошибок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Контракт ошибок
Этот образец демонстрирует передачу информации об ошибке из службы клиенту.  Этот образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) с добавлением в службу некоторого кода для преобразования внутреннего исключения в сбой.  Клиент пытается выполнить операцию деления на ноль для принудительного сбоя службы.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В контракт калькулятора добавлен атрибут <xref:System.ServiceModel.FaultContractAttribute>, как показано в следующем образце кода.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
    [OperationContract]  
    int Subtract(int n1, int n2);  
    [OperationContract]  
    int Multiply(int n1, int n2);  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 Атрибут <xref:System.ServiceModel.FaultContractAttribute> указывает, что операция `Divide` может возвратить сбой типа `MathFault`.  Сбой может принадлежать к любому типу, который сериализовать.  В данном случае `MathFault` представляет собой следующий контракт данных:  
  
```  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public class MathFault  
{      
    private string operation;  
    private string problemType;  
  
    [DataMember]  
    public string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]          
    public string ProblemType  
    {  
        get { return problemType; }  
        set { problemType = value; }  
    }  
}  
  
```  
  
 Метод `Divide` вызывает исключение <xref:System.ServiceModel.FaultException%601> при делении на ноль, как показано в следующем образце кода.  В результате исключения клиенту отправляется сбой.  
  
```  
public int Divide(int n1, int n2)  
{  
    try  
    {  
        return n1 / n2;  
    }  
    catch (DivideByZeroException)  
    {  
        MathFault mf = new MathFault();  
        mf.operation = "division";  
        mf.problemType = "divide by zero";  
        throw new FaultException<MathFault>(mf);  
    }  
}  
```  
  
 Клиентский код принудительно создает ошибку, запрашивая деление не ноль.  При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.  Деление на ноль будет выведено на консоль в виде сбоя.  Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 Клиент выводит сбой, перехватывая соответствующее исключение `FaultException<MathFault>`:  
  
```  
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 По умолчанию сведения о непредвиденных исключениях не отправляются клиенту во избежание утечки сведений о подробностях реализации службы за периметр безопасности службы.  `FaultContract` позволяет описать сбои в контракте и отметить определенные типы исключений как пригодные для передачи клиенту.  `FaultException<T>` предоставляет механизм среды выполнения для отправки данных о сбоях объектам\-пользователям.  
  
 Тем не менее, при отладке удобно иметь возможность просматривать внутренние сведения о сбое службы.  Для отключения описанного выше защитного поведения можно указать, что сведения о каждом необработанном исключении на сервере должны включаться в отправляемый клиенту сбой.  Это делается путем присвоения свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> значения `true`.  Задать это свойство можно в коде или в конфигурации, как показано в следующем образце.  
  
```  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Кроме того, поведение должно быть связано со службой путем присвоения атрибуту `behaviorConfiguration` службы в файле конфигурации значения "CalculatorServiceBehavior".  
  
 Для перехвата таких сбоев на клиенте необходимо перехватывать неуниверсальное исключение <xref:System.ServiceModel.FaultException>.  
  
 Это поведение следует использовать только в целях отладки и ни в коем случае не в рабочей среде.  
  
### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  
  
## См. также