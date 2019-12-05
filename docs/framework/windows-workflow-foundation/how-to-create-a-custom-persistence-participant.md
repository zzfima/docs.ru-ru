---
title: Как создать настраиваемого участника сохраняемости
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: 0e61395cb59a7d162668445d23241e3ff562d67b
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802548"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Как создать настраиваемого участника сохраняемости
В следующей процедуре содержаться шаги для создания участника сохраняемости. Примеры реализаций участников сохраняемости см. в разделе участие в примерах использования [сохраняемости](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100)) и [сохранении расширяемости](store-extensibility.md) .  
  
1. Создайте класс, который происходит от класса <xref:System.Activities.Persistence.PersistenceParticipant> или <xref:System.Activities.Persistence.PersistenceIOParticipant>. Класс PersistenceIOParticipant предлагает те же точки расширения, что и класс PersistenceParticipant, а также возможность участвовать в операциях ввода-вывода. Выполните один или несколько следующих шагов.  
  
2. Выполните метод <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>. Метод **CollectValues** имеет два параметра словаря: один для хранения значений чтения и записи, а другой — для хранения значений только для записи (используется позднее в запросах). В этом методе необходимо заполнить словари данными, соответствующими участнику сохраняемости. Каждый словарь содержит имя значения в качестве ключа и само значение в качестве объекта <xref:System.Runtime.DurableInstancing.InstanceValue>.  
  
    Значения в словаре Реадвритевалуес упаковываются как объекты **InstanceValue** . Значения в словаре, доступном только для записи, упаковываются в объекты **InstanceValue** с Инстанцевалуеоптионс. Optional и Инстанцевалуеоптион. WriteOnly Set. Каждый **InstanceValue** , предоставляемый реализациями **CollectValues** во всех участниках сохраняемости, должен иметь уникальное имя.
  
    ```csharp  
    protected virtual void CollectValues(out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
3. Выполните метод <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>. Метод **MapValues** принимает два параметра, аналогичные параметрам, получаемым методом **CollectValues** . Все значения, собранные на этапе **CollectValues** , передаются через эти параметры словаря. Новые значения, добавленные на этапе **MapValues** , добавляются к значениям только для записи.  Доступный только на запись словарь используется для передачи данных во внешний источник данных, не связанный напрямую со значениями экземпляра. Каждое значение, предоставляемое реализациями метода **MapValues** для всех участников сохраняемости, должно иметь уникальное имя.  
  
    ```csharp  
    protected virtual IDictionary<XName,Object> MapValues(IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
     Метод <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A> предоставляет функциональность, не реализуемую <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>, а именно допускает зависимость от другого значения, предоставленного другим участником сохраняемости, который еще не был обработан <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>.  
  
4. Реализуйте метод **PublishValues** . Метод **PublishValues** получает словарь, содержащий все значения, загруженные из хранилища сохраняемости.  
  
    ```csharp  
    protected virtual void PublishValues(IDictionary<XName,Object> readWriteValues)
    {
    }
    ```  
  
5. Реализуйте метод **бегинонсаве** , если участник является участником сохраняемого ввода-вывода. Метод вызывается во время создания сохранения. В этом методе следует выполнять операции ввода-вывода дополнения в сохраняемые (сохраняемые) экземпляры рабочих процессов.  Если узел использует транзакцию для соответствующей команды сохраняемости, та же самая транзакция используется в Transaction.Current.  Помимо этого, PersistenceIOParticipants могут объявить о требовании к совместимости транзакций, в случае чего узел создаст транзакцию для сеанса сохраняемости, если такая транзакция не будет использована иначе.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnSave(IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```  
  
6. Реализуйте метод **бегинонлоад** , если участник является участником сохраняемого ввода-вывода. Метод вызывается во время создания загрузки. В этом методе следует выполнять операции ввода-вывода дополнения для загрузки экземпляров рабочего процесса. Если узел использует транзакцию для соответствующей команды сохраняемости, та же самая транзакция используется в Transaction.Current. Кроме того, участники сохраняемости ввода-вывода могут объявить о требованиях к согласованности транзакций. в этом случае узел создает транзакцию для эпизода сохраняемости, если она не используется иным образом.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnLoad(IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```
