---
title: "Сеансы | Microsoft Docs"
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
  - "сеансы"
ms.assetid: 36e1db50-008c-4b32-8d09-b56e790b8417
caps.latest.revision: 31
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 31
---
# Сеансы
В образце сеанса показано, как реализовать контракт, требующий сеанс.Сеанс обеспечивает контекст для выполнения нескольких операций.Это позволяет службе связать состояние с заданным сеансом, чтобы последующие операции могли использовать состояние предыдущей операции.Этот образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.Контракт `ICalculator` был изменен, чтобы можно было выполнять набор арифметических операций с сохранением промежуточного результата.Эта функциональность определяется контрактом `ICalculatorSession`.Служба поддерживает состояние клиента во время вызова нескольких операций для вычислений.Клиент может извлечь текущий результат путем вызова метода `Result()` и очистить результат \(сделать его равным нулю\) путем вызова метода `Clear()`.  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Присвоение свойству <xref:System.ServiceModel.SessionMode> контракта значения `Required` гарантирует, что при предоставлении контракта через определенную привязку привязка будет поддерживать сеансы.Если привязка не поддерживает сеансы, создается исключение.Интерфейс `ICalculatorSession` определяется таким образом, чтобы можно было вызывать одну или более операций, что приводит к изменению текущего результата, как показано в следующем образце кода.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface ICalculatorSession  
{  
    [OperationContract(IsOneWay=true)]  
    void Clear();  
    [OperationContract(IsOneWay = true)]  
    void AddTo(double n);  
    [OperationContract(IsOneWay = true)]  
    void SubtractFrom(double n);  
    [OperationContract(IsOneWay = true)]  
    void MultiplyBy(double n);  
    [OperationContract(IsOneWay = true)]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
  
```  
  
 Служба использует <xref:System.ServiceModel.InstanceContextMode> поля <xref:System.ServiceModel.InstanceContextMode>, чтобы привязать контекст заданного экземпляра службы к каждому входящему сеансу.Это позволяет службе поддерживать промежуточный результат для каждого сеанса в локальной переменной\-члене.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class CalculatorService : ICalculatorSession  
{  
    double result = 0.0D;  
  
    public void Clear()  
    {  result = 0.0D; }  
  
    public void AddTo(double n)  
    {  result += n;   }  
  
    public void SubtractFrom(double n)  
    {  result -= n;   }  
  
    public void MultiplyBy(double n)  
    {  result *= n;   }  
  
    public void DivideBy(double n)  
    {  result /= n;   }  
  
    public double Result()  
    {  return result; }  
}  
  
```  
  
 При выполнении образца клиент отправляет на сервер несколько запросов и запрашивает результаты, которые затем отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
(((0 + 100) - 50) * 17.65) / 2 = 441.25  
Press <ENTER> to terminate client.  
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
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Session`  
  
## См. также