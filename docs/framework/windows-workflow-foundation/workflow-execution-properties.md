---
title: Свойства выполнения рабочего процесса
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: 0f958e7e112bfddc2740c2605d446493f2d49010
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182666"
---
# <a name="workflow-execution-properties"></a>Свойства выполнения рабочего процесса
Через локальную память потока (TLS) CLR поддерживает контекст выполнения для каждого потока. Этот контекст выполнения управляет хорошо известными свойствами потоков, например идентификатором потока, внешней транзакцией и текущим набором разрешений, а также пользовательскими свойствами потока, например именованными областями.  
  
 В отличие от программ, предназначенных для непосредственной работы в среде CLR, программы рабочих процессов представляют иерархические деревья действий, которые выполняются в среде, не поддерживающей разделение на потоки. Это предполагает, что с помощью стандартных механизмов TLS нельзя непосредственно определить, какой контекст находится в области для данного рабочего элемента. Например, две параллельные ветви выполнения могут использовать различные транзакции, но планировщик может чередовать их выполнение в одном потоке CLR.  
  
 Свойства выполнения рабочего процесса предоставляют механизм добавления определенных свойств контекста к среде действия. Это позволяет действию объявлять, какие свойства находятся в области для его поддерева, а также предоставлять обработчики для установки или удаления TLS в целях правильного взаимодействия с объектами CLR.  
  
## <a name="creating-and-using-workflow-execution-properties"></a>Создание и использование свойств выполнения рабочего процесса  
 Свойства выполнения рабочего процесса обычно реализуют интерфейс <xref:System.Activities.IExecutionProperty>, хотя свойства, сфокусированные на обмене сообщениями, могут вместо этого реализовать <xref:System.ServiceModel.Activities.ISendMessageCallback> и <xref:System.ServiceModel.Activities.IReceiveMessageCallback>. Чтобы создать свойство выполнения рабочего процесса, создайте класс, который реализует интерфейс <xref:System.Activities.IExecutionProperty>, а также реализует элементы <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> и <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>. Эти элементы обеспечивают для свойства выполнения возможность правильной настройки локального хранилища потока на всех этапах выполнения действия, которое содержит свойство, включая все дочерние свойства. В этом примере создается `ConsoleColorProperty`, который задает `Console.ForegroundColor`.  
  
```csharp  
class ConsoleColorProperty : IExecutionProperty  
{  
    public const string Name = "ConsoleColorProperty";  
  
    ConsoleColor original;  
    ConsoleColor color;  
  
    public ConsoleColorProperty(ConsoleColor color)  
    {  
        this.color = color;  
    }  
  
    void IExecutionProperty.SetupWorkflowThread()  
    {  
        original = Console.ForegroundColor;  
        Console.ForegroundColor = color;  
    }  
  
    void IExecutionProperty.CleanupWorkflowThread()  
    {  
        Console.ForegroundColor = original;  
    }  
}  
```  
  
 Создатели действия могут использовать это свойство путем его регистрации в операции переопределения выполнения действия. В этом примере определяется действие `ConsoleColorScope`, которое регистрирует свойство `ConsoleColorProperty` путем его добавления к коллекции <xref:System.Activities.NativeActivityContext.Properties%2A> текущего контекста <xref:System.Activities.NativeActivityContext>.  
  
```csharp  
public sealed class ConsoleColorScope : NativeActivity  
{  
    public ConsoleColorScope()  
        : base()  
    {  
    }  
  
    public ConsoleColor Color { get; set; }  
    public Activity Body { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        context.Properties.Add(ConsoleColorProperty.Name, new ConsoleColorProperty(this.Color));  
  
        if (this.Body != null)  
        {  
            context.ScheduleActivity(this.Body);  
        }  
    }  
}  
```  
  
 С началом в тексте действия рабочего импульса вызывается метод <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> этого свойства, а после завершения рабочего импульса вызывается <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>. В этом примере создается рабочий процесс, который использует действие <xref:System.Activities.Statements.Parallel> с тремя ветвями. В первых двух ветвях используется действие `ConsoleColorScope`, а в третьей - нет. Все три ветви содержат два действия <xref:System.Activities.Statements.WriteLine> и действие <xref:System.Activities.Statements.Delay>. При выполнении действия <xref:System.Activities.Statements.Parallel> те действия, которые содержатся в ветвях, выполняются с чередованием, но при выполнении каждого дочернего действия свойство `ConsoleColorProperty` применяет правильный цвет консоли.  
  
```csharp  
Activity wf = new Parallel  
{  
    Branches =
    {  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Blue,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start blue text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End blue text."  
                    }  
                }  
            }  
        },  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Red,  
            Body = new Sequence  
            {  
                Activities =
                {  
                    new WriteLine  
                    {  
                        Text = "Start red text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End red text."  
                    }  
                }  
            }  
        },  
        new Sequence  
        {  
            Activities =
            {  
                new WriteLine  
                {  
                    Text = "Start default text."  
                },  
                new Delay  
                {  
                    Duration = TimeSpan.FromSeconds(1)  
                },  
                new WriteLine  
                {  
                    Text = "End default text."  
                }  
            }  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 При вызове рабочего процесса в окне консоли записываются следующие выходные данные.  
  
```console  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
> Хотя это не показано в предшествующих выходных данных, все строки текста в окне консоли отображаются с использованием указанного цвета.  
  
 Создатели настраиваемого действия могут использовать свойства выполнения рабочего процесса, а также предоставлять механизм управления обработкой для таких действий, как <xref:System.ServiceModel.Activities.CorrelationScope> и <xref:System.Activities.Statements.TransactionScope>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Activities.IExecutionProperty>
- <xref:System.Activities.IPropertyRegistrationCallback>
- <xref:System.Activities.RegistrationContext>
