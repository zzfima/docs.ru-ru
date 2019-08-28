---
title: Состояния объектов и отслеживание изменений
ms.date: 03/30/2017
ms.assetid: 7a808b00-9c3c-479a-aa94-717280fefd71
ms.openlocfilehash: a60afab5158d0d5f66d12d6913ee890abc8ca730
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70043523"
---
# <a name="object-states-and-change-tracking"></a>Состояния объектов и отслеживание изменений

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]объекты всегда участвуют в определенном *состоянии*. Например, когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает объект, объект находится в состоянии `Unchanged`. Новый объект, который вы сами создаете, неизвестен <xref:System.Data.Linq.DataContext> и находится в `Untracked` состоянии. После успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> все объекты, известные [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], находятся в состоянии `Unchanged`. (Единственное исключение представляют объекты, успешно удаленные из базы данных, находящиеся в состоянии `Deleted` и не используемые в экземпляре <xref:System.Data.Linq.DataContext>.)

## <a name="object-states"></a>Состояния объектов

В следующей таблице представлены возможные состояния объектов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

|Область|Описание|
|-----------|-----------------|
|`Untracked`|Объект, не отслеживаемый [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Далее представлено несколько примеров.<br /><br /> — Объект не запрашивается через текущий <xref:System.Data.Linq.DataContext> (например, только что созданный объект).<br />— Объект, созданный с помощью десериализации.<br />— Объект, запрашиваемый через другой <xref:System.Data.Linq.DataContext>.|
|`Unchanged`|Объект, извлеченный с использованием текущего <xref:System.Data.Linq.DataContext> и не измененный после создания.|
|`PossiblyModified`|Объект, присоединенный к <xref:System.Data.Linq.DataContext>. Дополнительные сведения см. в статьях [Получение данных и операции CUD в N-уровневых приложениях (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md).|
|`ToBeInserted`|Объект, который не был извлечен с использованием текущего <xref:System.Data.Linq.DataContext>. Это приводит к `INSERT` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeUpdated`|Объект, известный для изменения после извлечения. Это приводит к `UPDATE` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`ToBeDeleted`|Объект, помеченный для удаления и вызывающий `DELETE` базы данных во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.|
|`Deleted`|Объект, удаленный в базе данных. Это состояние является завершающим и не допускает дополнительных переходов.|

## <a name="inserting-objects"></a>Вставка объектов

Используя `Inserts`, можно явным образом запросить <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>. Кроме того [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , может `Inserts` определиться путем поиска объектов, подключенных к одному из известных объектов, которые необходимо обновить. Например, если добавить `Untracked` объект <xref:System.Data.Linq.EntitySet%601> в <xref:System.Data.Linq.EntityRef%601> `Untracked` или задать объект для объекта,объектможносделатьдоступнымспомощьюотслеживанияобъектоввграфе.`Untracked` Во время <xref:System.Data.Linq.DataContext.SubmitChanges%2A>обработки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает отслеживающие объекты и обнаруживает все достижимые постоянные объекты, которые не отслеживаются. Такие объекты являются кандидатами на вставку в базу данных.

Для классов в иерархии наследования ( <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>`o`) также задает значение члена, обозначенного как *Дискриминатор* , в соответствии с типом объекта `o`. Если тип совпадает со значением дискриминатора по умолчанию, данное значение переопределяет значение дискриминатора. Дополнительные сведения см. в разделе [Поддержка наследования](../../../../../../docs/framework/data/adonet/sql/linq/inheritance-support.md).

> [!IMPORTANT]
> Объект, добавляемый в `Table` не является кэшем идентификации. Кэш идентификации отражает только данные, извлеченные из базы данных. После вызова <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A> добавленная сущность не отображается в запросах к базе данных до успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

## <a name="deleting-objects"></a>Удаление объектов

Отслеживаемый объект `o` помечается для удаления путем вызова метода <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>(o) для соответствующей таблицы <xref:System.Data.Linq.Table%601>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]рассматривает удаление объекта из <xref:System.Data.Linq.EntitySet%601> операции обновления, а соответствующее значение внешнего ключа устанавливается в NULL. Результат операции (`o`) из таблицы не удаляется. Например, `cust.Orders.DeleteOnSubmit(ord)` означает обновление, где для разрыва связи между `cust` и `ord` внешнему ключу `ord.CustomerID` задается значение NULL. При этом строка, соответствующая `ord`, не удаляется.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]выполняет следующую обработку при удалении объекта (<xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>) из его таблицы:

- При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A> для объекта выполняется операция `DELETE`.

- Удаление не отражается на связанных объектах независимо от того, загружены они или нет. В частности, связанные объекты не загружаются для обновления свойства связи.

- После успешного выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> все объекты переходят в состояние `Deleted`. В результате объект или его `id` не могут использоваться в данном <xref:System.Data.Linq.DataContext>. Внутренний кэш, поддерживаемый экземпляром <xref:System.Data.Linq.DataContext>, не удаляет объекты, извлеченные или добавленные в качестве новых, даже если они были удалены в базе данных.

Метод <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> можно вызвать только в объекте, отслеживаемом с помощью <xref:System.Data.Linq.DataContext>. Для объекта `Untracked` метод <xref:System.Data.Linq.Table%601.Attach%2A> необходимо вызвать до вызова <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>. При вызове метода <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> в объекте `Untracked` создается исключение.

> [!NOTE]
> При удалении объекта из таблицы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создается соответствующая <xref:System.Data.Linq.DataContext.SubmitChanges%2A>команда SQL `DELETE` во время. Это действие не приводит к удалению объекта из кэша статьи и не распространяется на удаление связанных объектов.
>
> Чтобы освободить `id` удаленного объекта, воспользуйтесь новым экземпляром <xref:System.Data.Linq.DataContext>. Для очистки связанных объектов можно использовать функцию *каскадного удаления* базы данных или удалить связанные объекты вручную.
>
> Связанные объекты можно удалять в произвольном порядке (в отличие от базы данных).

## <a name="updating-objects"></a>Обновление объектов

`Updates` можно обнаружить, просматривая уведомления об изменениях. Уведомления предоставляются с помощью события <xref:System.ComponentModel.INotifyPropertyChanging.PropertyChanging> в методах задания свойств. Когда [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] получает уведомление о первом изменении объекта, он создает копию объекта и рассматривает объект в качестве кандидата для создания оператора `Update`.

Для объектов, которые не <xref:System.ComponentModel.INotifyPropertyChanging>реализуют [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , сохраняет копию значений, которые объекты имели при первоначальном материализации. При вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>сравнивает [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] текущее и исходное значения, чтобы решить, был ли изменен объект.

При обновлении связей ссылка из дочернего элемента на родительский (то есть ссылка, соответствующая внешнему ключу) считается ведущей. Ссылка в обратном направлении (то есть из родительского элемента на дочерний) является необязательной. Классы отношений (<xref:System.Data.Linq.EntitySet%601> и <xref:System.Data.Linq.EntityRef%601>) гарантируют непротиворечивость двунаправленных ссылок для отношений "один-ко-многим" и "один-к-одному". Если в объектной модели не используется <xref:System.Data.Linq.EntitySet%601> или <xref:System.Data.Linq.EntityRef%601> и если имеется обратная ссылка, то при обновлении связей необходимо сохранить ее согласованность с прямой ссылкой.

При обновлении необходимой ссылки и соответствующего внешнего ключа следует обеспечить их непротиворечивость. Если на момент вызова <xref:System.InvalidOperationException> эти объекты не синхронизированы, создается исключение <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Несмотря на то, что изменения значения внешнего ключа достаточны для воздействия на обновление базовой строки, необходимо изменить ссылку, чтобы сохранить подключение графа объекта и обеспечить двунаправленную согласованность связей.

## <a name="see-also"></a>См. также

- [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Операции вставки, обновления и удаления](../../../../../../docs/framework/data/adonet/sql/linq/insert-update-and-delete-operations.md)
