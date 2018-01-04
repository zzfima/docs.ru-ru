---
title: "Архитектура компонента BindingSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 25a69f31d8da8638cfc92ff94d8f90dbcb327158
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="bindingsource-component-architecture"></a>Архитектура компонента BindingSource
С <xref:System.Windows.Forms.BindingSource> компонент глобально, все элементы управления Windows Forms можно привязать к источникам данных.  
  
 <xref:System.Windows.Forms.BindingSource> Компонент упрощает процесс привязки элемента управления к источнику данных и предоставляет следующие преимущества по сравнению с традиционной привязке данных:  
  
-   Позволяет привязывать разработки бизнес-объектов.  
  
-   Инкапсулирует <xref:System.Windows.Forms.CurrencyManager> функциональные возможности и предоставляет <xref:System.Windows.Forms.CurrencyManager> событий во время разработки.  
  
-   Упрощает создание списка, поддерживающего <xref:System.ComponentModel.IBindingList> интерфейса, предоставляя уведомления об изменении списка источников данных, которые изначально не поддерживают список уведомлений об изменениях.  
  
-   Предоставляет точку расширения для <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> метод.  
  
-   Обеспечивает уровень косвенного обращения между источником данных и управления. Такое обращение очень важно, если источник данных может изменяться во время выполнения.  
  
-   Взаимодействует с других связанных с данными элементов управления Windows Forms, в частности <xref:System.Windows.Forms.BindingNavigator> и <xref:System.Windows.Forms.DataGridView> элементов управления.  
  
 По этим причинам <xref:System.Windows.Forms.BindingSource> компонент является предпочтительным способом привязки элементов управления Windows Forms к источникам данных.  
  
## <a name="bindingsource-features"></a>Функции BindingSource  
 <xref:System.Windows.Forms.BindingSource> Компонент предоставляет несколько возможностей для привязки элементов управления к данным. Эти функции обеспечивают большинство сценариев привязки данных практически не требует написания кода.  
  
 <xref:System.Windows.Forms.BindingSource> Компонент это достигается путем предоставления согласованного интерфейса для доступа к много различных типов источников данных. Это означает, что использовать ту же процедуру для привязки к любому типу. Например, можно присоединить <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойства <xref:System.Data.DataSet> или бизнес-объект и в обоих случаях вы используют один набор свойств, методов и событий для работы с источником данных.  
  
 Согласованный интерфейс, предоставляемый <xref:System.Windows.Forms.BindingSource> компонент значительно упрощает процесс привязки данных к элементам управления. Для типов источников данных, которые предоставляют уведомление об изменениях, <xref:System.Windows.Forms.BindingSource> компонент автоматически передает изменения между элементом управления и источника данных. Для типов источников данных, не предоставляет уведомления об изменениях предусмотрены события, которые позволяют уведомление об изменении данных. В следующем списке показаны возможности, поддерживаемые <xref:System.Windows.Forms.BindingSource> компонента:  
  
-   Косвенное обращение.  
  
-   Оперативное управление.  
  
-   Источник данных в виде списка.  
  
-   <xref:System.Windows.Forms.BindingSource>как <xref:System.ComponentModel.IBindingList>.  
  
-   Создание пользовательских элементов.  
  
-   Создание транзакционных элементов.  
  
-   <xref:System.Collections.IEnumerable>Поддержка.  
  
-   Поддержка во время разработки.  
  
-   Статические <xref:System.Windows.Forms.ListBindingHelper> методы.  
  
-   Сортировка и фильтрация с помощью <xref:System.ComponentModel.IBindingListView> интерфейса.  
  
-   Интеграция с <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Косвенное обращение  
 <xref:System.Windows.Forms.BindingSource> Компонент обеспечивает уровень косвенного обращения между элементом управления и источником данных. Вместо привязки элемента управления непосредственно к источнику данных, привязан элемент управления <xref:System.Windows.Forms.BindingSource>, и присоедините источник данных для <xref:System.Windows.Forms.BindingSource> компонента <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойство.  
  
 Этот уровень косвенного обращения источник данных можно изменить без сброса привязки элемента управления. Это дает следующие возможности:  
  
