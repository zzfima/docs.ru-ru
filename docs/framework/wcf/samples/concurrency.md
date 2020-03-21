---
title: Параллелизм
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
ms.openlocfilehash: eb6140895bb922bd159f1abf536a0d0b12d4f96c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183931"
---
# <a name="concurrency"></a>Параллелизм
Образец Concurrency демонстрирует использование <xref:System.ServiceModel.ServiceBehaviorAttribute> с перечислением <xref:System.ServiceModel.ConcurrencyMode>, определяющим, будет ли экземпляр службы обрабатывать сообщения последовательно или параллельно. Образец основан на [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), `ICalculator` который реализует контракт на обслуживание. Этот образец определяет новый контракт, `ICalculatorConcurrency`, унаследованный от `ICalculator`, который добавляет две операции для контроля состояния параллелизма службы. Изменив параметр параллелизма, можно запустить клиент и посмотреть, как изменилось поведение.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Доступны три режима параллелизма.  
  
- `Single`: все экземпляры службы обрабатывают в данный момент времени одно сообщение. Это режим параллелизма по умолчанию.  
  
- `Multiple`: каждый экземпляр службы обрабатывает несколько сообщений параллельно. Чтобы использовать этот режим параллелизма, реализация службы должна быть потокобезопасной.  
  
- `Reentrant`: каждый экземпляр службы одновременно обрабатывает одно сообщение, но принимает вызовы с повторным входом. Служба принимает эти звонки только тогда, когда она вызывает. Реантентант демонстрируется в выборке [ConcurrencyMode.Reentrant.](../../../../docs/framework/wcf/samples/concurrencymode-reentrant.md)  
  
 Использование параллелизма связано с режимом создания экземпляров. В режиме создания экземпляров <xref:System.ServiceModel.InstanceContextMode.PerCall> параллелизм не имеет значения, так как каждое сообщение обрабатывается новым экземпляром службы. В режиме создания экземпляров <xref:System.ServiceModel.InstanceContextMode.Single> имеет значение параллелизм <xref:System.ServiceModel.ConcurrencyMode.Single> или <xref:System.ServiceModel.ConcurrencyMode.Multiple>, в зависимости от того, обрабатывает ли один экземпляр сообщения последовательно или параллельно. В режиме создания экземпляров <xref:System.ServiceModel.InstanceContextMode.PerSession> могут иметь значение любые режимы параллелизма.  
  
 Класс службы задает поведение параллелизма с помощью атрибута `[ServiceBehavior(ConcurrencyMode=<setting>)]`, как показано в следующем образце кода. Преобразуя в комментарий различные строки, можно поэкспериментировать с режимами параллелизма `Single` и `Multiple`. Не забывайте строить службу заново после изменения режима параллелизма.  
  
```csharp
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 По умолчанию образец использует параллелизм <xref:System.ServiceModel.ConcurrencyMode.Multiple> с режимом создания экземпляров <xref:System.ServiceModel.InstanceContextMode.Single>. Код клиента изменен для использования асинхронного прокси. Это позволяет клиенту направлять службе сразу несколько вызовов, не дожидаясь ответа на каждый вызов. Можно наблюдать различия в поведении режима параллелизма службы.  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Отображается режим параллелизма, в котором работает служба, вызываются все операции, и отображается число операций. Обратите внимание, что в режиме параллельности `Multiple` результаты возвращаются в порядке, отличном от порядка вызовов, потому что служба обрабатывает несколько сообщений параллельно. Если изменить режим параллельности на `Single`, результаты возвращаются в порядке вызова, потому что служба обрабатывает все сообщения последовательно. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Если вы используете Svcutil.exe для создания прокси-клиента, убедитесь, что вы включаете опцию. `/async`  
  
3. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4. Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
