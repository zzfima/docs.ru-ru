---
title: "Область сопровождения транзакции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37141708-a29f-4b6a-81fe-f8a11f825061
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 854e04c53bf438c3356072d762f129b7f21b7dd5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="transaction-convoy-scope"></a>Область сопровождения транзакции
В этом образце демонстрируется создание шаблона обмена сообщениями Parallel Convoy совместно с <xref:System.ServiceModel.Activities.TransactedReceiveScope> для моделирования протокола, при котором несколько операций могут выполняться в любом порядке в рамках одной транзакции. Также в этом образце показано, как класс <xref:System.ServiceModel.Activities.TransactedReceiveScope> автоматически создает новую транзакцию, если транзакция не была передана серверу, и клиент не смог воспользоваться какими-либо транзакциями.  
  
 Образец включает два проекта рабочих процессов, которые представляют клиент и сервер. Проект клиента запускает рабочий процесс, который начинается с отправки сообщения для загрузки рабочего процесса сервера, инициализирующего корреляцию и область транзакций для оставшихся действий по отправке и получению сообщений. Клиентское действие <xref:System.Activities.Statements.Sequence> содержит исходную пару <xref:System.ServiceModel.Activities.Send> и <xref:System.ServiceModel.Activities.ReceiveReply> и далее - действие <xref:System.Activities.Statements.Parallel> с тремя ответвлениями. Каждое ответвление отправляет на сервер одностороннее сообщение. Свойство <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> действия <xref:System.Activities.Statements.Parallel> устанавливается в значение `false`, таким образом, выполняются все три ответвления.  
  
 Серверный рабочий процесс похож на клиентский рабочий процесс, за исключением действий отправки и получения сообщений, которые направлены в сторону сервера и содержатся в действии <xref:System.ServiceModel.Activities.TransactedReceiveScope>, за счет чего вся работа выполняется в одной транзакции. Когда сервер получает первое сообщение, создается транзакция, которая становится внешней для области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, благодаря чему любое действие в этой области может получить доступ к транзакции. После этого все действия получения выполняются параллельно. Все действия получения должны быть выполнены строго один раз, в соответствии с условием завершения для параллельного действия. Неявная точка сохранения существует в конце области <xref:System.ServiceModel.Activities.TransactedReceiveScope>, при этом операция сохранения также выполняется в рамках той же транзакции.  
  
#### <a name="to-use-this-sample"></a>Использование этого образца  
  
1.  Откройте файл решения ParallelConvoySample.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Для построения решения нажмите CTRL+SHIFT+B.  
  
3.  Убедитесь, что оба проекта готовы к запуску.  
  
    1.  В **обозревателе решений**, щелкните правой кнопкой мыши решение и выберите **назначить запускаемые проекты**.  
  
    2.  Выберите **несколько запускаемых проектов** и убедитесь, что для обоих проектов задано действие **запустить**.  
  
4.  Чтобы запустить решение, нажмите клавиши CTRL+F5.  
  
     Сервер отобразит сообщение `Server is running`, указывающее, что сервер готов.  
  
     Нажмите любую клавишу в окне консоли клиента, чтобы запустить образец.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Transactions\TransactedConvoyScope`