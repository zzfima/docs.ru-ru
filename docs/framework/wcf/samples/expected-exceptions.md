---
title: "Ожидаемые исключения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 299a6987-ae6b-43c6-987f-12b034b583ae
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 093480ae4c1932cdf3294945a3f981527cdd7a6d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="expected-exceptions"></a>Ожидаемые исключения
В этом образце показано, как перехватывать ожидаемые исключения при использовании типизированного клиента. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) , реализующий службу калькулятора. В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце показано кэширование и обработка ожидаемых исключений двух типов, которые должны обрабатываться правильно работающими программами: `TimeoutException` и `CommunicationException`.  
  
 Исключения, создаваемые методами взаимодействия клиента [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут быть ожидаемыми или неожиданными. Неожиданные исключения включают разрушительный сбой, например `OutOfMemoryException`, и ошибки программирования, например `ArgumentNullException` или `InvalidOperationException`. В общем случае не существует удобного способа обработки неожиданных ошибок, поэтому обычно их не следует перехватывать при вызове метода взаимодействия клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 К ожидаемым исключениям методов взаимодействия клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] относятся исключения `TimeoutException`, `CommunicationException`, а также все производные классы для класса `CommunicationException`. Они указывают на проблему взаимодействия, которую можно безопасно обработать путем прерывания работы клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и создания сообщения о сбое взаимодействия. Поскольку внешние факторы могут вызывать появление таких ошибок в любом приложении, правильно разработанные приложения должны перехватывать эти исключения и предпринимать соответствующие восстановительные меры.  
  
 Имеется несколько классов, производных от `CommunicationException`, которые могут создаваться клиентом. В некоторых случаях приложение может также перехватывать определенные исключения, чтобы выполнять специальную обработку, и обрабатывать оставшиеся исключения как исключения типа `CommunicationException`. Чтобы реализовать это, необходимо в первую очередь перехватывать более узкие виды исключений, а лишь затем перехватывать исключение `CommunicationException` в более позднем предложении catch.  
  
 Код, вызывающий методы взаимодействия, должен перехватывать исключения `TimeoutException` и `CommunicationException`. Один из способов обработки таких ошибок заключается в прерывании работы клиента и создании сообщения о сбое взаимодействия.  
  
```  
try  
{  
    ...  
    double result = client.Add(value1, value2);  
    ...  
    client.Close();  
}  
catch (TimeoutException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
catch (CommunicationException exception)  
{  
    Console.WriteLine("Got {0}", exception.GetType());  
    client.Abort();  
}  
```  
  
 Если происходит ожидаемое исключение, клиент может стать или не стать непригодным к использованию в дальнейшем. Чтобы определить, можно ли использовать клиент, проверьте, что свойство `State` имеет значение `CommunicationState`.Opened. Если свойство имеет значение Opened, клиент можно использовать. В противном случае необходимо прервать работу клиента и освободить все ссылки на него.  
  
> [!CAUTION]
>  Можно заметить, что клиенты с сеансом невозможно использовать после возникновения исключения, а клиенты без сеансов использовать после исключения можно. Однако это не является универсальным правилом, поэтому если требуется продолжать использовать клиент после исключения, приложение должно проверить значение свойства `State`, чтобы убедиться, что клиент еще открыт.  
  
 При выполнении образца ответы и исключения операций отображаются в окне консоли клиента.  
  
 Клиентский процесс выполняет два сценария, каждый из которых пытается выполнить операцию `Add`, а затем операцию `Divide`. Первый сценарий имитирует сбой в работе сети путем прерывания работы клиента перед вызовом `Divide`. Второй сценарий вызывает возникновение таймаута путем задания слишком короткого времени ожидания завершения метода. Ниже представлен ожидаемый результат выполнения клиентского процесса.  
  
```  
Add(100,15.99) = 115.99  
Simulated network problem occurs...  
Got System.ServiceModel.CommunicationObjectAbortedException  
Add(100,15.99) = 115.99  
Set timeout too short for method to complete...  
Got System.TimeoutException  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ExpectedExceptions`  
  
## <a name="see-also"></a>См. также
