---
title: Привязка данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
ms.openlocfilehash: c7048d292bdf5c1372d5f8f174f7f0e84efa7593
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634720"
---
# <a name="data-binding"></a>Привязка данных

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает привязку к общим элементам управления, например к элементам управления "Сетка". В частности, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет базовые шаблоны для привязки к сетке данных и обработку привязки «основной-подробности», как в случае отображения, так и для обновления.

## <a name="underlying-principle"></a>Основной принцип

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запросы LINQ в SQL для выполнения в базе данных. Результаты являются строго типизированной коллекцией `IEnumerable`. Поскольку эти объекты являются обычными объектами среды CLR, то для отображения результатов можно использовать привязку к данным обычных объектов. С другой стороны, для выполнения операций изменения (вставки, обновления и удаления) требуются дополнительные действия.

## <a name="operation"></a>Операция

Неявная привязка к элементам управления Windows Forms осуществляется посредством реализации интерфейса <xref:System.ComponentModel.IListSource>. Источники данных универсальные <xref:System.Data.Linq.Table%601> (`Table<T>` C# в или `Table(Of T)` в Visual Basic) и универсальный `DataQuery` были обновлены для реализации <xref:System.ComponentModel.IListSource>. Оба обработчика привязки данных пользовательского интерфейса (Windows Forms и Windows Presentation Foundation) проверяют, реализует ли их источник данных интерфейс <xref:System.ComponentModel.IListSource>. Поэтому при написании прямого влияния запроса на источник данных элемента управления неявным образом вызывается [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создания коллекции, как показано в следующем примере:

[!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
[!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]

То же происходит в Windows Presentation Foundation:

[!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
[!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]

Создание коллекции реализуется с помощью универсального класса <xref:System.Data.Linq.Table%601> и универсального класса `DataQuery` в методе <xref:System.ComponentModel.IListSource.GetList%2A>.

## <a name="ilistsource-implementation"></a>Реализация интерфейса "IListSource"

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует <xref:System.ComponentModel.IListSource> в двух местах:

- Источником данных является <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает таблицу для заполнения `DataBindingList` коллекции, которая хранит ссылку на таблицу.

- Источником данных является интерфейс <xref:System.Linq.IQueryable%601>. Существует два сценария:

  - Если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] находит базовый <xref:System.Data.Linq.Table%601> из <xref:System.Linq.IQueryable%601>, источник допускает выпуск, и ситуация аналогична ситуации, описанной в первом пункте.

  - Если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не удается найти базовый <xref:System.Data.Linq.Table%601>, источник не допускает выпуска (например, `groupby`). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает запрос для заполнения универсального `SortableBindingList`, который представляет собой простой <xref:System.ComponentModel.BindingList%601>, реализующий функцию сортировки для сущностей T для данного свойства.

## <a name="specialized-collections"></a>Специализированные коллекции

Для реализации многих функций, описанных ранее в этом документе, класс <xref:System.ComponentModel.BindingList%601> был специализирован для получения некоторых других классов. Этими классами являются универсальный класс `SortableBindingList` и универсальный класс `DataBindingList`. Оба класса объявляются как внутренние.

### <a name="generic-sortablebindinglist"></a>Универсальный класс «SortableBindingList»

Этот класс, который является производным от класса <xref:System.ComponentModel.BindingList%601>, представляет собой сортируемую версию класса <xref:System.ComponentModel.BindingList%601>. Сортировка выполняется в памяти и никогда не обращается к самой базе данных. Объект <xref:System.ComponentModel.BindingList%601> реализует интерфейс <xref:System.ComponentModel.IBindingList>, но не поддерживает сортировку по умолчанию. Однако <xref:System.ComponentModel.BindingList%601> реализует <xref:System.ComponentModel.IBindingList> с виртуальными *базовыми* методами. Эти методы легко переопределить. Общий объект `SortableBindingList` переопределяет методы <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> и <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>. Метод `ApplySortCore` вызывается методом <xref:System.ComponentModel.IBindingList.ApplySort%2A> и сортирует список из T элементов по данному свойству.

Если свойство не принадлежит "T", возникает исключение.

Чтобы выполнить сортировку, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает универсальный `SortableBindingList.PropertyComparer` класс, наследующий от универсального <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> и реализующий компаратор по умолчанию для заданного типа T, `PropertyDescriptor`и направления. Этот класс динамически создает класс `Comparer` для "T", где "T" является типом `PropertyType` дескриптора `PropertyDescriptor`. Затем из статического универсального класса `Comparer` извлекается компаратор по умолчанию. Экземпляр по умолчанию получается с помощью отражения.

Универсальный класс `SortableBindingList` также является базовым классом для `DataBindingList`. Универсальный класс `SortableBindingList` предлагает два виртуальных метода для приостановки или возобновления отслеживания добавления и удаления элементов. Эти два метода могут использоваться для базовых функций, таких как сортировка, но в действительности они реализуются классами верхнего уровня, например универсальным классом `DataBindingList`.

### <a name="generic-databindinglist"></a>Универсальный класс «DataBindingList»

Этот класс наследует от класса `SortableBindingLIst`. Универсальный класс `DataBindingList` сохраняет ссылку на базовый универсальный класс `Table` универсального интерфейса `IQueryable`, используемого для первоначального заполнения коллекции. Универсальный класс `DatabindingList` обеспечивает отслеживание для добавления и удаления элементов в коллекции посредством переопределения методов `InsertItem`() и `RemoveItem`(). Он также реализует абстрактную возможность приостановки/возобновления, чтобы сделать отслеживание условным. Эта возможность позволяет универсальному классу `DataBindingList` воспользоваться всеми преимуществами полиморфного использования возможности отслеживания родительских классов.

## <a name="binding-to-entitysets"></a>Привязка к коллекциям «EntitySet»

Привязка к классу `EntitySet` является особым случаем, поскольку класс `EntitySet` уже является коллекцией, реализующей интерфейс <xref:System.ComponentModel.IBindingList>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] добавляет поддержку сортировки и отмены (<xref:System.ComponentModel.ICancelAddNew>). Для хранения сущностей класс `EntitySet` использует внутренний список. Этот список представляет собой коллекцию нижнего уровня, основанную на универсальном массиве, универсальном классе `ItemList`.

### <a name="adding-a-sorting-feature"></a>Добавление возможности сортировки

Массивы предлагают метод сортировки (`Array.Sort()`), который можно использовать с классом `Comparer` типа "T". [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует универсальный класс `SortableBindingList.PropertyComparer`, описанный ранее в этом разделе, для получения данного класса `Comparer` для свойства и направления, в котором требуется выполнить сортировку. Для вызова этой функции к универсальному интерфейсу `ApplySort` добавляется метод `ItemList`.

На стороне класса `EntitySet` необходимо объявить поддержку сортировки.

- <xref:System.ComponentModel.IBindingList.SupportsSorting%2A> возвращает `true`.

- <xref:System.ComponentModel.IBindingList.ApplySort%2A> вызывает метод `entities.ApplySort()`, а затем метод `OnListChanged()`.

- Свойства <xref:System.ComponentModel.IBindingList.SortDirection%2A> и <xref:System.ComponentModel.IBindingList.SortProperty%2A> предоставляют текущее определение сортировки, которое хранится в локальных членах.

При использовании System. Windows. Forms. BindingSource и привязки набора EntitySet\<> к System. Windows. Forms. BindingSource. DataSource необходимо вызвать EntitySet\<>ости. Жетневбиндинглист для обновления BindingSource. List.

Если вы используете System. Windows. Forms. BindingSource и устанавливаете свойство BindingSource. DataMember и устанавливаете BindingSource. DataSource в класс, имеющий свойство с именем в BindingSource. DataMember, которое предоставляет набор EntitySet\<>, вам не нужно вызывать EntitySet\<>ости. Жетневбиндинглист обновить BindingSource. List, но вы потеряли возможность сортировки.

## <a name="caching"></a>Кэширование

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]ные запросы реализуют <xref:System.ComponentModel.IListSource.GetList%2A>. Если класс Windows Forms BindingSource встречает этот интерфейс, он три раза вызывает метод GetList() для одного подключения. Чтобы обойти эту ситуацию, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует кэш для каждого экземпляра для хранения и всегда возвращает одну и ту же созданную коллекцию.

## <a name="cancellation"></a>Отмена

Интерфейс <xref:System.ComponentModel.IBindingList> определяет метод <xref:System.ComponentModel.IBindingList.AddNew%2A>, который используется элементами управления для создания нового элемента из связанной коллекции. Элемент управления `DataGridView` прекрасно демонстрирует эту возможность, когда последняя отображаемая строка содержит звездочку в заголовке. Звездочка означает, что можно добавить новый элемент.

В дополнение к этой возможности коллекция может также реализовать интерфейс <xref:System.ComponentModel.ICancelAddNew>. Это позволяет элементам выполнять отмену и проверять, был ли проверен новый измененный элемент.

Интерфейс <xref:System.ComponentModel.ICancelAddNew> реализуется во всех коллекциях привязки данных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (универсальном классе `SortableBindingList` и универсальном классе `EntitySet`). В обоих реализациях код выполняет перечисленные ниже задачи.

- Позволяет вставлять, а затем удалять элементы в коллекции.

- Не отслеживает изменений, если пользовательский интерфейс не зафиксировал версию.

- Не отслеживает изменений, если версия отменена (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).

- Разрешает отслеживать фиксацию версий (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).

- Позволяет коллекции осуществлять нормальное поведение, если новый элемент добавлен не с помощью метода <xref:System.ComponentModel.IBindingList.AddNew%2A>.

## <a name="troubleshooting"></a>Диагностика

В этом разделе приведены несколько замечаний, которые могут оказаться полезными при устранении неполадок в приложениях привязки данных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].

- Необходимо использовать свойства - использования одних полей недостаточно. Это требование обусловлено Windows Forms.

- По умолчанию типы баз данных `image`, `varbinary`и `timestamp` сопоставляются с массивом байтов. В данном сценарии не поддерживается метод `ToString()`, поэтому эти объекты невозможно отобразить.

- Член класса, сопоставленный с первичным ключом, имеет метод задания, но [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает изменение идентификатора объекта. Поэтому первичный/уникальный ключ, используемый в сопоставлении, не может быть обновлен в базе данных. Изменение в сетке вызывает исключение при вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

- Если сущность привязана в двух отдельных сетках (например, в основной сетке и в сетке подробных сведений), операция `Delete` в основной сетке не распространяется на сетку подробных сведений.

## <a name="see-also"></a>См. также:

- [Основные сведения](background-information.md)
