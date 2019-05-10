---
title: Состояния объектов и отслеживание изменений
ms.date: 03/30/2017
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
ms.openlocfilehash: 704c5271f71c3709bbf48cf6a5af0a60828e6244
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610098"
---
# <a name="object-states-and-change-tracking"></a>Состояния объектов и отслеживание изменений
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] объекты всегда участвовать в некоторых *состояние*. Например, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объект, объект находится в состоянии `Unchanged`. Объект, создаваемый пользователем неизвестен <xref:System.Data.Linq.DataContext> и находится в `Untracked` состояние. После успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> все объекты, известные [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], находятся в состоянии `Unchanged`. (Единственное исключение представляют объекты, успешно удаленные из базы данных, находящиеся в состоянии `Deleted` и не используемые в экземпляре <xref:System.Data.Linq.DataContext>.)  
  
## <a name="object-states"></a>Состояния объектов  
 В следующей таблице представлены возможные состояния объектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Регион|Описание|  
|-----------|-----------------|  
|`Untracked`|Объект, не отслеживаемый [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Далее представлено несколько примеров.<br /><br /> — Объект не запрошенный с помощью текущего <xref:System.Data.Linq.DataContext> (например, вновь созданного объекта).<br />-Объект, созданный с помощью десериализации<br />— Объект запрошенный с помощью другого <xref:System.Data.Linq.DataContext>.|  
|`Unchanged`|Объект, извлеченный с использованием текущего <xref:System.Data.Linq.DataContext> и не измененный после создания.|  
|`PossiblyModified`|Объект, который *присоединенного* для <xref:System.Data.Linq.DataContext>. Дополнительные сведения см. в разделе [извлечение данных и операции CUD в N-уровневых приложениях (LINQ to SQL) и](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|  
|`ToBeInserted`|Объект, который не был извлечен с использованием текущего <xref:System.Data.Linq.DataContext>. Это приводит к `INSERT` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeUpdated`|Объект, известный для изменения после извлечения. Это приводит к `UPDATE` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`ToBeDeleted`|Объект, помеченный для удаления и вызывающий `DELETE` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|  
|`Deleted`|Объект, удаленный в базе данных. Это состояние является завершающим и не допускает дополнительных переходов.|  
  
## <a name="inserting-objects"></a>Вставка объектов  
 Используя `Inserts`, можно явным образом запросить <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>. Кроме того [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] может вывести `Inserts` путем поиска объектов, которые подключены к одному из известных объектов, которые должны быть обновлены. Например, если вы добавите `Untracked` объект <xref:System.Data.Linq.EntitySet%601> или задать <xref:System.Data.Linq.EntityRef%601> для `Untracked` объект `Untracked` он становится доступным за счет отслеживаемых объектов в графе. При обработке <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] проходит через отслеживаемые объекты и обнаруживает все постоянные достижимых объектов, которые не отслеживаются. Такие объекты являются кандидатами на вставку в базу данных.  
  
 Для классов в иерархии наследования <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>(`o`) также задает значение члена, назначенного в качестве *дискриминатора* в соответствии с типом объекта `o`. Если тип совпадает со значением дискриминатора по умолчанию, данное значение переопределяет значение дискриминатора. Дополнительные сведения см. в разделе [Поддержка наследования](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).  
  
> [!IMPORTANT]
>  Объект, добавляемый в `Table` не является кэшем идентификации. Кэш идентификации отражает только данные, извлеченные из базы данных. После вызова <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> добавленная сущность не отображается в запросах к базе данных до успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
## <a name="deleting-objects"></a>Удаление объектов  
 Отслеживаемый объект `o` помечается для удаления путем вызова метода <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>(o) для соответствующей таблицы <xref:System.Data.Linq.Table%601>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] рассматривает удаление объекта из <xref:System.Data.Linq.EntitySet%601> как обновление устанавливается операции и соответствующие значения внешнего ключа в null. Результат операции (`o`) из таблицы не удаляется. Например, `cust.Orders.DeleteOnSubmit(ord)` означает обновление, где для разрыва связи между `cust` и `ord` внешнему ключу `ord.CustomerID` задается значение NULL. При этом строка, соответствующая `ord`, не удаляется.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняет следующий процесс при удалении объекта (<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>) из таблицы:  
  
- При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для объекта выполняется операция `DELETE`.  
  
- Удаление не отражается на связанных объектах независимо от того, загружены они или нет. В частности, связанные объекты не загружаются для обновления свойства связи.  
  
- После успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> все объекты переходят в состояние `Deleted`. В результате объект или его `id` не могут использоваться в данном <xref:System.Data.Linq.DataContext>. Внутренний кэш, поддерживаемый экземпляром <xref:System.Data.Linq.DataContext>, не удаляет объекты, извлеченные или добавленные в качестве новых, даже если они были удалены в базе данных.  
  
 Метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> можно вызвать только в объекте, отслеживаемом с помощью <xref:System.Data.Linq.DataContext>. Для объекта `Untracked` метод <xref:System.Data.Linq.Table%601.Attach%2A> необходимо вызвать до вызова <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>. При вызове метода <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> в объекте `Untracked` создается исключение.  
  
> [!NOTE]
>  Удаление объекта из таблицы сообщает [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] для создания соответствующего SQL `DELETE` команды во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Это действие не приводит к удалению объекта из кэша статьи и не распространяется на удаление связанных объектов.  
>   
>  Чтобы освободить `id` удаленного объекта, воспользуйтесь новым экземпляром <xref:System.Data.Linq.DataContext>. Для очистки связанных объектов, можно использовать *каскадное удаление* компонентов базы данных, в противном случае вручную удалите связанные объекты.  
>   
>  Связанные объекты можно удалять в произвольном порядке (в отличие от базы данных).  
  
## <a name="updating-objects"></a>Обновление объектов  
 `Updates` можно обнаружить, просматривая уведомления об изменениях. Уведомления предоставляются с помощью события <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> в методах задания свойств. Когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] получает уведомление о первом изменении объекта, он создает копию объекта и рассматривает объект в качестве кандидата для создания оператора `Update`.  
  
 Для объектов, которые не реализуют <xref:System.ComponentModel.INotifyPropertyChanging>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] хранит копию значения, которые у объектов при они были первой материализации. При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сравнивает текущие и исходные значения, чтобы определить, был ли изменен объект.  
  
 При обновлении связей ссылка из дочернего элемента на родительский (то есть ссылка, соответствующая внешнему ключу) считается ведущей. Ссылка в обратном направлении (то есть из родительского элемента на дочерний) является необязательной. Классы отношений (<xref:System.Data.Linq.EntitySet%601> и <xref:System.Data.Linq.EntityRef%601>) гарантируют непротиворечивость двунаправленных ссылок для отношений "один-ко-многим" и "один-к-одному". Если в объектной модели не используется <xref:System.Data.Linq.EntitySet%601> или <xref:System.Data.Linq.EntityRef%601> и если имеется обратная ссылка, то при обновлении связей необходимо сохранить ее согласованность с прямой ссылкой.  
  
 При обновлении необходимой ссылки и соответствующего внешнего ключа следует обеспечить их непротиворечивость. Если на момент вызова <xref:System.InvalidOperationException> эти объекты не синхронизированы, создается исключение <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Несмотря на то, что изменения значения внешнего ключа достаточны для воздействия на обновление базовой строки, необходимо изменить ссылку, чтобы сохранить подключение графа объекта и обеспечить двунаправленную согласованность связей.  
  
## <a name="see-also"></a>См. также

- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Операции вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)
