---
title: Контракт ошибок
ms.date: 03/30/2017
ms.assetid: b31b140e-dc3b-408b-b3c7-10b6fe769725
ms.openlocfilehash: 907497101c13e1f62ff2abb5da563178c9643c6c
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70039656"
---
# <a name="fault-contract"></a>Контракт ошибок
Этот образец демонстрирует передачу информации об ошибке из службы клиенту. Образец основан на [Начало работые](../../../../docs/framework/wcf/samples/getting-started-sample.md)с дополнительным кодом, добавленным в службу для преобразования внутреннего исключения в ошибку. Клиент пытается выполнить операцию деления на ноль для принудительного сбоя службы.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В контракт калькулятора добавлен атрибут <xref:System.ServiceModel.FaultContractAttribute>, как показано в следующем образце кода.  
  
```csharp
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
  
 Атрибут <xref:System.ServiceModel.FaultContractAttribute> указывает, что операция `Divide` может возвратить сбой типа `MathFault`. Сбой может принадлежать к любому типу, который сериализовать. В данном случае `MathFault` представляет собой следующий контракт данных:  
  
```csharp
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
  
 Метод `Divide` вызывает исключение <xref:System.ServiceModel.FaultException%601> при делении на ноль, как показано в следующем образце кода. В результате исключения клиенту отправляется сбой.  
  
```csharp
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
  
 Клиентский код принудительно создает ошибку, запрашивая деление не ноль. При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Деление на ноль будет выведено на консоль в виде сбоя. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
FaultException<MathFault>: Math fault while doing division. Problem: divide by zero  
  
Press <ENTER> to terminate client.  
```  
  
 Клиент выводит сбой, перехватывая соответствующее исключение `FaultException<MathFault>`:  
  
```csharp
catch (FaultException<MathFault> e)  
{  
    Console.WriteLine("FaultException<MathFault>: Math fault while doing " + e.Detail.operation + ". Problem: " + e.Detail.problemType);  
    client.Abort();  
}  
```  
  
 По умолчанию сведения о непредвиденных исключениях не отправляются клиенту во избежание утечки сведений о подробностях реализации службы за периметр безопасности службы. `FaultContract` позволяет описать сбои в контракте и отметить определенные типы исключений как пригодные для передачи клиенту. `FaultException<T>` предоставляет механизм среды выполнения для отправки данных о сбоях объектам-пользователям.  
  
 Тем не менее, при отладке удобно иметь возможность просматривать внутренние сведения о сбое службы. Для отключения описанного выше защитного поведения можно указать, что сведения о каждом необработанном исключении на сервере должны включаться в отправляемый клиенту сбой. Это делается путем присвоения свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A> значения `true`. Задать это свойство можно в коде или в конфигурации, как показано в следующем образце.  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="True" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 Кроме того, поведение должно быть связано со службой, задав `behaviorConfiguration` атрибуту службы в файле конфигурации значение "калкулаторсервицебехавиор".  
  
 Для перехвата таких сбоев на клиенте необходимо перехватывать неуниверсальное исключение <xref:System.ServiceModel.FaultException>.  
  
 Это поведение следует использовать только в целях отладки и ни в коем случае не в рабочей среде.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Faults`  
