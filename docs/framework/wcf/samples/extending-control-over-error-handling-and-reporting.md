---
title: Повышение управляемости обработки ошибок и формирования сообщений об ошибках
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: 6492807b55b50662790cf25807a35ddd65fbe01d
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032842"
---
# <a name="extending-control-over-error-handling-and-reporting"></a>Повышение управляемости обработки ошибок и формирования сообщений об ошибках
В этом примере показано, как расширить управление обработкой ошибок и ошибок на службу Windows Communication Foundation (WCF) с помощью <xref:System.ServiceModel.Dispatcher.IErrorHandler> интерфейс. Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) некоторые дополнительный код, добавленный в службу для обработки ошибок. Клиент вызывает несколько ошибок. Служба перехватывает эти ошибки и регистрирует их в файле.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Интерфейс <xref:System.ServiceModel.Dispatcher.IErrorHandler> позволяет службам перехватывать ошибки, обрабатывать их и определять, каким образом будут создаваться отчеты об этих ошибках. Интерфейс позволяет реализовать два метода: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> и <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>. Метод <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> служит для добавления, изменения и подавления сообщений ошибках, создаваемых в результате исключений. Метод <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> служит для обработки ошибки в случае ее возникновения и позволяет определять, требуется ли дополнительная обработка ошибок.  
  
 В этом образце тип `CalculatorErrorHandler` реализует интерфейс <xref:System.ServiceModel.Dispatcher.IErrorHandler>. В  
  
 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> обработчик `CalculatorErrorHandler` записывает ошибку в текстовый файл Error.txt в папке c:\logs. Обратите внимание, что этот образец регистрирует ошибку в журнале и не подавляет ее, чтобы о ней можно было уведомить клиент.  
  
```  
public class CalculatorErrorHandler : IErrorHandler  
{  
        // Provide a fault. The Message fault parameter can be replaced, or set to  
        // null to suppress reporting a fault.  
  
        public void ProvideFault(Exception error, MessageVersion version, ref Message fault)  
        {  
        }  
  
        // HandleError. Log an error, then allow the error to be handled as usual.  
        // Return true if the error is considered as already handled  
  
        public bool HandleError(Exception error)  
        {  
            using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))  
            {  
                if (error != null)  
                {  
                    tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);  
                }  
                tw.Close();  
            }  
            return true;  
        }  
    }  
```  
  
 Атрибут `ErrorBehaviorAttribute` выполняет роль механизма регистрации обработчика ошибок в службе. Этот атрибут принимает параметр единственного типа. Этот тип должен быть реализацией интерфейса <xref:System.ServiceModel.Dispatcher.IErrorHandler> и должен иметь открытый пустой конструктор. В этом случае атрибут создает экземпляр типа обработчика ошибок и устанавливает его в службе. Для этого он реализует интерфейс <xref:System.ServiceModel.Description.IServiceBehavior> и с помощью метода <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> добавляет экземпляры в обработчик ошибок в службе.  
  
```  
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }                                                  
    }  
}  
```  
  
 Этот образец реализует службу калькулятора. Клиент намеренно вызывает в службе две ошибки путем предоставления параметров с недопустимыми значениями. `CalculatorErrorHandler` с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IErrorHandler> записывает ошибки в локальный файл и позволяет уведомить клиент об этих ошибках. Клиент вызывает ошибки типа "деление на ноль" и "аргумент вне диапазона".  
  
```  
try  
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. При этом будут появляться ошибки типа "деление на ноль" и "аргумент вне диапазона". Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 Файл c:\logs\errors.txt содержит записанные службой сведения об ошибках. Обратите внимание: чтобы служба могла вести запись в определенном каталоге, у процесса, в котором выполняется служба (обычно это ASP.NET или Network Service) должны быть разрешения на запись для этого каталога.  
  
```  
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Проверьте, что создан каталог c:\logs для файла error.txt. Либо измените имя файла, используемое в `CalculatorErrorHandler.HandleError`.  
  
4.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
  
## <a name="see-also"></a>См. также