-   Можно присоединить <xref:System.Windows.Forms.BindingSource> к различным источникам данных, сохраняя текущие привязки элементов управления.  
  
-   Можно изменять элементы в источнике данных и уведомлять связанные элементы управления. Дополнительные сведения см. в разделе [как: отражают обновления источника данных в элементе управления Windows Forms с использованием компонента BindingSource](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Можно привязать к <xref:System.Type> вместо объекта в памяти. Дополнительные сведения см. в разделе [как: привязки элемента управления Windows Forms к типу](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md). Затем можно привязать объект во время выполнения.  
  
### <a name="currency-management"></a>Управление валюты  
 <xref:System.Windows.Forms.BindingSource> Компонент реализует <xref:System.Windows.Forms.ICurrencyManagerProvider> интерфейс осуществлять управление валюты. С <xref:System.Windows.Forms.ICurrencyManagerProvider> интерфейс, также можно использовать для диспетчер денежных единиц для <xref:System.Windows.Forms.BindingSource>, помимо диспетчер денежных единиц для другого <xref:System.Windows.Forms.BindingSource> привязан к тому же <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 <xref:System.Windows.Forms.BindingSource> Инкапсулирует компонент <xref:System.Windows.Forms.CurrencyManager> функциональные возможности и предоставляет стандартные <xref:System.Windows.Forms.CurrencyManager> свойства и события. Ниже перечислены некоторые из элементов, связанных с управлением валюты.  
  
 Свойство <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Возвращает диспетчер денежных единиц, связанные с <xref:System.Windows.Forms.BindingSource>.  
  
 Метод <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Если существует другой <xref:System.Windows.Forms.BindingSource> , привязанных к определенным элементом данных, возвращает диспетчер денежных единиц.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.Current%2A>  
 Возвращает текущий элемент источника данных.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.Position%2A>  
 Возвращает или задает текущую позицию в базовом списке.  
  
 Метод <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Применяет ожидающие изменения к базовому источнику данных.  
  
 Метод <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Отменяет текущую операцию редактирования.  
  
### <a name="data-source-as-a-list"></a>Источник данных в виде списка  
 <xref:System.Windows.Forms.BindingSource> Компонент реализует <xref:System.ComponentModel.IBindingListView> и <xref:System.ComponentModel.ITypedList> интерфейсов. Эта реализация позволяет использовать <xref:System.Windows.Forms.BindingSource> сам компонент как источник данных без любого внешнего хранилища.  
  
 При <xref:System.Windows.Forms.BindingSource> компонента присоединяется к источнику данных, он представляет источник данных в виде списка.  
  
 <xref:System.Windows.Forms.BindingSource.DataSource%2A> Может быть установлено для нескольких источников данных. К ним относятся типы, объекты и списки типов. Итоговый источник данных будет представлен в виде списка. В следующей таблице показаны некоторые общие источники данных и оценка полученного списка.  
  
|Свойства источника данных|Список результатов|  
|-------------------------|------------------|  
|Пустая ссылка (`Nothing` в Visual Basic)|Пустой <xref:System.ComponentModel.IBindingList> объектов. Добавление элемента списка присваивается тип добавляемого элемента.|  
|Пустая ссылка (`Nothing` в Visual Basic) с <xref:System.Windows.Forms.BindingSource.DataMember%2A> значение|Не поддерживается; вызывает <xref:System.ArgumentException>.|  
|Тип, не являющийся списком или объект типа «T»|Пустой <xref:System.ComponentModel.IBindingList> типа «T».|  
|Экземпляр массива|<xref:System.ComponentModel.IBindingList> Содержащий элементы массива.|  
|<xref:System.Collections.IEnumerable>экземпляр|<xref:System.ComponentModel.IBindingList> Содержащий <xref:System.Collections.IEnumerable> элементов|  
|Экземпляр списка, содержащий тип «T»|<xref:System.ComponentModel.IBindingList> Экземпляра, содержащего тип «T».|  
  
 Кроме того <xref:System.Windows.Forms.BindingSource.DataSource%2A> можно задать для других типов списков, таких как <xref:System.ComponentModel.IListSource> и <xref:System.ComponentModel.ITypedList>и <xref:System.Windows.Forms.BindingSource> будет обрабатывать их соответствующим образом. В этом случае тип, который содержится в списке должен быть конструктор по умолчанию.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource как IBindingList  
 <xref:System.Windows.Forms.BindingSource> Компонент предоставляет элементы для доступа и обработки базовых данных как <xref:System.ComponentModel.IBindingList>. Ниже перечислены некоторые из этих элементов.  
  
|Член|Описание|  
|------------|-----------------|  
|Свойство <xref:System.Windows.Forms.BindingSource.List%2A>|Получает список, полученный в результате вычисления <xref:System.Windows.Forms.BindingSource.DataSource%2A> или <xref:System.Windows.Forms.BindingSource.DataMember%2A> свойства.|  
|Метод <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Добавляет новый элемент в базовый список. Применяется к источникам данных, которые реализуют <xref:System.ComponentModel.IBindingList> интерфейс, а также позволяют добавлять элементы (то есть <xref:System.Windows.Forms.BindingSource.AllowNew%2A> свойству `true`).|  
  
### <a name="custom-item-creation"></a>Создание пользовательских элементов  
 Можно обработать <xref:System.Windows.Forms.BindingSource.AddingNew> событие, чтобы предоставить свою собственную логику создания элементов. <xref:System.Windows.Forms.BindingSource.AddingNew> Событие возникает перед добавлением нового объекта <xref:System.Windows.Forms.BindingSource>. Это событие возникает после <xref:System.Windows.Forms.BindingSource.AddNew%2A> вызывается метод, но до добавлен новый элемент в базовый список. С помощью обработки этого события, вы можете указать поведение создания пользовательского элемента без создания класса, производного от <xref:System.Windows.Forms.BindingSource> класса. Дополнительные сведения см. в разделе [как: Настройка добавления элемента с помощью компонента BindingSource в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### <a name="transactional-item-creation"></a>Создание транзакционных элементов  
 <xref:System.Windows.Forms.BindingSource> Компонент реализует <xref:System.ComponentModel.ICancelAddNew> интерфейс, который позволяет создавать транзакционные элементы. После создания нового элемента предварительно создается с помощью вызова <xref:System.Windows.Forms.BindingSource.AddNew%2A>, добавление может быть фиксации или отката одним из следующих способов:  
  
-   <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> Метод явным образом подтверждает отложенное добавление.  
  
-   Выполнение другой операции коллекции, таких как вставки, удаления или перемещения, неявным образом подтверждает отложенное добавление.  
  
-   <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> Метод приведет к откату отложенное добавление, если метод еще не зафиксированы.  
  
### <a name="ienumerable-support"></a>Поддержка интерфейса IEnumerable  
 <xref:System.Windows.Forms.BindingSource> Компонент позволяет привязывать элементы управления к <xref:System.Collections.IEnumerable> источники данных. С этим компонентом можно привязать к источнику данных таких как <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>.  
  
 При <xref:System.Collections.IEnumerable> источника данных присваивается <xref:System.Windows.Forms.BindingSource> компонента, <xref:System.Windows.Forms.BindingSource> создает <xref:System.ComponentModel.IBindingList> и добавляет содержимое <xref:System.Collections.IEnumerable> источника данных в список.  
  
### <a name="design-time-support"></a>Поддержку во время разработки  
 Некоторые типы объектов невозможно создать во время разработки, например объекты, созданные на основе класса фабрики или объектов, возвращаемых веб-службой. Иногда необходимо привязать элементы управления для этих типов во время разработки, даже если отсутствует объект в памяти, к которому можно привязать элементы управления. Например, необходимо пометить заголовки столбцов из <xref:System.Windows.Forms.DataGridView> управления именами общих свойств пользовательского типа.  
  
 Для поддержки этого сценария <xref:System.Windows.Forms.BindingSource> компонент поддерживает привязку к <xref:System.Type>. При назначении <xref:System.Type> для <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойства <xref:System.Windows.Forms.BindingSource> компонент создает пустой <xref:System.ComponentModel.BindingList%601> из <xref:System.Type> элементов. Все элементы управления, можно впоследствии привязку к <xref:System.Windows.Forms.BindingSource> компонент появится предупреждение о наличии свойств или схемы данного типа, во время разработки или во время выполнения. Дополнительные сведения см. в разделе [как: привязки элемента управления Windows Forms к типу](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>ListBindingHelper статические методы  
 <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>, И <xref:System.Windows.Forms.BindingSource> типы все папки ту же логику для создания списка из `DataSource` / `DataMember` пары. Кроме того, эта общая логика открыта для использования авторами элементов управления и другими третьими лицами, в следующем `static` методов:  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Сортировка и фильтрация с помощью IBindingListView-интерфейс  
 <xref:System.Windows.Forms.BindingSource> Компонент реализует <xref:System.ComponentModel.IBindingListView> интерфейс, который расширяет <xref:System.ComponentModel.IBindingList> интерфейса. <xref:System.ComponentModel.IBindingList> Предлагает один столбец сортировки и <xref:System.ComponentModel.IBindingListView> предлагает улучшенную сортировку и фильтрацию. С <xref:System.ComponentModel.IBindingListView>, можно сортировать и фильтровать элементы в источнике данных, если источник данных, также реализует один из этих интерфейсов. <xref:System.Windows.Forms.BindingSource> Компонент не предоставляет реализации этих членов. Вместо этого выполняется перенаправление вызовов в базовый список.  
  
 Ниже перечислены свойства, используемого для сортировки и фильтрации.  
  
|Член|Описание|  
|------------|-----------------|  
|Свойство <xref:System.Windows.Forms.BindingSource.Filter%2A>|Если источником данных является <xref:System.ComponentModel.IBindingListView>, то возвращает или задает выражение, используемое для фильтрации просматриваемых строк.|  
|Свойство <xref:System.Windows.Forms.BindingSource.Sort%2A>|Если источником данных является <xref:System.ComponentModel.IBindingList>, то возвращает или задает имя столбца, используемого для сортировки, и порядок сортировки.<br /><br /> - или -<br /><br /> Если источником данных является <xref:System.ComponentModel.IBindingListView> и поддерживается Расширенная сортировка, возвращает имена нескольких столбцов, используемые для сортировки и порядка сортировки|  
  
### <a name="integration-with-bindingnavigator"></a>Интеграция с BindingNavigator  
 Можно использовать <xref:System.Windows.Forms.BindingSource> компонента для привязки любого элемента управления Windows Forms к источнику данных, но <xref:System.Windows.Forms.BindingNavigator> управления разработан специально для работы с <xref:System.Windows.Forms.BindingSource> компонента. <xref:System.Windows.Forms.BindingNavigator> Управления предоставляет пользовательский интерфейс для управления <xref:System.Windows.Forms.BindingSource> компонента текущего элемента. По умолчанию <xref:System.Windows.Forms.BindingNavigator> управления содержит кнопки, соответствующие методы навигации на <xref:System.Windows.Forms.BindingSource> компонента. Дополнительные сведения см. в разделе [как: перемещения данных с помощью элемента управления BindingNavigator в Windows Forms](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.BindingNavigator>  
 [Общие сведения о компоненте BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)  
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)  
 [Привязка данных Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [Элементы управления для использования в Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)  
 [Практическое руководство. Отражение в элементе управления данных, которые обновились в источнике, с использованием компонента BindingSource в Windows Forms](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
