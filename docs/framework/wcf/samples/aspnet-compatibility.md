---
title: "Совместимость с ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c8b51f1e-c096-4c42-ad99-0519887bbbc5
caps.latest.revision: 25
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 25
---
# Совместимость с ASP.NET
В этом образце показано, как включить режим совместимости [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  Службы, работающие в режиме совместимости с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], полностью участвуют в конвейере приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и могут использовать функции [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], такие как "File\/URL Authorization" \(Авторизация файла\/URL\-адреса\), "Session State" \(Состояние сеанса\) и класс <xref:System.Web.HttpContext>.  Класс <xref:System.Web.HttpContext> обеспечивает доступ к файлам cookie, сеансам и другим функциям [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  Для этого режима требуется, чтобы привязки использовали транспорт HTTP, а сами службы были размещены в службах IIS.  
  
 В этом примере клиентом является консольное приложение \(как исполняемый файл\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!NOTE]
>  Для выполнения данного образца необходим пул приложений [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].  Чтобы создать новый пул приложений или изменить пул приложений по умолчанию, выполните следующие шаги.  
>   
>  1.  Откройте **панель управления**.  Откройте приложение **Администрирование** в разделе **Безопасность**.  Откройте приложение **Диспетчер служб IIS**.  
> 2.  Разверните дерево в области **Соединения**.  Выберите узел **Пулы приложений**.  
> 3.  Чтобы настроить пул приложений по умолчанию для использования [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] \(что может вызвать проблемы несовместимости у существующих узлов\), щелкните правой кнопкой мыши элемент списка **DefaultAppPool** и выберите пункт **Основные параметры…** Выберите в раскрывающемся меню **Версия .Net Framework** пункт **.Net Framework 4.0.30128** \(или более позднюю версию\).  
> 4.  Чтобы создать новый пул приложений, использующий [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)] \(для сохранения совместимости с другими приложениями\), щелкните правой кнопкой мыши узел **Пулы приложений** и выберите пункт **Добавить пул приложений…** Введите имя нового пула приложений и выберите в раскрывающемся меню **Версия .Net Framework** пункт **.Net Framework 4.0.30128** \(или более позднюю версию\).  После выполнения приведенных ниже шагов настройки щелкните правой кнопкой мыши приложение **ServiceModelSamples** и выберите пункты **Управление приложением** и **Дополнительные параметры…**.  Укажите в качестве значения параметра **Пул приложений** вновь созданный пул приложений.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.  Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].  Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\ASPNetCompatibility`  
  
 Этот пример основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.  Контракт `ICalculator` был изменен в соответствии с контрактом `ICalculatorSession`, чтобы можно было выполнять набор операций с сохранением промежуточного результата.  
  
```  
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
  
 Благодаря использованию функции служба поддерживает состояние клиента во время вызова нескольких операций для вычислений.  Клиент может извлечь текущий результат путем вызова метода `Result` и очистить результат \(сделать его равным нулю\) путем вызова метода `Clear`.  
  
 Служба использует сеанс [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] для хранения результата каждого сеанса клиента.  Это позволяет службе поддерживать промежуточный результат для каждого клиента по мере множественных вызовов службы.  
  
> [!NOTE]
>  Состояние сеанса [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и сеансы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] имеют очень большие отличия.  Дополнительные сведения о сеансах [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Сеансы](../../../../docs/framework/wcf/samples/session.md).  
  
 Служба сильно зависит от состояния сеанса [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и требует правильной работы режима совместимости [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  Такие требования выражаются декларативно путем применения атрибута `AspNetCompatibilityRequirements`.  
  
```  
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
  
 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.  Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
  
0, + 100, - 50, * 17.65, / 2 = 441.25  
Press <ENTER> to terminate client.  
  
```  
  
### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  После построения решения запустите файл Setup.bat, чтобы настроить приложение ServiceModelSamples в службах [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  Теперь каталог ServiceModelSamples должен представляться как приложение [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также  
 [Образцы размещения и сохраняемости фабрики приложений](http://go.microsoft.com/fwlink/?LinkId=193961)