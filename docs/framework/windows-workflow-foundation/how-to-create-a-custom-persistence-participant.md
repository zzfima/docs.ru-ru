---
title: Как создать настраиваемого участника сохраняемости
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: 8daf4924db48c79486e85660357e3b28a2583836
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "43855846"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Как создать настраиваемого участника сохраняемости
В следующей процедуре содержаться шаги для создания участника сохраняемости. См. в разделе [участие в сохраняемости](https://go.microsoft.com/fwlink/?LinkID=177735) пример и [расширяемости Store](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) разделе Примеры реализации участников сохраняемости.  
  
1.  Создайте класс, который происходит от класса <xref:System.Activities.Persistence.PersistenceParticipant> или <xref:System.Activities.Persistence.PersistenceIOParticipant>. Класс PersistenceIOParticipant предлагает же точки расширяемости, что класс PersistenceParticipant, кроме того, что может участвовать в операциях ввода-вывода. Выполните один или несколько следующих шагов.  
  
2.  Выполните метод <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. **CollectValues** метод имеет два словарных параметра, один для хранения значений для чтения и записи и другой для хранения только для записи значений (используется в дальнейшем в запросах). В этом методе необходимо заполнить словари данными, соответствующими участнику сохраняемости. Каждый словарь содержит имя значения в качестве ключа и само значение в качестве объекта <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
     Значения в словаре readWriteValues упаковываются в виде **InstanceValue** объектов. Значения в словаре только для записи упаковываются в виде **InstanceValue** объектов с заданными параметрами InstanceValueOptions.Optional и InstanceValueOption.WriteOnly. Каждый **InstanceValue** предоставляемые **CollectValues** реализации для всех участников сохраняемости, должен иметь уникальное имя.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  Выполните метод <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. **MapValues** метод принимает два параметра, которые похожи на параметры, **CollectValues** метод получает. Все значения, собранные в **CollectValues** этап передаются посредством этих словарных параметров. Новые значения, добавленные **MapValues** этапа добавляются значения только для записи.  Доступный только на запись словарь используется для передачи данных во внешний источник данных, не связанный напрямую со значениями экземпляра. Каждого значения, предоставленные реализациями **MapValues** метод для всех участников сохраняемости, должен иметь уникальное имя.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Метод <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> предоставляет функциональность, не реализуемую <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>, а именно допускает зависимость от другого значения, предоставленного другим участником сохраняемости, который еще не был обработан <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.  
  
4.  Реализуйте **PublishValues** метод. **PublishValues** метод получает словарь, содержащий все значения, загруженные из хранилища сохраняемости.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  Реализуйте **BeginOnSave** метод, если участник является участником сохраняемости ввода-вывода. Метод вызывается во время создания сохранения. В этом методе необходимо выполнить дополнительные операции ввода-вывода для сохранения (экземпляров рабочих процессов сохранение).  Если узел использует транзакцию для соответствующей команды сохраняемости, та же самая транзакция используется в Transaction.Current.  Помимо этого, PersistenceIOParticipants могут объявить о требовании к совместимости транзакций, в случае чего узел создаст транзакцию для сеанса сохраняемости, если такая транзакция не будет использована иначе.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  Реализуйте **BeginOnLoad** метод, если участник является участником сохраняемости ввода-вывода. Метод вызывается во время создания загрузки. В этом методе необходимо выполнить дополнительные операции ввода-вывода и загрузки экземпляров рабочего процесса. Если узел использует транзакцию для соответствующей команды сохраняемости, та же самая транзакция используется в Transaction.Current. Кроме того участники ввода-вывода сохраняемости могут объявить о требовании к совместимости транзакций, в случае чего узел создаст транзакцию для сеанса сохраняемости, если один в противном случае не будут использоваться.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
