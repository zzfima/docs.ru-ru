---
title: "Размещение в службах IIS с использованием встроенного кода | Microsoft Docs"
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
  - "образец размещения в службах IIS с использованием встроенного кода [Windows Communication Foundation]"
  - "размещаемая на веб-узле служба"
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Размещение в службах IIS с использованием встроенного кода
Этот образец демонстрирует реализацию службы, размещенной в службах IIS, когда код службы находится в строках файла SVC и компилируется по требованию.Код службы может также быть реализован непосредственно в файлах исходного кода, расположенных в каталоге \\App\_Code приложения, или он может быть скомпилирован в сборку, развернутую в каталоге \\bin.В этом образце такие приемы не демонстрируются.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`  
  
 В этом образце показана типичная служба, которая реализует контракт, определяющий шаблон взаимодействия «запрос\-ответ».Служба размещается в службах IIS, а весь код службы полностью содержится в файле Service.svc.Служба активируется основным приложением и компилируется по требованию при поступлении первого сообщения, отправленного этой службе.Предварительная компиляция не требуется.Служба реализует контракт `ICalculator`, как показано в следующем примере кода:  
  
```  
// Define a service contract.  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 Реализация службы выполняет вычисления и возвращает соответствующий результат.  
  
```  
<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>   
…  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  После построения решения запустите файл setup.bat, чтобы настроить приложение ServiceModelSamples в службах [!INCLUDE[iisver](../../../../includes/iisver-md.md)].Теперь каталог ServiceModelSamples должен представляться как приложение [!INCLUDE[iisver](../../../../includes/iisver-md.md)].  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).Пример способов создания клиентских приложений, которые можно использовать для вызова этой службы, см. в [Как создать клиент](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).  
  
## См. также  
 [Образцы размещения и сохраняемости AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)