---
title: "Как создать настраиваемого участника сохраняемости | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Как создать настраиваемого участника сохраняемости
В следующей процедуре содержаться шаги для создания участника сохраняемости.Реализацию образцов участников сохраняемости см. в образце [Участие в сохраняемости](http://go.microsoft.com/fwlink/?LinkID=177735) и в разделе [Расширяемость хранилища](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
1.  Создайте класс, который происходит от класса <xref:System.Activities.Persistence.PersistenceParticipant> или <xref:System.Activities.Persistence.PersistenceIOParticipant>.Класс PersistenceIOParticipant предлагает те же самые точки расширяемости, что и класс PersistenceParticipant, при этом он может принимать участие в операциях ввода\-вывода данных.Выполните один или несколько следующих шагов.  
  
2.  Выполните метод <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.Метод **CollectValues** содержит два словарных параметра, один для хранения значений «запись\-чтение» и другой для хранения значений «только запись» \(используемых в дальнейшем в запросах\).В этом методе необходимо заполнить словари данными, соответствующими участнику сохраняемости.Каждый словарь содержит имя значения в качестве ключа и само значение в качестве объекта <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
     Значения в словаре readWriteValues упаковываются в виде объектов **InstanceValue**.Значения в словаре типа «только запись» упаковываются в виде объектов **InstanceValue** с заданными параметрами InstanceValueOptions.Optional и InstanceValueOption.WriteOnly.Каждый объект **InstanceValue**, обеспечиваемый реализацией **CollectValues** для всех участников сохраняемости, должен иметь уникальное имя.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
  
    ```  
  
3.  Выполните метод <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>.Метод **MapValues** получает два параметра, схожих с параметрами, получаемыми методом **CollectValues**.Все значения, собранные на этапе **CollectValues**, передаются посредством этих словарных параметров.Новые значения, добавленные на этапе **MapValues**, добавляются как значения типа «только запись».Доступный только для записи словарь используется для передачи данных во внешний источник данных, не связанный напрямую со значениями экземпляра.Каждое значение, предоставляемое реализацией метода **MapValues** для всех участников сохраняемости, должно иметь уникальное имя.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Метод <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> предоставляет функциональность, не реализуемую <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>, а именно допускает зависимость от другого значения, предоставленного другим участником сохраняемости, который еще не был обработан <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.  
  
4.  Реализуйте метод **PublishValues**.Метод **PublishValues** получает словарь, содержащий все значения, загруженные из хранилища сохраняемости.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
  
    ```  
  
5.  Реализуйте метод **BeginOnSave**, если участник является участником ввода\-вывода значений сохраняемости.Метод вызывается во время создания сохранения.В этом методе необходимо выполнить дополнительные операции ввода\-вывода при сохранении экземпляров рабочих процессов.Если узел использует транзакцию для соответствующей команды сохраняемости, та же самая транзакция используется в Transaction.Current.Помимо этого, PersistenceIOParticipants могут объявить о требовании к совместимости транзакций, в случае чего узел создаст транзакцию для сеанса сохраняемости, если такая транзакция не будет использована иначе.  
  
    ```  
  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  Реализуйте метод **BeginOnLoad**, если участник выполняет также операции ввода\-вывода.Метод вызывается во время создания загрузки.В этом методе необходимо выполнить дополнительные операции ввода\-вывода при загрузке экземпляров рабочих процессов.Если узел использует транзакцию для соответствующей команды сохраняемости, та же самая транзакция используется в Transaction.Current.Помимо этого, участники ввода\-вывода данных сохраняемости могут объявить о требовании к совместимости транзакций, в случае чего узел создаст транзакцию для сеанса сохраняемости, если такая транзакция не будет использована иначе.  
  
    ```  
  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
  
    ```