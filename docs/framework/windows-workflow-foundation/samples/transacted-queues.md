---
title: "Транзакционные очереди"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b1b011dd-5e0b-482c-9bb0-9d8727038f14
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2373d4d7bec73b6f517c7bd3dfeeb4c26edf7d5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="transacted-queues"></a>Транзакционные очереди
Этот образец показывает, как объединить очереди и транзакции в [!INCLUDE[wf](../../../../includes/wf-md.md)], чтобы создать надежные и масштабируемые службы. Объект <!--zz <xref:System.Activities.TransactionScope>--> `System.Activities.TransactionScope` используется в рабочем потоке клиента для отправки сообщения в очередь в рамках транзакции с использованием <xref:System.ServiceModel.NetMsmqBinding>. Область <xref:System.ServiceModel.Activities.TransactedReceiveScope> используется на сервере для получения сообщений из очереди и обновления состояния рабочего процесса в рамках той же транзакции.  
  
## <a name="demonstrates"></a>Демонстрации  
 Объекты <xref:System.Activities.Statements.TransactionScope>, <xref:System.ServiceModel.Activities.TransactedReceiveScope>, <xref:System.ServiceModel.NetMsmqBinding>, <xref:System.ServiceModel.Activities.Receive>, а также корреляция на основе содержимого.  
  
## <a name="discussion"></a>Обсуждение  
 Для демонстрации функциональности, рассматриваемой в этом образце, создается служба рабочего процесса `RewardsPoints`, которая следит за точками, приобретенными и используемыми для данной учетной записи.. Клиент использует <xref:System.Activities.WorkflowInvoker> для моделирования вывода различных запросов в очередь. Для вывода сообщения в очередь в рамках транзакции действие <xref:System.ServiceModel.Activities.Send> может быть помещено в тело <xref:System.Activities.Statements.TransactionScope.Body%2A> области <xref:System.Activities.Statements.TransactionScope>. В этом образце сначала запускается клиент, а затем сервер, что позволяет показать, как обеспечить развязку клиентских и серверных приложений с помощью сообщений, поставленных в очередь.  
  
 После завершения работы клиента служба настраивается и размещается. Как только служба открывается, она начинает обработку сообщений, которые были уже помещены в очередь. Получение и обработка каждого сообщения происходит в рамках одной и той же серверной транзакции. В этом образце первым полученным сообщением является запрос `CreateAccount`, который создает экземпляр и инициализирует корреляцию содержимого на основе имени учетной записи, переданной как часть сообщения запроса. Для моделирования разновидности службы, которая могла бы встретиться в реальном мире, ниже приведены два действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>, которые обрабатывают сообщения `AddPoints` и `UsePoints`, помещенные в параллельные ветви цикла `while`, чтобы с их помощью можно было неоднократно обрабатывать указанные сообщения в любом порядке.  
  
 Каждый из объектов <xref:System.Activities.Statements.TransactionScope> и <xref:System.ServiceModel.Activities.TransactedReceiveScope> имеет неявную точку сохраняемости в конце своей области, поэтому использование этих действий в [!INCLUDE[wf1](../../../../includes/wf1-md.md)] в сочетании с очередями представляет собой надежный способ перемещения рабочего процесса из одного согласованного состояния в следующее с гарантией того, что сообщения никогда не потеряются.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Установите и настройте MSMQ. В разделе [Установка очереди сообщений](http://go.microsoft.com/fwlink/?LinkId=178526) подробные сведения.  
  
2.  Убедитесь, что MSDTC работает, выполнив следующую команду в командной строке. `net start msdtc`  
  
3.  Откомпилируйте проект и откройте исполняемый файл или откройте проект в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и выберите параметр запуска в меню отладки. Сначала создается очередь, затем запускается клиент и выводит сообщения в очередь, и, наконец, запускается служба, и производится обработка сообщений. Чтобы выйти из программы, нажмите клавишу ВВОД.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedQueues`
