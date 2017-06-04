---
title: "Предотвращение проблем при использовании операторов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: aff82a8d-933d-4bdc-b0c2-c2f7527204fb
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Предотвращение проблем при использовании операторов
В этом образце показано, как не следует использовать оператор "using" в C\# для автоматической очистки ресурсов при использовании типизированного клиента.Данный образец основан на образце [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md), реализующем службу калькулятора.В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце показаны две общие проблемы, которые могут возникнуть при использовании оператора "using" в C\# с типизированными клиентами, а также код, который правильно выполняет очистку после исключений.  
  
 Оператор "using" в C\# приводит к вызову метода `Dispose`\(\).Этот метод эквивалентен методу `Close`\(\), который может выдавать исключения при возникновении сетевой ошибки.Поскольку вызов метода `Dispose`\(\) выполняется неявно в закрывающей круглой скобке блока "using", этот источник исключений, скорее всего, останется незамеченным как теми, кто пишет код, так и теми, кто его считывает.Он представляет собой потенциальный источник ошибок приложения.  
  
 Первая проблема, показанная в методе `DemonstrateProblemUsingCanThrow`, заключается в том, что закрывающая круглая скобка выдает исключение, а код после закрывающей круглой скобки не выполняет следующее.  
  
```  
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
} // <-- this line might throw  
Console.WriteLine("Hope this code wasn't important, because it might not happen.");  
```  
  
 Даже если ничего в блоке "using" не выдает исключения или все исключения в блоке "using" перехватываются, `Console.Writeline` может не произойти, поскольку неявный вызов метода `Dispose`\(\) в закрывающей круглой скобке может выдать исключение.  
  
 Вторая проблема, показанная в методе `DemonstrateProblemUsingCanThrowAndMask`, представляет собой еще одно последствие использования закрывающей круглой скобки, выдающей исключение.  
  
```  
using (CalculatorClient client = new CalculatorClient())  
{  
    ...  
    throw new ApplicationException("Hope this exception was not important, because "+  
                                   "it might be masked by the Close exception.");  
} // <-- this line might throw an exception.  
```  
  
 Поскольку метод `Dispose`\(\) происходит в блоке "finally", исключение `ApplicationException` никогда не видно за пределами блока "using", если метод `Dispose`\(\) выполняется с ошибкой.Если внешний код должен знать, когда происходит исключение `ApplicationException`, конструкция "using" может стать причиной возникновения проблем, маскируя это исключение.  
  
 Наконец, в этом образце показано, как правильно выполнить очистку, если исключения происходят в `DemonstrateCleanupWithExceptions`.При этом используется блок try\/catch для сообщения об ошибках и вызова метода `Abort`.Дополнительные сведения о перехвате исключений из вызовов клиента см. в разделе [Ожидаемые исключения](../../../../docs/framework/wcf/samples/expected-exceptions.md).  
  
```  
try  
{  
    ...  
    client.Close();  
}  
catch (CommunicationException e)  
{  
    ...  
    client.Abort();  
}  
catch (TimeoutException e)  
{  
    ...  
    client.Abort();  
}  
catch (Exception e)  
{  
    ...  
    client.Abort();  
    throw;  
}  
```  
  
> [!NOTE]
>  Оператор "using" и ServiceHost. Большинство резидентных приложений не только размещают службу, а метод ServiceHost.Close редко выдает исключение, поэтому такие приложения могут безопасно использовать оператор "using" с ServiceHost.Однако необходимо помнить, что метод ServiceHost.Close может выдать исключение `CommunicationException`, поэтому если приложение продолжает работать после закрытия ServiceHost, следует избегать использования оператора "using" и следовать шаблону, указанному ранее.  
  
 При выполнении образца ответы и исключения операций отображаются в окне консоли клиента.  
  
 Клиентский процесс выполняет три сценария, каждый из которых пытается вызвать метод `Divide`.В первом сценарии показан код, пропущенный из\-за исключения, выданного методом `Dispose`\(\).Во втором сценарии показано важное исключение с маской из\-за исключения, выданного методом `Dispose`\(\).В третьем сценарии показана правильная очистка.  
  
 Ниже представлен ожидаемый результат выполнения клиентского процесса.  
  
```  
=  
= Demonstrating problem:  closing brace of using statement can throw.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating problem:  closing brace of using statement can mask other Exceptions.  
=  
Got System.ServiceModel.CommunicationException from Divide.  
Got System.ServiceModel.Security.MessageSecurityException  
=  
= Demonstrating cleanup with Exceptions.  
=  
Calling client.Add(0.0, 0.0);  
        client.Add(0.0, 0.0); returned 0  
Calling client.Divide(0.0, 0.0);  
Got System.ServiceModel.CommunicationException from Divide.  
  
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
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Client\UsingUsing`  
  
## См. также