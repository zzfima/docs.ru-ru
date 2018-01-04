---
title: "Вложенные объекты TransactionScope в службе"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1c4e51f65df010f466f43c2018d9b1eec6e4ca58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="nesting-of-transactionscope-within-a-service"></a>Вложенные объекты TransactionScope в службе
Этот образец состоит из двух сценариев, при выполнении показывающих, как обрабатывать экземпляры действий <xref:System.Activities.Statements.TransactionScope> в службе. Сначала запускается транзакция с использованием действия <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции на клиенте и объекта <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения транзакции и определения времени ее существования на сервере. Первый сценарий в службе выполняет вторичное действие <xref:System.Activities.Statements.TransactionScope> для демонстрации вложения действий <xref:System.Activities.Statements.TransactionScope> в службе. Второй сценарий показывает, как соблюдаются времена ожиданий во вложенных действиях <xref:System.Activities.Statements.TransactionScope>.  
  
## <a name="client-application"></a>Клиентское приложение  
 Клиентское приложение выполняет рабочий процесс, запускающий действие <xref:System.Activities.Statements.TransactionScope>, выводит на печать идентификатор распределенной транзакции, отсылает сообщение на сервер, передает транзакцию, получает ответ, снова выводит на печать идентификатор распределенной транзакции и завершает свою работу. Данный порядок операций осуществляется один раз для каждого сценария службы.  
  
## <a name="server-application"></a>Серверное приложение  
 Проект сервера размещается на узле <xref:System.ServiceModel.Activities.WorkflowServiceHost>, создающем конечную точку, прослушивающую сообщения от клиента. Рабочий процесс центрирован относительно действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>, которое получает переданное сообщение от клиента, выводит на печать идентификатор распределенной транзакции, а затем выполняет второе действие <xref:System.Activities.Statements.TransactionScope>. В первом сценарии транзакция завершена успешно. Во втором сценарии текст действия <xref:System.Activities.Statements.TransactionScope> имеет пятисекундную задержку, а время ожидания для транзакции составляет две секунды. Когда истекает время ожидания транзакции, транзакция прерывается.  
  
#### <a name="to-run-the-sample"></a>Выполнение образца  
  
1.  Откройте решение TransactionServiceExample.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите клавиши CTRL + SHIFT + B или выберите **построить решение** из **построения** меню.  
  
3.  После успешного построения щелкните решение правой кнопкой мыши и выберите **назначить запускаемые проекты**. В диалоговом окне выберите **несколько запускаемых проектов** и убедитесь, что для обоих проектов задано действие **запустить**.  
  
4.  Нажмите клавишу F5 или выберите **начать отладку** из **отладки** меню. Кроме того, нажмите клавиши CTRL + F5 или выберите **Запуск без отладки** из **отладки** меню для запуска без отладки.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Transactions\TRSComposability`
