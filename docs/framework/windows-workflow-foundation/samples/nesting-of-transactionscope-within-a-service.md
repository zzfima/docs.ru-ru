---
title: "Вложенные объекты TransactionScope в службе | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e7e1ba64-1384-4eba-add8-415636e2d6d0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Вложенные объекты TransactionScope в службе
Этот образец состоит из двух сценариев, при выполнении показывающих, как обрабатывать экземпляры действий <xref:System.Activities.Statements.TransactionScope> в службе.Сначала запускается транзакция с использованием действия <xref:System.Activities.Statements.TransactionScope> для создания новой транзакции на клиенте и объекта <xref:System.ServiceModel.Activities.TransactedReceiveScope> для получения транзакции и определения времени ее существования на сервере.Первый сценарий в службе выполняет вторичное действие <xref:System.Activities.Statements.TransactionScope> для демонстрации вложения действий <xref:System.Activities.Statements.TransactionScope> в службе.Второй сценарий показывает, как соблюдаются времена ожиданий во вложенных действиях <xref:System.Activities.Statements.TransactionScope>.  
  
## Клиентское приложение  
 Клиентское приложение выполняет рабочий процесс, запускающий действие <xref:System.Activities.Statements.TransactionScope>, выводит на печать идентификатор распределенной транзакции, отсылает сообщение на сервер, передает транзакцию, получает ответ, снова выводит на печать идентификатор распределенной транзакции и завершает свою работу.Данный порядок операций осуществляется один раз для каждого сценария службы.  
  
## Серверное приложение  
 Проект сервера размещается на узле <xref:System.ServiceModel.Activities.WorkflowServiceHost>, создающем конечную точку, прослушивающую сообщения от клиента.Рабочий процесс центрирован относительно действия <xref:System.ServiceModel.Activities.TransactedReceiveScope>, которое получает переданное сообщение от клиента, выводит на печать идентификатор распределенной транзакции, а затем выполняет второе действие <xref:System.Activities.Statements.TransactionScope>.В первом сценарии транзакция завершена успешно.Во втором сценарии текст действия <xref:System.Activities.Statements.TransactionScope> имеет пятисекундную задержку, а время ожидания для транзакции составляет две секунды.Когда истекает время ожидания транзакции, транзакция прерывается.  
  
#### Выполнение образца  
  
1.  Откройте решение TransactionServiceExample.sln в [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Чтобы построить решение, нажмите сочетание клавиш CTRL\+SHIFT\+B или выберите команду **Построить решение** в меню **Построение**.  
  
3.  После успешного построения щелкните решение правой кнопкой мыши и выберите команду **Назначить запускаемые проекты**.В диалоговом окне выберите вариант **Несколько запускаемых проектов** и убедитесь, что для обоих проектов задано действие **Запустить**.  
  
4.  Нажмите клавишу F5 или выберите команду **Начать отладку** в меню **Отладка**.Также можно нажать клавиши CTRL\+F5 или выбрать команду **Запуск без отладки** в меню **Отладка**, чтобы запустить выполнение без отладки.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Basic\Transactions\TRSCompostability`