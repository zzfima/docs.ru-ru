---
title: "Привязка данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bb7562c2f6fab7ce496fd87ecdd891531589abfa
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="data-binding"></a>Привязка данных
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]поддерживает привязку к распространенным элементам управления, такие как элементы управления сетки. В частности [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет основные шаблоны для привязки к сетке данных и обработки привязки основной подробности, как в отношении отображения и обновления.  
  
## <a name="underlying-principle"></a>Основной принцип  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Преобразует [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] запросов в SQL для выполнения в базе данных. Результаты являются строго типизированной коллекцией `IEnumerable`. Поскольку эти объекты являются обычными объектами среды CLR, то для отображения результатов можно использовать привязку к данным обычных объектов. С другой стороны, для выполнения операций изменения (вставки, обновления и удаления) требуются дополнительные действия.  
  
## <a name="operation"></a>Операция  
 Неявная привязка к элементам управления Windows Forms осуществляется посредством реализации интерфейса <xref:System.ComponentModel.IListSource>. Универсальный класс источников данных <xref:System.Data.Linq.Table%601> (`Table<T>` в C# или `Table(Of T)` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]) и универсальный класс `DataQuery` были обновлены и теперь реализуют интерфейс <xref:System.ComponentModel.IListSource>. Оба обработчика привязки данных пользовательского интерфейса (Windows Forms и Windows Presentation Foundation) проверяют, реализует ли их источник данных интерфейс <xref:System.ComponentModel.IListSource>. Поэтому написание непосредственной связи запроса с источником данных элемента управления неявно вызывает [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создание коллекции, как показано в следующем примере:  
  
 [!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
 [!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]  
  
 То же происходит в Windows Presentation Foundation:  
  
 [!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
 [!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]  
  
 Создание коллекции реализуется с помощью универсального класса <xref:System.Data.Linq.Table%601> и универсального класса `DataQuery` в методе <xref:System.ComponentModel.IListSource.GetList%2A>.  
  
## <a name="ilistsource-implementation"></a>Реализация интерфейса "IListSource"  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]реализует <xref:System.ComponentModel.IListSource> в двух местах:  
  
-   Источник данных — <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает таблицу, заполняя `DataBindingList` коллекции, в которой хранится ссылка на таблицу.  
  
-   Источником данных является интерфейс <xref:System.Linq.IQueryable%601>. Имеется два сценария.  
  
    -   Если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] находит базовый <xref:System.Data.Linq.Table%601> из <xref:System.Linq.IQueryable%601>, источник учитывает версию и ситуация аналогична описанной в первом пункте.  
  
    -   Если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не удается найти базовый <xref:System.Data.Linq.Table%601>, источник учитывает версию (например, `groupby`). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]просматривает запрос, чтобы заполнить универсальный `SortableBindingList`, который является простой <xref:System.ComponentModel.BindingList%601> , реализующий функцию сортировки сущностей "T" для данного свойства.  
  
## <a name="specialized-collections"></a>Специализированные коллекции  
 Для реализации многих функций, описанных ранее в этом документе, класс <xref:System.ComponentModel.BindingList%601> был специализирован для получения некоторых других классов. Этими классами являются универсальный класс `SortableBindingList` и универсальный класс `DataBindingList`. Оба класса объявляются как внутренние.  
  
### <a name="generic-sortablebindinglist"></a>Универсальный класс «SortableBindingList»  
 Этот класс, который является производным от класса <xref:System.ComponentModel.BindingList%601>, представляет собой сортируемую версию класса <xref:System.ComponentModel.BindingList%601>. Сортировка выполняется в памяти и никогда не обращается к самой базе данных. Объект <xref:System.ComponentModel.BindingList%601> реализует интерфейс <xref:System.ComponentModel.IBindingList>, но не поддерживает сортировку по умолчанию. Тем не менее <xref:System.ComponentModel.BindingList%601> реализует <xref:System.ComponentModel.IBindingList> с виртуальными *core* методы. Эти методы легко переопределить. Общий объект `SortableBindingList` переопределяет методы <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> и <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>. Метод `ApplySortCore` вызывается методом <xref:System.ComponentModel.IBindingList.ApplySort%2A> и сортирует список из T элементов по данному свойству.  
  
 Если свойство не принадлежит "T", возникает исключение.  
  
 Для осуществления сортировки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает универсальный `SortableBindingList.PropertyComparer` класс, наследующий от универсального <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> и реализует компаратор по умолчанию для данного типа T, `PropertyDescriptor`и направление. Этот класс динамически создает класс `Comparer` для "T", где "T" является типом `PropertyType` дескриптора `PropertyDescriptor`. Затем из статического универсального класса `Comparer` извлекается компаратор по умолчанию. Экземпляр по умолчанию получается с помощью отражения.  
  
 Универсальный класс `SortableBindingList` также является базовым классом для `DataBindingList`. Универсальный класс `SortableBindingList` предлагает два виртуальных метода для приостановки или возобновления отслеживания добавления и удаления элементов. Эти два метода могут использоваться для базовых функций, таких как сортировка, но в действительности они реализуются классами верхнего уровня, например универсальным классом `DataBindingList`.  
  
### <a name="generic-databindinglist"></a>Универсальный класс «DataBindingList»  
 Этот класс наследует от класса `SortableBindingLIst`. Универсальный класс `DataBindingList` сохраняет ссылку на базовый универсальный класс `Table` универсального интерфейса `IQueryable`, используемого для первоначального заполнения коллекции. Универсальный класс `DatabindingList` обеспечивает отслеживание для добавления и удаления элементов в коллекции посредством переопределения методов `InsertItem`() и `RemoveItem`(). Он также реализует абстрактную функцию приостановки/возобновления, чтобы сделать отслеживание условным. Эта функция позволяет универсальному классу `DataBindingList` воспользоваться всеми преимуществами полиморфного использования функции отслеживания родительских классов.  
  
## <a name="binding-to-entitysets"></a>Привязка к коллекциям «EntitySet»  
 Привязка к классу `EntitySet` является особым случаем, поскольку класс `EntitySet` уже является коллекцией, реализующей интерфейс <xref:System.ComponentModel.IBindingList>. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Добавляет сортировки и отмены (<xref:System.ComponentModel.ICancelAddNew>) поддерживает. Для хранения сущностей класс `EntitySet` использует внутренний список. Этот список представляет собой коллекцию нижнего уровня, основанную на универсальном массиве, универсальном классе `ItemList`.  
  
### <a name="adding-a-sorting-feature"></a>Добавление возможности сортировки  
 Массивы предлагают метод сортировки (`Array.Sort()`), который можно использовать с классом `Comparer` типа "T". [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует универсальный класс `SortableBindingList.PropertyComparer`, описанный ранее в этом разделе, для получения данного класса `Comparer` для свойства и направления, в котором требуется выполнить сортировку. Для вызова этой функции к универсальному интерфейсу `ApplySort` добавляется метод `ItemList`.  
  
 На стороне класса `EntitySet` необходимо объявить поддержку сортировки.  
  
-   <xref:System.ComponentModel.IBindingList.SupportsSorting%2A> возвращает `true`.  
  
-   <xref:System.ComponentModel.IBindingList.ApplySort%2A> вызывает метод `entities.ApplySort()`, а затем метод `OnListChanged()`.  
  
-   Свойства <xref:System.ComponentModel.IBindingList.SortDirection%2A> и <xref:System.ComponentModel.IBindingList.SortProperty%2A> предоставляют текущее определение сортировки, которое хранится в локальных членах.  
  
 При использовании System.Windows.Forms.BindingSource и привязке EntitySet\<TEntity > к System.Windows.Forms.BindingSource.DataSource необходимо вызвать EntitySet\<Tentity >. GetNewBindingList для обновления BindingSource.List.  
  
 При использовании System.Windows.Forms.BindingSource и установке свойства BindingSource.DataMember и установке BindingSource.DataSource в класс, имеющий свойство, именуемое в BindingSource.DataMember, который представляет EntitySet\<TEntity >, вы Нет необходимости вызывать EntitySet\<Tentity >. GetNewBindingList для обновления BindingSource.List, но потеряна возможность сортировки.  
  
## <a name="caching"></a>Кэширование  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Реализация запросов <xref:System.ComponentModel.IListSource.GetList%2A>. Если класс Windows Forms BindingSource встречает этот интерфейс, он три раза вызывает метод GetList() для одного подключения. Чтобы обойти эту проблему, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует кэш для каждого экземпляра, чтобы хранить и всегда возвращать одну созданную коллекцию.  
  
## <a name="cancellation"></a>Отмена  
 Интерфейс <xref:System.ComponentModel.IBindingList> определяет метод <xref:System.ComponentModel.IBindingList.AddNew%2A>, который используется элементами управления для создания нового элемента из связанной коллекции. Элемент управления `DataGridView` прекрасно демонстрирует эту функцию, когда последняя отображаемая строка содержит звездочку в заголовке. Звездочка означает, что можно добавить новый элемент.  
  
 В дополнение к этой функции коллекция может также реализовать интерфейс <xref:System.ComponentModel.ICancelAddNew>. Это позволяет элементам выполнять отмену и проверять, был ли проверен новый измененный элемент.  
  
 Интерфейс <xref:System.ComponentModel.ICancelAddNew> реализуется во всех коллекциях привязки данных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (универсальном классе `SortableBindingList` и универсальном классе `EntitySet`). В обоих реализациях код выполняет перечисленные ниже задачи.  
  
-   Позволяет вставлять, а затем удалять элементы в коллекции.  
  
-   Не отслеживает изменений, если пользовательский интерфейс не зафиксировал версию.  
  
-   Не отслеживает изменений, если версия отменена (<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>).  
  
-   Разрешает отслеживать фиксацию версий (<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>).  
  
-   Позволяет коллекции осуществлять нормальное поведение, если новый элемент добавлен не с помощью метода <xref:System.ComponentModel.IBindingList.AddNew%2A>.  
  
## <a name="troubleshooting"></a>Устранение неполадок  
 В этом разделе приведены несколько замечаний, которые могут оказаться полезными при устранении неполадок в приложениях привязки данных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Необходимо использовать свойства - использования одних полей недостаточно. Это требование обусловлено Windows Forms.  
  
-   По умолчанию `image`, `varbinary`, и `timestamp` типов базы данных сопоставляются с байтовыми массивами. В данном сценарии не поддерживается метод `ToString()`, поэтому эти объекты невозможно отобразить.  
  
-   Члена класса, сопоставленного первичному ключу, имеется метод установки, но [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает изменение идентификации объекта. Поэтому первичный/уникальный ключ, используемый в сопоставлении, не может быть обновлен в базе данных. Изменение сетки вызывает исключение при вызове <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
-   Если сущность привязана в двух отдельных сетках (например, в основной сетке и в сетке подробных сведений), операция `Delete` в основной сетке не распространяется на сетку подробных сведений.  
  
## <a name="see-also"></a>См. также  
 [Основные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
