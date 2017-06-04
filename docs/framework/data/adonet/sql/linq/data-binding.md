---
title: "Привязка данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: cbec8b02-a1e8-4ae8-a83b-bb5190413ac5
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Привязка данных
Технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает привязку к распространенным элементам управления, таким как элементы управления "сетка".  В частности, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] определяет основные шаблоны для привязки к сетке данных и обработки привязки к элементу управления "основной\-подробности" в отношении отображения и обновления.  
  
## Основной принцип  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует запросы [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] в команды SQL для выполнения в базе данных.  Результаты являются строго типизированной коллекцией `IEnumerable`.  Поскольку эти объекты являются обычными объектами среды CLR, то для отображения результатов можно использовать привязку к данным обычных объектов.  С другой стороны, для выполнения операций изменения \(вставки, обновления и удаления\) требуются дополнительные действия.  
  
## Операция  
 Неявная привязка к элементам управления Windows Forms осуществляется посредством реализации интерфейса <xref:System.ComponentModel.IListSource>.  Универсальный класс источников данных <xref:System.Data.Linq.Table%601> \(`Table<T>` в C\# или `Table(Of T)` в [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\) и универсальный класс `DataQuery` обновлены для реализации <xref:System.ComponentModel.IListSource>. Оба обработчика привязки данных пользовательского интерфейса \(Windows Forms и Windows Presentation Foundation\) проверяют, реализует ли их источник данных <xref:System.ComponentModel.IListSource>.  Поэтому написание непосредственной связи запроса с источником данных элемента управления неявно вызывает создание коллекции [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], как показано в следующем примере.  
  
 [!code-csharp[DLinqDataBinding#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#1)]
 [!code-vb[DLinqDataBinding#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#1)]  
  
 То же происходит в Windows Presentation Foundation:  
  
 [!code-csharp[DLinqDataBinding#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqDataBinding/cs/Program.cs#2)]
 [!code-vb[DLinqDataBinding#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqDataBinding/vb/Module1.vb#2)]  
  
 Создание коллекции реализуется с помощью универсального класса <xref:System.Data.Linq.Table%601> и универсального класса `DataQuery` в методе <xref:System.ComponentModel.IListSource.GetList%2A>.  
  
## Реализация интерфейса "IListSource"  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует <xref:System.ComponentModel.IListSource> в двух расположениях, указанных ниже.  
  
-   Источник данных \- класс <xref:System.Data.Linq.Table%601>: [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает таблицу, заполняя коллекцию `DataBindingList`, в которой хранится ссылка на таблицу.  
  
-   Источником данных является интерфейс <xref:System.Linq.IQueryable%601>.  Имеется два сценария.  
  
    -   Если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] находит базовый класс <xref:System.Data.Linq.Table%601> из интерфейса <xref:System.Linq.IQueryable%601>, то источник учитывает версию и ситуация аналогична описанной в первом пункте.  
  
    -   Если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не удается найти базовый класс <xref:System.Data.Linq.Table%601>, источник не учитывает версию \(например, `groupby`\). [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает запрос, чтобы заполнить универсальный класс `SortableBindingList`, который является простым экземпляром <xref:System.ComponentModel.BindingList%601>, реализующим функцию сортировки сущностей "T" для данного свойства.  
  
## Специализированные коллекции  
 Для реализации многих функций, описанных ранее в этом документе, класс <xref:System.ComponentModel.BindingList%601> был специализирован для получения некоторых других классов.  Этими классами являются универсальный класс `SortableBindingList` и универсальный класс `DataBindingList`.  Оба класса объявляются как внутренние.  
  
### Универсальный класс «SortableBindingList»  
 Этот класс, который является производным от класса <xref:System.ComponentModel.BindingList%601>, представляет собой сортируемую версию класса <xref:System.ComponentModel.BindingList%601>.  Сортировка выполняется в памяти и никогда не обращается к самой базе данных.  Объект <xref:System.ComponentModel.BindingList%601> реализует интерфейс <xref:System.ComponentModel.IBindingList>, но не поддерживает сортировку по умолчанию.  Однако класс <xref:System.ComponentModel.BindingList%601> реализует интерфейс <xref:System.ComponentModel.IBindingList> с помощью виртуальных *базовых* методов.  Эти методы легко переопределить.  Общий объект `SortableBindingList` переопределяет методы <xref:System.ComponentModel.BindingList%601.SupportsSortingCore%2A>, <xref:System.ComponentModel.BindingList%601.SortPropertyCore%2A>, <xref:System.ComponentModel.BindingList%601.SortDirectionCore%2A> и <xref:System.ComponentModel.BindingList%601.ApplySortCore%2A>.  Метод `ApplySortCore` вызывается методом <xref:System.ComponentModel.IBindingList.ApplySort%2A> и сортирует список из T элементов по данному свойству.  
  
 Если свойство не принадлежит "T", возникает исключение.  
  
 Для осуществления сортировки [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] создает универсальный класс `SortableBindingList.PropertyComparer`, который является производным от универсального класса <xref:System.Collections.Generic.Comparer%601.System%23Collections%23IComparer%23Compare%2A> и реализует компаратор по умолчанию для данного типа "T", дескриптора `PropertyDescriptor` и направления.  Этот класс динамически создает класс `Comparer` для "T", где "T" является типом `PropertyType` дескриптора `PropertyDescriptor`.  Затем из статического универсального класса `Comparer` извлекается компаратор по умолчанию.  Экземпляр по умолчанию получается с помощью отражения.  
  
 Универсальный класс `SortableBindingList` также является базовым классом для `DataBindingList`.  Универсальный класс `SortableBindingList` предлагает два виртуальных метода для приостановки или возобновления отслеживания добавления и удаления элементов.  Эти два метода могут использоваться для базовых функций, таких как сортировка, но в действительности они реализуются классами верхнего уровня, например универсальным классом `DataBindingList`.  
  
### Универсальный класс «DataBindingList»  
 Этот класс наследует от класса `SortableBindingLIst`.  Универсальный класс `DataBindingList` сохраняет ссылку на базовый универсальный класс `Table` универсального интерфейса `IQueryable`, используемого для первоначального заполнения коллекции.  Универсальный класс `DatabindingList` обеспечивает отслеживание для добавления и удаления элементов в коллекции посредством переопределения методов `InsertItem`\(\) и `RemoveItem`\(\).  Он также реализует абстрактную функцию приостановки\/возобновления, чтобы сделать отслеживание условным.  Эта функция позволяет универсальному классу `DataBindingList` воспользоваться всеми преимуществами полиморфного использования функции отслеживания родительских классов.  
  
## Привязка к коллекциям «EntitySet»  
 Привязка к классу `EntitySet` является особым случаем, поскольку класс `EntitySet` уже является коллекцией, реализующей интерфейс <xref:System.ComponentModel.IBindingList>.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] добавляет поддержку сортировки и отмены \(<xref:System.ComponentModel.ICancelAddNew>\).  Для хранения сущностей класс `EntitySet` использует внутренний список.  Этот список представляет собой коллекцию нижнего уровня, основанную на универсальном массиве, универсальном классе `ItemList`.  
  
### Добавление функции сортировки  
 Массивы обеспечивают метод сортировки \(`Array.Sort()`\), который может быть использован с классом `Comparer` типа T.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] использует универсальный класс `SortableBindingList.PropertyComparer`, описанный ранее в этом разделе, для получения данного класса `Comparer`, который определяет свойства и направления сортировки.  Для вызова этой функции к универсальному интерфейсу `ItemList` добавляется метод `ApplySort`.  
  
 На стороне класса `EntitySet` необходимо объявить поддержку сортировки.  
  
-   <xref:System.ComponentModel.IBindingList.SupportsSorting%2A> возвращает `true`.  
  
-   <xref:System.ComponentModel.IBindingList.ApplySort%2A> вызывает метод `entities.ApplySort()`, а затем метод `OnListChanged()`.  
  
-   Свойства <xref:System.ComponentModel.IBindingList.SortDirection%2A> и <xref:System.ComponentModel.IBindingList.SortProperty%2A> предоставляют текущее определение сортировки, которое хранится в локальных членах.  
  
 При использовании System.Windows.Forms.BindingSource и привязке EntitySet\<TEntity\> к System.Windows.Forms.BindingSource.DataSource необходимо вызвать EntitySet\<Tentity\>.GetNewBindingList для обновления BindingSource.List.  
  
 При использовании System.Windows.Forms.BindingSource и установке свойства BindingSource.DataMember и установке BindingSource.DataSource в класс, имеющий свойство, именуемое в BindingSource.DataMember, который представляет EntitySet\<TEntity\>, нет необходимости вызывать EntitySet\<Tentity\>.GetNewBindingList для обновления BindingSource.List, но будет потеряна возможность сортировки.  
  
## Кэширование  
 Запросы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализуют метод <xref:System.ComponentModel.IListSource.GetList%2A>.  Если класс Windows Forms BindingSource встречает этот интерфейс, он три раза вызывает метод GetList\(\) для одного подключения.  Для разрешения этой ситуации [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] реализует кэш для каждого экземпляра, чтобы хранить и всегда возвращать одну созданную коллекцию.  
  
## Отмена  
 Интерфейс <xref:System.ComponentModel.IBindingList> определяет метод <xref:System.ComponentModel.IBindingList.AddNew%2A>, который используется элементами управления для создания нового элемента из связанной коллекции.  Элемент управления `DataGridView` прекрасно демонстрирует эту функцию, когда последняя отображаемая строка содержит звездочку в заголовке.  Звездочка означает, что можно добавить новый элемент.  
  
 В дополнение к этой функции коллекция может также реализовать интерфейс <xref:System.ComponentModel.ICancelAddNew>.  Это позволяет элементам выполнять отмену и проверять, был ли проверен новый измененный элемент.  
  
 Интерфейс <xref:System.ComponentModel.ICancelAddNew> реализован во всех коллекциях привязки данных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] \(универсальных классах `SortableBindingList` и универсальных классах `EntitySet`\). В обеих реализациях код выполняется следующим образом.  
  
-   Позволяет вставлять, а затем удалять элементы в коллекции.  
  
-   Не отслеживает изменений, если пользовательский интерфейс не зафиксировал версию.  
  
-   Не отслеживает изменений, если версия отменена \(<xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>\).  
  
-   Разрешает отслеживать фиксацию версий \(<xref:System.ComponentModel.ICancelAddNew.EndNew%2A>\).  
  
-   Позволяет коллекции осуществлять нормальное поведение, если новый элемент добавлен не с помощью метода <xref:System.ComponentModel.IBindingList.AddNew%2A>.  
  
## Устранение неполадок  
 В этом разделе приведены несколько замечаний, которые могут оказаться полезными при устранении неполадок в приложениях привязки данных [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
-   Необходимо использовать свойства \- использования одних полей недостаточно.  Это требование обусловлено Windows Forms.  
  
-   По умолчанию типы баз данных `image`, `varbinary` и `timestamp` сопоставляются с байтовыми массивами.  В данном сценарии не поддерживается метод `ToString()`, поэтому эти объекты невозможно отобразить.  
  
-   Для члена класса, сопоставленного первичному ключу, имеется метод установки, однако [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не поддерживает изменение идентификации объекта.  Поэтому первичный\/уникальный ключ, используемый в сопоставлении, не может быть обновлен в базе данных.  При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> изменение сетки вызывает исключение.  
  
-   Если сущность привязана в двух отдельных сетках \(например, в основной сетке и в сетке подробных сведений\), операция `Delete` в основной сетке не распространяется на сетку подробных сведений.  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)