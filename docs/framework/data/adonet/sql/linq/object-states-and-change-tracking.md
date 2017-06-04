---
title: "Состояния объектов и отслеживание изменений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Состояния объектов и отслеживание изменений
Объекты [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] всегда находятся в каком\-либо *состоянии*.  Например, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объект, объект находится в состоянии `Unchanged`.  Новый объект, создаваемый пользователем, неизвестен <xref:System.Data.Linq.DataContext> и находится в состоянии `Untracked`.  После успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> все объекты, известные [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], находятся в состоянии `Unchanged`.  \(Единственное исключение представляют объекты, успешно удаленные из базы данных, находящиеся в состоянии `Deleted` и не используемые в экземпляре <xref:System.Data.Linq.DataContext>.\)  
  
## Состояния объектов  
 В следующей таблице представлены возможные состояния объектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Состояние|Описание|  
|---------------|--------------|  
|`Untracked`|Объект, не отслеживаемый [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  Далее представлено несколько примеров.<br /><br /> -   Объект, не запрошенный с помощью текущего <xref:System.Data.Linq.DataContext> \(например, недавно созданный объект\).<br />-   Объект, созданный с помощью сериализации<br />-   Объект, запрошенный с помощью другого <xref:System.Data.Linq.DataContext>.|  
|`Unchanged`|Объект, извлеченный с использованием текущего <xref:System.Data.Linq.DataContext> и не измененный после создания.|  
|`PossiblyModified`|Объект, который *присоединен* к <xref:System.Data.Linq.DataContext>.  Для получения дополнительной информации см. [Получение данных и операции CUD в многоуровневых приложениях \(LINQ to SQL\)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|  
|`ToBeInserted`|Объект, который не был извлечен с использованием текущего <xref:System.Data.Linq.DataContext>.  Это приводит к `INSERT` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeUpdated`|Объект, известный для изменения после извлечения.  Это приводит к `UPDATE` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeDeleted`|Объект, помеченный для удаления и вызывающий `DELETE` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`Deleted`|Объект, удаленный в базе данных.  Это состояние является завершающим и не допускает дополнительных переходов.|  
  
## Вставка объектов  
 Используя <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>, можно явным образом запросить `Inserts`.  В качестве альтернативы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] может определить `Inserts`, выполнив поиск объектов, которые подключены к одному из известных объектов, подлежащих обновлению.  Например, если объект `Untracked` добавляется к <xref:System.Data.Linq.EntitySet%601> или для объекта `Untracked` устанавливается <xref:System.Data.Linq.EntityRef%601>, объект `Untracked` он становится доступным за счет отслеживаемых объектов в графике.  Во время обработки <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проходит через отслеживаемые объекты и находит неотслеженные доступные постоянные объекты.  Такие объекты являются кандидатами на вставку в базу данных.  
  
 Для классов в иерархии наследования <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>\(`o`\) также задает значение члена, назначенного в качестве *дискриминатора*, для соответствия типу объекта `o`.  Если тип совпадает со значением дискриминатора по умолчанию, данное значение переопределяет значение дискриминатора.  Для получения дополнительной информации см. [Поддержка наследования](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
> [!IMPORTANT]
>  Объект, добавляемый в `Table` не является кэшем идентификации.  Кэш идентификации отражает только данные, извлеченные из базы данных.  После вызова <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> добавленная сущность не отображается в запросах к базе данных до успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## Удаление объектов  
 Отслеживаемый объект `o` помечается для удаления путем вызова метода <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>\(o\) для соответствующей таблицы <xref:System.Data.Linq.Table%601>.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] рассматривает удаление объекта из набора <xref:System.Data.Linq.EntitySet%601> как операцию обновления, поэтому соответствующий внешний ключ устанавливается в значение NULL.  Результат операции \(`o`\) из таблицы не удаляется.  Например, `cust.Orders.DeleteOnSubmit(ord)` означает обновление, где для разрыва связи между `cust` и `ord` внешнему ключу `ord.CustomerID` задается значение NULL.  При этом строка, соответствующая `ord`, не удаляется.  
  
 При удалении объекта из таблицы \(<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>\) [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняет следующий процесс.  
  
-   При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для объекта выполняется операция `DELETE`.  
  
-   Удаление не отражается на связанных объектах независимо от того, загружены они или нет.  В частности, связанные объекты не загружаются для обновления свойства связи.  
  
-   После успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> все объекты переходят в состояние `Deleted`.  В результате объект или его `id` не могут использоваться в данном <xref:System.Data.Linq.DataContext>.  Внутренний кэш, поддерживаемый экземпляром <xref:System.Data.Linq.DataContext>, не удаляет объекты, извлеченные или добавленные в качестве новых, даже если они были удалены в базе данных.  
  
 Метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> можно вызвать только в объекте, отслеживаемом с помощью <xref:System.Data.Linq.DataContext>.  Для объекта `Untracked` метод <xref:System.Data.Linq.Table%601.Attach%2A> необходимо вызвать до вызова <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>.  При вызове метода <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> в объекте `Untracked` создается исключение.  
  
> [!NOTE]
>  При удалении объекта из таблицы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] получает указание создать соответствующую команду SQL `DELETE` в момент вызова <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  Это действие не приводит к удалению объекта из кэша статьи и не распространяется на удаление связанных объектов.  
>   
>  Чтобы освободить `id` удаленного объекта, воспользуйтесь новым экземпляром <xref:System.Data.Linq.DataContext>.  Для очистки связанных объектов можно использовать функцию *каскадного удаления* или удалить данные объекты вручную.  
>   
>  Связанные объекты можно удалять в произвольном порядке \(в отличие от базы данных\).  
  
## Обновление объектов  
 `Updates` можно обнаружить, просматривая уведомления об изменениях.  Уведомления предоставляются с помощью события <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> в методах задания свойств.  Когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] получает уведомление о первом изменении объекта, он создает копию объекта и рассматривает объект в качестве кандидата для создания оператора `Update`.  
  
 Для объектов, которые не реализуют <xref:System.ComponentModel.INotifyPropertyChanging>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сохраняет копию значений, которые были у объектов при первой материализации.  При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сравнивает текущие и исходные значения и делает вывод об изменении объекта.  
  
 При обновлении связей ссылка из дочернего элемента на родительский \(то есть ссылка, соответствующая внешнему ключу\) считается ведущей.  Ссылка в обратном направлении \(то есть из родительского элемента на дочерний\) является необязательной.  Классы отношений \(<xref:System.Data.Linq.EntitySet%601> и <xref:System.Data.Linq.EntityRef%601>\) гарантируют непротиворечивость двунаправленных ссылок для отношений "один\-ко\-многим" и "один\-к\-одному".  Если в объектной модели не используется <xref:System.Data.Linq.EntitySet%601> или <xref:System.Data.Linq.EntityRef%601> и если имеется обратная ссылка, то при обновлении связей необходимо сохранить ее согласованность с прямой ссылкой.  
  
 При обновлении необходимой ссылки и соответствующего внешнего ключа следует обеспечить их непротиворечивость.  Если на момент вызова <xref:System.Data.Linq.DataContext.SubmitChanges%2A> эти объекты не синхронизированы, создается исключение <xref:System.InvalidOperationException>.  Несмотря на то, что изменения значения внешнего ключа достаточны для воздействия на обновление базовой строки, необходимо изменить ссылку, чтобы сохранить подключение графа объекта и обеспечить двунаправленную согласованность связей.  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Операции вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)