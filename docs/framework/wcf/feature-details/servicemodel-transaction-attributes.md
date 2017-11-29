---
title: "Атрибуты транзакции ServiceModel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: transactions [WCF], ServiceModel attributes
ms.assetid: 1e0d2436-6ae5-439b-9765-a448d6f60000
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4857c6e9f77e8cf201c47814405e4db9f08ae2d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="servicemodel-transaction-attributes"></a>Атрибуты транзакции ServiceModel
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] предоставляет свойства в трех стандартных атрибутах <xref:System.ServiceModel>, которые позволяют настроить поведение транзакций для службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:  
  
-   <xref:System.ServiceModel.TransactionFlowAttribute>  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute>  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute>  
  
## <a name="transactionflowattribute"></a>TransactionFlowAttribute  
 Атрибут <xref:System.ServiceModel.TransactionFlowAttribute> указывает готовность операции в контракте службы к приему входящих транзакций от клиента. Атрибут снабжает данный элемент управления следующим свойством: в транзакциях используется перечисление <xref:System.ServiceModel.TransactionFlowOption> для указания того, является входящая транзакция <xref:System.ServiceModel.TransactionFlowOption.Mandatory>, <xref:System.ServiceModel.TransactionFlowOption.Allowed> или <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.  
  
 Это единственный атрибут, связывающий операции службы с внешним взаимодействием с клиентом. Атрибуты, описанные в следующих разделах, связаны с использованием транзакций в рамках выполнения операции.  
  
## <a name="servicebehaviorattribute"></a>ServiceBehaviorAttribute  
 Атрибут <xref:System.ServiceModel.ServiceBehaviorAttribute> задает поведение внутреннего выполнения реализации контракта службы. Из свойств этого атрибута к транзакциям относятся следующие.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionAutoCompleteOnSessionClose%2A> указывает, завершать ли незавершенную транзакцию при закрытии сеанса. Значение по умолчанию для этого свойства — `false`. Если это свойство имеет значение `true` и входящий сеанс был закрыт корректно, а не по причине ошибок сети или клиента, любая незавершенная транзакция успешно завершается. В противном случае, если свойство имеет значение `false` или если сеанс был закрыт некорректно, любая незавершенная транзакция при закрытии сеанса откатывается. Если свойство имеет значение `true`, входящий канал должен быть основан на сеансах.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A> указывает, освобождать ли базовый экземпляр службы при завершении транзакции. Значение по умолчанию для этого свойства — `true`. При поступлении следующего входящего сообщения создается новый базовый экземпляр, и любое записанное в предыдущий экземпляр связанное с транзакцией состояние сбрасывается. Освобождение экземпляра службы - это внутреннее предпринимаемое службой действие, которое не затрагивает никакие существующие подключения или сеансы, установленные клиентами. Эта функциональность эквивалентна JIT-активации, обеспечиваемой COM+. Если свойство имеет значение `true`, свойство <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> должно быть равно <xref:System.ServiceModel.ConcurrencyMode.Single>. В противном случае при запуске служба вызывает исключение проверки "недопустимая конфигурация".  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A> задает уровень изоляции, используемый для транзакций в рамках службы; это свойство принимает одно из значений перечисления <xref:System.Transactions.IsolationLevel>. Если локальное свойство уровня изоляции имеет значение, отличное от <xref:System.Transactions.IsolationLevel.Unspecified>, уровень изоляции входящей транзакции должен соответствовать значению этого локального свойства. В противном случае входящая транзакция отклоняется, и клиенту отправляется ошибка. Если свойство <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> имеет значение `true` и нет поточных транзакций, это свойство определяет значение перечисления <xref:System.Transactions.IsolationLevel>, которое будет использоваться для локально созданной транзакции. Если <xref:System.Transactions.IsolationLevel> имеет значение <xref:System.Transactions.IsolationLevel.Unspecified>, используется значение <xref:System.Transactions.IsolationLevel> перечисления <xref:System.Transactions.IsolationLevel.Serializable>.  
  
-   <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> задает период времени, в течение которого созданная в службе новая транзакция должна быть завершена. Если по истечении этого времени транзакция не завершена, она будет прервана. Структура <xref:System.TimeSpan> используется в качестве времени ожидания <xref:System.Transactions.TransactionScope> для любых операций, у которых свойству <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> присвоено значение `true` и для которых была создана новая транзакция. Время ожидания - это максимально допустимый промежуток от создания транзакции до завершения фазы 1 в протоколе двухфазной фиксации. В качестве времени ожидания всегда используется меньшее из значений свойства <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionTimeout%2A> и параметра конфигурации `transactionTimeout`.  
  
## <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute  
 Атрибут <xref:System.ServiceModel.OperationBehaviorAttribute> задает расширения функциональности методов в реализации службы. Его можно использовать для задания конкретного поведения выполнения операции. Свойства этого атрибута не влияют на описание контракта службы на языке WSDL и представляют собой исключительно элементы модели программирования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], обеспечивающие стандартные функции, которые разработчикам в противном случае пришлось бы реализовывать самостоятельно.  
  
 Этот атрибут имеет следующие относящиеся к транзакциям свойства.  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> указывает, должен ли метод выполняться в области активной транзакции. Значение по умолчанию — `false`. Если для метода не задан атрибут <xref:System.ServiceModel.OperationBehaviorAttribute>, это также подразумевает, что метод не будет выполняться в транзакции. Если для операции не требуется область транзакции, любая транзакция, присутствующая в заголовке сообщения, не активируется и остается элементом свойства <xref:System.ServiceModel.OperationContext.IncomingMessageProperties%2A> класса <xref:System.ServiceModel.OperationContext>. Если для операции требуется область транзакции, источник транзакции определяется одним из следующих способов.  
  
    -   Если транзакция передается в потоке от клиента, метод выполняется в области транзакции, созданной с использованием этой распределенной транзакции.  
  
    -   При транспорте по принципу очереди используется транзакция, которая использовалась для удаления сообщения из очереди. Обратите внимание, что используемая транзакция не является поточной транзакцией, т. е. она не была предоставлена исходным отправителем сообщения.  
  
    -   Пользовательский транспорт может предоставить транзакцию посредством использования свойства `TransportTransactionProperty`.  
  
    -   Если внешний источник транзакции не задается ничем из перечисленного, непосредственно перед вызовом метода создается новый экземпляр <xref:System.Transactions.Transaction>.  
  
-   <xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A> указывает, следует ли автоматически завершать транзакцию, в которой выполняется метод, при отсутствии необработанных исключений. Если это свойство имеет значение `true`, вызывающая инфраструктура автоматически помечает транзакцию как завершенную, если пользовательский метод возвращается без вызова исключения. Если свойство имеет значение `false`, транзакция присоединяется к экземпляру и помечается как завершенная, только если клиент вызывает следующий метод, у которого это свойство равно `true`, или если следующий метод явно вызывает метод <xref:System.ServiceModel.OperationContext.SetTransactionComplete%2A>. Если ни одно из этих условий не выполняется, транзакция не будет считаться завершенной, и содержащиеся в ней данные не будут зафиксированы, за исключением случая, когда свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionAutoCompleteOnSessionClose%2A> присвоено значение `true`. Если этому свойству присвоено значение `true`, в сеансе необходимо использовать канал, и свойству <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> должно быть присвоено значение <xref:System.ServiceModel.InstanceContextMode.PerSession>.
