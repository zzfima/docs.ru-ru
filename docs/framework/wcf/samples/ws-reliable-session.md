---
title: "Надежный сеанс WS | Microsoft Docs"
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
  - "надежный сеанс"
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Надежный сеанс WS
Данный образец демонстрирует использование надежных сеансов.Надежные сеансы предоставляют поддержку для надежных сеансов и обмена сообщениями.При надежном обмене сообщениями в случае сбоя предпринимается повторная попытка передачи и задаются такие гарантии доставки, как соблюдение порядка получения сообщений.Сеансы поддерживают состояние для клиентов между вызовами.Образец реализует сеансы для поддержки состояния клиента и задает гарантии соблюдения очередности доставки сообщений.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.Функции надежного сеанса включаются и настраиваются в файлах конфигурации приложения для клиента и службы.  
  
 В этом образце служба размещается в службах IIS, а клиентом является консольное приложение \(EXE\).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце используется привязка `wsHttpBinding`.Привязка задается в файлах конфигурации клиента и службы.Тип привязки задается в атрибуте `binding` элемента конечной точки, как показано в следующем образце конфигурации.  
  
```  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  
```  
  
 Конечная точка содержит атрибут `bindingConfiguration`, ссылающийся на конфигурацию привязки с именем "Binding1". Конфигурация привязки разрешает безопасные сеансы путем присвоения значения `true` атрибуту `enabled` элемента [\<reliableSession\>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md).Гарантии доставки для упорядоченных сеансов контролируются путем присвоения атрибуту упорядочивания значений `true` или `false`.Значение по умолчанию — `true`.  
  
```  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
  
```  
  
 Класс реализации службы реализует <xref:System.ServiceModel.InstanceContextMode>, создающий экземпляры для поддержания отдельного экземпляра класса для каждого клиента, как показано в следующем образце кода.  
  
```  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
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
  
1.  Установите [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0, выполнив следующую команду.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
  
    ```  
  
2.  Убедитесь, что выполнена процедура, описанная в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
3.  Чтобы создать версию решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы выполнить образец на одном или нескольких компьютерах, следуйте инструкциям раздела [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
## См. также