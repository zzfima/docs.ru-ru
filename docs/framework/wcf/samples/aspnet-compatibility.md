---
title: Совместимость с ASP.NET
ms.date: 03/30/2017
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
ms.openlocfilehash: 01381dc579f5ae3eadd2f913a0e09d7d259794a1
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59304227"
---
# <a name="aspnet-compatibility"></a>Совместимость с ASP.NET
В этом примере показано, как включить режим совместимости ASP.NET в Windows Communication Foundation (WCF). Использование служб, работающих в режиме, принимают полное участие в конвейере приложения ASP.NET и осуществлять совместимости с ASP.NET функции ASP.NET, такие как авторизация файла/URL-адрес, состояние сеанса и <xref:System.Web.HttpContext> класса. <xref:System.Web.HttpContext> Класс позволяет получить доступ к файлы cookie, сеансов и других функций ASP.NET. Для этого режима требуется, чтобы привязки использовали транспорт HTTP, а сами службы были размещены в службах IIS.  
  
 В этом примере клиентом является консольное приложение (как исполняемый файл), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
Для выполнения данного образца необходим пул приложений [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]. Чтобы создать новый пул приложений или изменить пул приложений по умолчанию, выполните следующие шаги.  

1. Откройте **панель управления**.  Откройте **Администрирование** приложения в разделе **система и безопасность** заголовок. Откройте **Internet Information Services (IIS) Manager** приложения.  

2. Разверните дерево в **подключений** области. Выберите **пулы приложений** узла.  

3. Чтобы настроить пул приложений по умолчанию для использования [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (что может вызвать проблемы несовместимости у существующих сайтов), щелкните правой кнопкой мыши **DefaultAppPool** элемент списка и выберите **основные параметры...** . Задайте **.Net Framework версии** подключен к **.Net Framework 4.0.30128** (или более поздней версии).  

4. Чтобы создать новый пул приложений, который использует [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] (для сохранения совместимости с другими приложениями), щелкните правой кнопкой мыши **пулы приложений** узел и выберите **добавить пул приложений...** . Присвойте имя нового пула приложений и задайте **.Net Framework версии** подключен к **.Net Framework 4.0.30128** (или более поздней версии). После запуска программы установки шагов ниже, щелкните правой кнопкой мыши **ServiceModelSamples** и выберите команду **управление приложением**, **Дополнительные параметры...** . Задайте **пул приложений** новый пул приложений.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md), который реализует службу калькулятора. Контракт `ICalculator` был изменен в соответствии с контрактом `ICalculatorSession`, чтобы можно было выполнять набор операций с сохранением промежуточного результата.  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculatorSession  
{  
    [OperationContract]  
    void Clear();  
    [OperationContract]  
    void AddTo(double n);  
    [OperationContract]  
    void SubtractFrom(double n);  
    [OperationContract]  
    void MultiplyBy(double n);  
    [OperationContract]  
    void DivideBy(double n);  
    [OperationContract]  
    double Result();  
}  
```  
  
 Благодаря использованию возможности служба поддерживает состояние клиента во время вызова нескольких операций для вычислений. Клиент может извлечь текущий результат путем вызова метода `Result` и очистить результат (сделать его равным нулю) путем вызова метода `Clear`.  
  
 Служба использует сеанс ASP.NET для хранения результата для каждого сеанса клиента. Это позволяет службе поддерживать промежуточный результат для каждого клиента по мере множественных вызовов службы.  
  
> [!NOTE]
> Состояние сеанса ASP.NET и WCF сеансы являются очень разные вещи. См. в разделе [сеанса](../../../../docs/framework/wcf/samples/session.md) Дополнительные сведения о сеансах WCF.
  
 Служба глубоким зависимого от состояния сеанса ASP.NET и требуется режим совместимости ASP.NET для правильной работы. Такие требования выражаются декларативно путем применения атрибута `AspNetCompatibilityRequirements`.  
  
```csharp  
[AspNetCompatibilityRequirements(RequirementsMode =  
                       AspNetCompatibilityRequirementsMode.Required)]  
public class CalculatorService : ICalculatorSession  
{  
    double Result  
    {  // store result in AspNet Session  
       get {  
          if (HttpContext.Current.Session["Result"] != null)  
             return (double)HttpContext.Current.Session["Result"];  
          return 0.0D;  
       }  
       set  
       {  
          HttpContext.Current.Session["Result"] = value;  
       }  
    }  
    public void Clear()  
    {  
        Result = 0.0D;  
    }  
    public void AddTo(double n)  
    {  
        Result += n;  
    }  
    public void SubtractFrom(double n)  
    {  
        Result -= n;  
    }  
    public void MultiplyBy(double n)  
    {  
        Result *= n;  
    }  
    public void DivideBy(double n)  
    {  
        Result /= n;  
    }  
    public double Result()  
    {  
        return Result;  
    }  
}  
```
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```console
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. После построения решения запустите файл Setup.bat, чтобы настроить приложение ServiceModelSamples в службах [!INCLUDE[iisver](../../../../includes/iisver-md.md)]. Теперь каталог ServiceModelSamples должен представляться как приложение [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4. Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## <a name="see-also"></a>См. также

- [Образцы размещения и сохраняемости AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)
