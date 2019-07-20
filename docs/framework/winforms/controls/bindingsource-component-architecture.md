---
title: Архитектура компонента BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 30a83efb57c468da74e9e218de26cf88d3254597
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2019
ms.locfileid: "68364417"
---
# <a name="bindingsource-component-architecture"></a>Архитектура компонента BindingSource
С помощью <xref:System.Windows.Forms.BindingSource> компонента можно универсально привязать все Windows Forms элементы управления к источникам данных.  
  
 <xref:System.Windows.Forms.BindingSource> Компонент упрощает процесс привязки элементов управления к источнику данных и предоставляет следующие преимущества по сравнению с традиционной привязкой данных:  
  
- Включает привязку к бизнес-объектам во время разработки.  
  
- Инкапсулирует функциональность и предоставляет <xref:System.Windows.Forms.CurrencyManager> события во время разработки. <xref:System.Windows.Forms.CurrencyManager>  
  
- Упрощает создание списка, поддерживающего <xref:System.ComponentModel.IBindingList> интерфейс, предоставляя уведомление об изменении списка для источников данных, которые изначально не поддерживают уведомления об изменении списка.  
  
- Предоставляет точку расширения для <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> метода.  
  
- Обеспечивает уровень косвенного обращения между источником данных и элементом управления. Это косвенное обращение важно, когда источник данных может измениться во время выполнения.  
  
- Взаимодействует с другими элементами управления Windows Forms, связанными с данными, <xref:System.Windows.Forms.BindingNavigator> в частности <xref:System.Windows.Forms.DataGridView> , и элементами управления.  
  
 По этим причинам <xref:System.Windows.Forms.BindingSource> компонент является предпочтительным способом привязки элементов управления Windows Forms к источникам данных.  
  
## <a name="bindingsource-features"></a>Функции BindingSource  
 <xref:System.Windows.Forms.BindingSource> Компонент предоставляет несколько функций для привязки элементов управления к данным. С помощью этих функций можно реализовать большинство сценариев привязки данных с практически без написания кода.  
  
 <xref:System.Windows.Forms.BindingSource> Компонент выполняет эту задачу, предоставляя единообразный интерфейс для доступа к различным типам источников данных. Это означает, что для привязки к любому типу используется та же процедура. Например, можно присоединить <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойство <xref:System.Data.DataSet> к бизнес-объекту или к нему и в обоих случаях использовать один и тот же набор свойств, методов и событий для управления источником данных.  
  
 Последовательный интерфейс, предоставляемый <xref:System.Windows.Forms.BindingSource> компонентом, значительно упрощает процесс привязки данных к элементам управления. Для типов источников данных, предоставляющих уведомления об изменениях, <xref:System.Windows.Forms.BindingSource> компонент автоматически передает изменения между элементом управления и источником данных. Для типов источников данных, которые не предоставляют уведомления об изменениях, предоставляются события, позволяющие создавать уведомления об изменениях. В следующем списке показаны функции, поддерживаемые <xref:System.Windows.Forms.BindingSource> компонентом.  
  
- Косвенного обращения.  
  
- Управление валютой.  
  
- Источник данных в виде списка.  
  
- <xref:System.Windows.Forms.BindingSource><xref:System.ComponentModel.IBindingList>как.  
  
- Создание настраиваемого элемента.  
  
- Создание транзакционного элемента.  
  
- <xref:System.Collections.IEnumerable>технической.  
  
- Поддержка во время разработки.  
  
- Статические <xref:System.Windows.Forms.ListBindingHelper> методы.  
  
- Сортировка и фильтрация с помощью <xref:System.ComponentModel.IBindingListView> интерфейса.  
  
- Интеграция с <xref:System.Windows.Forms.BindingNavigator>.  
  
### <a name="indirection"></a>Косвенное обращение  
 <xref:System.Windows.Forms.BindingSource> Компонент обеспечивает уровень косвенного обращения между элементом управления и источником данных. Вместо привязки элемента управления непосредственно к источнику данных необходимо привязать элемент управления к <xref:System.Windows.Forms.BindingSource>, а также присоединить источник данных <xref:System.Windows.Forms.BindingSource> к <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойству компонента.  
  
 Этот уровень косвенного обращения позволяет изменить источник данных без сброса привязки элемента управления. Это дает следующие возможности:  
  
