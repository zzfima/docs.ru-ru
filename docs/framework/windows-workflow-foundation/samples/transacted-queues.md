---
title: Транзакционные очереди
ms.date: 03/30/2017
ms.assetid: b1b011dd-5e0b-482c-9bb0-9d8727038f14
ms.openlocfilehash: b125158a113079d87eb6926393d5a2b5fe326824
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transacted-queues"></a>Транзакционные очереди
В этом примере показано, как объединить очереди и транзакции в Windows Workflow Foundation (WF) для создания надежные и масштабируемые службы. Объект <!--zz <xref:System.Activities.TransactionScope>--> `System.Activities.TransactionScope` используется в рабочем потоке клиента для отправки сообщения в очередь в рамках транзакции с использованием <xref:System.ServiceModel.NetMsmqBinding>. Область <xref:System.ServiceModel.Activities.TransactedReceiveScope> используется на сервере для получения сообщений из очереди и обновления состояния рабочего процесса в рамках той же транзакции.  
  
## <a name="demonstrates"></a>Демонстрации  
 Объекты <xref:System.Activities.Statements.TransactionScope>, <xref:System.ServiceModel.Activities.TransactedReceiveScope>, <xref:System.ServiceModel.NetMsmqBinding>, <xref:System.ServiceModel.Activities.Receive>, а также корреляция на основе содержимого.  
  
## <a name="discussion"></a>Обсуждение  
 Для демонстрации функциональности, рассматриваемой в этом образце, создается служба рабочего процесса `RewardsPoints`, которая следит за точками, приобретенными и используемыми для данной учетной записи. Клиент использует <xref:System.Activities.WorkflowInvoker> для моделирования вывода различных запросов в очередь. Для вывода сообщения в очередь в рамках транзакции действие <xref:System.ServiceModel.Activities.Send> может быть помещено в тело <xref:System.Activities.Statements.TransactionScope.Body%2A> области <xref:System.Activities.Statements.TransactionScope>. В этом образце сначала запускается клиент, а затем сервер, что позволяет показать, как обеспечить развязку клиентских и серверных приложений с помощью сообщений, поставленных в очередь.  
  
 После завершения работы клиента служба настраивается и размещается. Как только служба открывается, она начинает обработку сообщений, которые были уже помещены в очередь. Получение и обработка каждого сообщения происходит в рамках одной и той же серверной транзакции. В этом образце первым полученным сообщением является запрос `CreateAccount`, который создает экземпляр и инициализирует корреляцию содержимого на основе имени учетной записи, переданной как часть сообщения запроса. Для моделирования разновидности службы, которая могла бы встретиться в реальном мире, ниже приведены два действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>, которые обрабатывают сообщения `AddPoints` и `UsePoints`, помещенные в параллельные ветви цикла `while`, чтобы с их помощью можно было неоднократно обрабатывать указанные сообщения в любом порядке.  
  
 <xref:System.Activities.Statements.TransactionScope>и <xref:System.ServiceModel.Activities.TransactedReceiveScope> имеют Неявная точка сохранения в конце своей области, поэтому использование этих действий в [!INCLUDE[wf1](../../../../includes/wf1-md.md)] в сочетании с очередями – надежный способ перемещения рабочего процесса из одного состояния к другому, гарантируя, что сообщения, никогда не теряются.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Установите и настройте MSMQ. В разделе [Установка очереди сообщений](http://go.microsoft.com/fwlink/?LinkId=178526) подробные сведения.  
  
2.  Убедитесь, что MSDTC работает, выполнив следующую команду в командной строке. `net start msdtc`  
  
3.  Скомпилируйте проект и откройте исполняемый файл или откройте проект в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] и выберите параметр запуска в меню "Отладка". Сначала создается очередь, затем запускается клиент и выводит сообщения в очередь, и, наконец, запускается служба, и производится обработка сообщений. Чтобы выйти из программы, нажмите клавишу ВВОД.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов. Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedQueues`