- Можно присоединить к <xref:System.Windows.Forms.BindingSource> разным источникам данных, сохраняя текущие привязки элементов управления.  
  
- Можно изменять элементы в источнике данных и уведомлять связанные элементы управления. Дополнительные сведения см. в разделе [Практическое руководство. Отражает обновления источника данных в элементе управления Windows Forms с помощью BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
- Можно выполнить привязку к <xref:System.Type> объекту вместо объекта в памяти. Дополнительные сведения см. в разделе [Практическое руководство. Привязка элемента управления Windows Forms к типу](how-to-bind-a-windows-forms-control-to-a-type.md). Затем можно выполнить привязку к объекту во время выполнения.  
  
### <a name="currency-management"></a>Управление валютой  
 <xref:System.Windows.Forms.BindingSource> Компонент<xref:System.Windows.Forms.ICurrencyManagerProvider> реализует интерфейс для управления валютой. С помощью <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.DataMember%2A>интерфейса можно также получить доступ к диспетчеру валюты для, в дополнение к диспетчеру валюты для другого привязанного к тому же. <xref:System.Windows.Forms.ICurrencyManagerProvider>  
  
 Компонент инкапсулирует функциональные возможности и предоставляет наиболее распространенные <xref:System.Windows.Forms.CurrencyManager> свойства и события. <xref:System.Windows.Forms.CurrencyManager> <xref:System.Windows.Forms.BindingSource> В следующей таблице описаны некоторые элементы, связанные с управлением валютой.  
  
 Свойство <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Возвращает диспетчер валюты, <xref:System.Windows.Forms.BindingSource>связанный с.  
  
 Метод <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Если существует другая <xref:System.Windows.Forms.BindingSource> привязка к указанному элементу данных, получает его диспетчер валюты.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.Current%2A>  
 Возвращает текущий элемент источника данных.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.Position%2A>  
 Возвращает или задает текущую позицию в базовом списке.  
  
 Метод <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Применяет ожидающие изменения к базовому источнику данных.  
  
 Метод <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Отменяет текущую операцию редактирования.  
  
### <a name="data-source-as-a-list"></a>Источник данных в виде списка  
 Компонент реализует интерфейсы<xref:System.ComponentModel.ITypedList> и <xref:System.ComponentModel.IBindingListView>. <xref:System.Windows.Forms.BindingSource> В этой реализации можно использовать <xref:System.Windows.Forms.BindingSource> сам компонент в качестве источника данных без внешнего хранилища.  
  
 <xref:System.Windows.Forms.BindingSource> Когда компонент присоединяется к источнику данных, он предоставляет источник данных в виде списка.  
  
 Для <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойства можно задать несколько источников данных. К ним относятся типы, объекты и списки типов. Полученный источник данных будет представлен в виде списка. В следующей таблице показаны некоторые общие источники данных и вычисление результирующего списка.  
  
|Свойство DataSource|Вывод списка результатов|  
|-------------------------|------------------|  
|Пустая ссылка (`Nothing` в Visual Basic)|Пустой <xref:System.ComponentModel.IBindingList> объект. При добавлении элемента список присваивается типу добавленного элемента.|  
|Пустая ссылка (`Nothing` в Visual Basic) с <xref:System.Windows.Forms.BindingSource.DataMember%2A> набором|Не поддерживается; вызывает <xref:System.ArgumentException>.|  
|Тип, не являющийся списком, или объект типа "T"|Пустой <xref:System.ComponentModel.IBindingList> тип "T".|  
|Экземпляр массива|Объект <xref:System.ComponentModel.IBindingList> , содержащий элементы массива.|  
|<xref:System.Collections.IEnumerable>вхождение|Объект <xref:System.ComponentModel.IBindingList> ,<xref:System.Collections.IEnumerable> содержащий элементы|  
|Экземпляр списка, содержащий тип "T"|Экземпляр <xref:System.ComponentModel.IBindingList> , содержащий тип "T".|  
  
 Кроме того <xref:System.Windows.Forms.BindingSource.DataSource%2A> , можно задать другие типы списков, <xref:System.ComponentModel.IListSource> например и <xref:System.ComponentModel.ITypedList>, и <xref:System.Windows.Forms.BindingSource> будет обрабатывать их соответствующим образом. В этом случае тип, содержащийся в списке, должен иметь конструктор без параметров.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource в качестве IBindingList  
 Компонент предоставляет члены для доступа к базовым данным и управления ими в <xref:System.ComponentModel.IBindingList>качестве. <xref:System.Windows.Forms.BindingSource> В следующей таблице описаны некоторые из этих членов.  
  
|Член|Описание|  
|------------|-----------------|  
|Свойство <xref:System.Windows.Forms.BindingSource.List%2A>|Возвращает список, полученный в результате вычисления <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойств или. <xref:System.Windows.Forms.BindingSource.DataMember%2A>|  
|Метод <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Добавляет новый элемент в базовый список. Применяется к источникам данных, которые <xref:System.ComponentModel.IBindingList> реализуют интерфейс и позволяют добавлять элементы (то есть <xref:System.Windows.Forms.BindingSource.AllowNew%2A> свойство имеет значение `true`).|  
  
### <a name="custom-item-creation"></a>Создание настраиваемого элемента  
 Можно выполнить обработку <xref:System.Windows.Forms.BindingSource.AddingNew> события, чтобы предоставить собственную логику создания элементов. Это <xref:System.Windows.Forms.BindingSource.AddingNew> событие возникает перед добавлением нового объекта <xref:System.Windows.Forms.BindingSource>в. Это событие возникает после <xref:System.Windows.Forms.BindingSource.AddNew%2A> вызова метода, но перед добавлением нового элемента в базовый список. Обрабатывая это событие, можно обеспечить поведение создания пользовательского элемента без наследования от <xref:System.Windows.Forms.BindingSource> класса. Дополнительные сведения см. в разделе [Практическое руководство. Настройка добавления элементов с помощью BindingSource](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)Windows Forms.  
  
### <a name="transactional-item-creation"></a>Создание транзакционных элементов  
 <xref:System.Windows.Forms.BindingSource> Компонент<xref:System.ComponentModel.ICancelAddNew> реализует интерфейс, который позволяет создавать транзакционные элементы. После того <xref:System.Windows.Forms.BindingSource.AddNew%2A>, как новый элемент был подготовлен с помощью вызова, его добавление может быть зафиксировано или отменено следующим образом:  
  
- <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> Метод явно зафиксирует ожидающее добавление.  
  
- Выполнение другой операции сбора, например вставки, удаления или перемещения, приводит к неявному фиксации ожидающего добавления.  
  
- <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> Метод будет выполнять откат ожидающего добавления, если метод еще не был зафиксирован.  
  
### <a name="ienumerable-support"></a>Поддержка интерфейса IEnumerable  
 Компонент позволяет привязать элементы управления <xref:System.Collections.IEnumerable> к источникам данных. <xref:System.Windows.Forms.BindingSource> С помощью этого компонента можно выполнить привязку к источнику данных, например <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType>к.  
  
 <xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource> При<xref:System.ComponentModel.IBindingList>назначении источника <xref:System.Collections.IEnumerable> данных компонент<xref:System.Collections.IEnumerable> создает и добавляет содержимое источника данных в список.  
  
### <a name="design-time-support"></a>Поддержка времени разработки  
 Некоторые типы объектов не могут быть созданы во время разработки, например объекты, созданные из класса фабрики, или объекты, возвращаемые веб-службой. Иногда может потребоваться привязать элементы управления к этим типам во время разработки, даже если в памяти нет объекта, к которому могут быть привязаны элементы управления. Например, можно пометить заголовки <xref:System.Windows.Forms.DataGridView> столбцов элемента управления именами общедоступных свойств пользовательского типа.  
  
 Для поддержки этого сценария <xref:System.Windows.Forms.BindingSource> компонент поддерживает привязку <xref:System.Type>к. При назначении <xref:System.Type> <xref:System.Windows.Forms.BindingSource.DataSource%2A> свойству <xref:System.Windows.Forms.BindingSource> компонент создает пустое <xref:System.ComponentModel.BindingList%601> <xref:System.Type> значение элементов. Все элементы управления, которые в дальнейшем <xref:System.Windows.Forms.BindingSource> привязываются к компоненту, будут получать оповещения о наличии свойств или схемы типа во время разработки или во время выполнения. Дополнительные сведения см. в разделе [Практическое руководство. Привязка элемента управления Windows Forms к типу](how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Статические методы Листбиндингхелпер  
 <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType>Типы, <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType>и всеиспользуют`DataSource` общую`DataMember`логику для создания списка из пары./ <xref:System.Windows.Forms.BindingSource> Кроме того, эта общая логика общедоступна для использования авторами элементов управления и третьими сторонами `static` в следующих методах:  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Сортировка и фильтрация с помощью интерфейса IBindingListView  
 <xref:System.Windows.Forms.BindingSource> Компонент реализует<xref:System.ComponentModel.IBindingList> интерфейс, который расширяет интерфейс. <xref:System.ComponentModel.IBindingListView> Предложение предлагает сортировку по отдельным столбцам <xref:System.ComponentModel.IBindingListView> и предлагает расширенную сортировку и фильтрацию. <xref:System.ComponentModel.IBindingList> С <xref:System.ComponentModel.IBindingListView>помощью можно сортировать и фильтровать элементы в источнике данных, если в источнике данных также реализован один из этих интерфейсов. <xref:System.Windows.Forms.BindingSource> Компонент не предоставляет эталонную реализацию этих членов. Вместо этого вызовы перенаправляются в базовый список.  
  
 В следующей таблице описаны свойства, используемые для сортировки и фильтрации.  
  
|Член|Описание|  
|------------|-----------------|  
|Свойство <xref:System.Windows.Forms.BindingSource.Filter%2A>|Если источником данных является <xref:System.ComponentModel.IBindingListView>, то возвращает или задает выражение, используемое для фильтрации просматриваемых строк.|  
|Свойство <xref:System.Windows.Forms.BindingSource.Sort%2A>|Если источником данных является <xref:System.ComponentModel.IBindingList>, то возвращает или задает имя столбца, используемого для сортировки, и порядок сортировки.<br /><br /> -или-<br /><br /> Если источник данных является <xref:System.ComponentModel.IBindingListView> и поддерживает расширенную сортировку, возвращает несколько имен столбцов, используемых для сортировки и порядка сортировки.|  
  
### <a name="integration-with-bindingnavigator"></a>Интеграция с BindingNavigator  
 <xref:System.Windows.Forms.BindingSource> Компонент можно использовать для привязки любого Windows Forms элемента управления к источнику данных, <xref:System.Windows.Forms.BindingNavigator> но элемент управления разработан <xref:System.Windows.Forms.BindingSource> специально для работы с компонентом. Элемент управления предоставляет пользовательский интерфейс для <xref:System.Windows.Forms.BindingSource> управления текущим элементом компонента. <xref:System.Windows.Forms.BindingNavigator> По умолчанию <xref:System.Windows.Forms.BindingNavigator> элемент управления предоставляет кнопки, соответствующие методам <xref:System.Windows.Forms.BindingSource> навигации компонента. Дополнительные сведения см. в разделе [Практическое руководство. Навигация по данным с помощью Windows Forms BindingNavigator](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md)Control.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Общие сведения о компоненте BindingSource](bindingsource-component-overview.md)
- [Элемент управления BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Привязка данных Windows Forms](../windows-forms-data-binding.md)
- [Элементы управления для использования в Windows Forms](controls-to-use-on-windows-forms.md)
- [Практическое руководство. Привязка элемента управления Windows Forms к типу](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Практическое руководство. Отражение обновлений источника данных в элементе управления Windows Forms с помощью BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
