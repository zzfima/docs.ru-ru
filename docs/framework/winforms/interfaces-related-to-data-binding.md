---
title: "Интерфейсы, относящиеся к привязке данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8108cd3c5ae305b6def5324385cb12c94cd42774
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="interfaces-related-to-data-binding"></a>Интерфейсы, относящиеся к привязке данных
С помощью [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] можно создать различные структуры данных в соответствии с требованиями привязки приложения и данных, с которыми приходится работать. Можно создать собственные классы, которые предоставляют или используют данные в Windows Forms. Такие объекты могут предоставлять функциональные возможности и обеспечивать сложность различного уровня, такие как базовая привязка данных, поддержка на этапе разработки, проверка ошибок, уведомление об изменениях или даже поддержка структурированного отката изменений, внесенных в сами данные.  
  
## <a name="consumers-of-data-binding-interfaces"></a>Потребители интерфейсов привязки данных  
 Ниже описаны две группы объектов интерфейса. В первую группу входят интерфейсы, реализованные на основе источников данных авторами источников данных. Такие интерфейсы предназначены для использования потребителями источников данных, которыми в большинстве случаев являются элементы управления или компоненты Windows Forms. Ко второй группе относятся интерфейсы, используемые авторами компонентов. Авторы компонентов используют эти интерфейсы при создании компонента, поддерживающего привязку данных, которую должен применять модуль привязки данных Windows Forms. Данные интерфейсы можно реализовать внутри классов, связанных с вашей формой, чтобы обеспечить привязку данных. Каждый вариант представляет класс, реализующий интерфейс, позволяющий взаимодействовать с данными. Такие возможности уже применяются в средствах быстрой разработки приложений (RAD) [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
### <a name="interfaces-for-implementation-by-data-source-authors"></a>Интерфейсы для реализации авторами источников данных  
 Следующие интерфейсы предназначены для использования элементами управления Windows Forms.  
  
-   <xref:System.Collections.IList>интерфейс  
  
     Класс, реализующий <xref:System.Collections.IList> интерфейс может быть <xref:System.Array>, <xref:System.Collections.ArrayList>, или <xref:System.Collections.CollectionBase>. Они представляют собой индексированные списки элементов типа <xref:System.Object>. Эти списки должны содержать однородные типы, так как первый элемент индекса определяет тип. <xref:System.Collections.IList>должна быть доступна для привязки только во время выполнения.  
  
    > [!NOTE]
    >  Если вы хотите создать список бизнес-объектов для привязки с Windows Forms, следует использовать <xref:System.ComponentModel.BindingList%601>. <xref:System.ComponentModel.BindingList%601> Представляет собой расширяемый класс, реализующий интерфейсы для двусторонней привязки данных Windows Forms.  
  
-   <xref:System.ComponentModel.IBindingList>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.IBindingList> интерфейс обеспечивает более высокий уровень функциональных возможностей привязки данных. Благодаря данной реализации у вас есть основные возможности сортировки и уведомлений об изменении как при изменении элементов списка (например, третий элемент в списке заказчиков имеет изменения в поле адреса), так и при изменении самого списка (например, увеличение или уменьшение числа элементов в списке). Уведомление об изменении важно, если вы планируете использовать несколько элементов управления, привязанных к одним и тем же данным, и необходимо, чтобы изменения данных, сделанные в одном из элементов управления, распространялись в другие привязанные элементы управления.  
  
    > [!NOTE]
    >  Уведомления об изменениях включена для <xref:System.ComponentModel.IBindingList> интерфейс, с помощью <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> свойства которого, когда `true`, вызывает <xref:System.ComponentModel.IBindingList.ListChanged> событие, указывающее, изменен список или элемент в списке изменен.  
  
     Тип изменения описывается <xref:System.ComponentModel.ListChangedType> свойство <xref:System.ComponentModel.ListChangedEventArgs> параметр. Следовательно, при любом обновлении модели данных все зависимые представления, например другие элементы управления, привязанные к тому же источнику данных, также будут обновлены. Однако для объектов, содержащихся в списке будет уведомить список при изменении ее, чтобы список <xref:System.ComponentModel.IBindingList.ListChanged> событий.  
  
    > [!NOTE]
    >  <xref:System.ComponentModel.BindingList%601> Предоставляет универсальную реализацию <xref:System.ComponentModel.IBindingList> интерфейса.  
  
-   <xref:System.ComponentModel.IBindingListView>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.IBindingListView> интерфейс предоставляет все функциональные возможности реализации <xref:System.ComponentModel.IBindingList>, а также как фильтрации и расширенные возможности сортировки. Такая реализация обеспечивает фильтрацию на основе строк и сортировку по нескольким столбцам с помощью пары "дескриптор свойства-направление".  
  
-   <xref:System.ComponentModel.IEditableObject>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.IEditableObject> интерфейс позволяет объекту для управления, когда становятся постоянными изменения этого объекта. Эта реализация предоставляет <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> методы, которые позволяют выполнить откат изменений, внесенных в объект. Ниже приводится краткое объяснение работы методов <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> методы и как они работают в сочетании друг с другом, чтобы обеспечить откат изменений, внесенных в данные:  
  
    -   <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Метод сигнализирует о начале изменения объекта. Объект, реализующий этот интерфейс, должен сохранить все обновления после <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> вызова метода таким образом, что они могли быть отменены при <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> вызывается метод. В Windows Forms привязки данных, можно вызвать <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> несколько раз в пределах одной транзакции изменения (например, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Реализации <xref:System.ComponentModel.IEditableObject> следует фиксировать ли <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> уже был вызван и игнорировать последующие вызовы <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Поскольку этот метод может вызываться несколько раз, очень важно, что последующие вызовы являются безопасными; то есть последующие <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> вызовы не могут отменить обновления, которые были внесены или изменить данные, сохраненные на первом <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> вызова.  
  
    -   <xref:System.ComponentModel.IEditableObject.EndEdit%2A> Метод записывает все изменения с момента <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> был вызван в основной объект, если объект находится в режиме редактирования.  
  
    -   <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Метод отменяет все изменения, внесенные в объект.  
  
     Дополнительные сведения о том, как <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>, и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> методы работы см. в разделе [сохранить данные в базе данных](/visualstudio/data-tools/save-data-back-to-the-database).  
  
     Такое транзакционное представление функциональных возможностей данных используется <xref:System.Windows.Forms.DataGridView> элемента управления.  
  
-   <xref:System.ComponentModel.ICancelAddNew>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.ICancelAddNew> обычно реализует интерфейс <xref:System.ComponentModel.IBindingList> интерфейс и позволяет выполнять откат добавлений, сделанные в источнике данных с <xref:System.ComponentModel.IBindingList.AddNew%2A> метод. Если источник данных реализует <xref:System.ComponentModel.IBindingList> интерфейс, он также должен реализовать <xref:System.ComponentModel.ICancelAddNew> интерфейса.  
  
-   <xref:System.ComponentModel.IDataErrorInfo>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.IDataErrorInfo> интерфейс позволяет объектам предоставлять пользовательских сведений об ошибке на связанные элементы:  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Error%2A> Свойство возвращает общее сообщение об ошибке (например, «ошибка»).  
  
    -   <xref:System.ComponentModel.IDataErrorInfo.Item%2A> Свойство возвращает строку с сообщением об ошибке из столбца (например, «значение в `State` столбец недопустим»).  
  
-   <xref:System.Collections.IEnumerable>интерфейс  
  
     Класс, реализующий <xref:System.Collections.IEnumerable> интерфейс обычно используется [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]. Поддержка Windows Forms для этого интерфейса доступна только через <xref:System.Windows.Forms.BindingSource> компонента.  
  
    > [!NOTE]
    >  <xref:System.Windows.Forms.BindingSource> Компонент копирует все <xref:System.Collections.IEnumerable> элементы в отдельном списке для привязки.  
  
-   <xref:System.ComponentModel.ITypedList>интерфейс  
  
     Класс коллекции, реализующий <xref:System.ComponentModel.ITypedList> интерфейс предоставляет возможность управлять порядком и набор свойств, доступных в привязанном элементе управления.  
  
    > [!NOTE]
    >  При реализации <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> метода и <xref:System.ComponentModel.PropertyDescriptor> массива не имеет значение null, последняя запись в массиве будет дескриптор свойства, описывающие свойство списка, являющееся другим списком элементов.  
  
-   <xref:System.ComponentModel.ICustomTypeDescriptor>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.ICustomTypeDescriptor> интерфейс предоставляет динамические сведения о себе. Этот интерфейс аналогичен <xref:System.ComponentModel.ITypedList> , но используется для объектов, а не списки. Этот интерфейс используется <xref:System.Data.DataRowView> для применения схемы основных строк. Простая реализация <xref:System.ComponentModel.ICustomTypeDescriptor> обеспечивается <xref:System.ComponentModel.CustomTypeDescriptor> класса.  
  
    > [!NOTE]
    >  Для поддержки привязки во время разработки для типов, реализующих <xref:System.ComponentModel.ICustomTypeDescriptor>, тип должен также реализовывать <xref:System.ComponentModel.IComponent> и занесены в качестве экземпляра для формы.  
  
-   <xref:System.ComponentModel.IListSource>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.IListSource> интерфейс позволяет привязку на основе списка объектов не из списка. <xref:System.ComponentModel.IListSource.GetList%2A> Метод <xref:System.ComponentModel.IListSource> используется для возврата связываемого списка из объекта, который не является производным от <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource>используется <xref:System.Data.DataSet> класса.  
  
-   <xref:System.ComponentModel.IRaiseItemChangedEvents>интерфейс  
  
     Класс, реализующий <xref:System.ComponentModel.IRaiseItemChangedEvents> интерфейс является связываемого списка, который также реализует <xref:System.ComponentModel.IBindingList> интерфейса. Этот интерфейс используется для указания того, если ваш тип вызывает <xref:System.ComponentModel.IBindingList.ListChanged> события типа <xref:System.ComponentModel.ListChangedType.ItemChanged> через его <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> свойство.  
  
    > [!NOTE]
    >  Вам следует реализовать <xref:System.ComponentModel.IRaiseItemChangedEvents> Если источник данных обеспечивает преобразование свойства в список событий было описано выше и работать с ними <xref:System.Windows.Forms.BindingSource> компонента. В противном случае <xref:System.Windows.Forms.BindingSource> также будет выполнять преобразование свойства в список событий приведет к снижению производительности.  
  
-   <xref:System.ComponentModel.ISupportInitialize>интерфейс  
  
     Компонент, реализующий <xref:System.ComponentModel.ISupportInitialize> интерфейс использует преимущества пакетной оптимизации для задания свойств и инициализации взаимозависимых свойств. <xref:System.ComponentModel.ISupportInitialize> Содержит два метода:  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>подает сигнал о начале инициализации этого объекта.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>сигнализирует о том, завершения инициализации объекта.  
  
-   <xref:System.ComponentModel.ISupportInitializeNotification>интерфейс  
  
     Компонент, реализующий <xref:System.ComponentModel.ISupportInitializeNotification> также интерфейс реализует <xref:System.ComponentModel.ISupportInitialize> интерфейса. Этот интерфейс позволяет уведомлять другие <xref:System.ComponentModel.ISupportInitialize> компоненты о завершении инициализации. <xref:System.ComponentModel.ISupportInitializeNotification> Интерфейс содержит два элемента:  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>Возвращает `boolean` значение, указывающее, инициализирован ли компонент.  
  
    -   <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>Происходит при <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> вызывается.  
  
-   <xref:System.ComponentModel.INotifyPropertyChanged>интерфейс  
  
     Класс, реализующий этот интерфейс, представляет собой тип, который вызывает событие при изменении любого значения его свойств. Этот интерфейс предназначен для замены шаблона, в рамках которого имеется отдельное событие изменения для каждого свойства элемента управления. При использовании в <xref:System.ComponentModel.BindingList%601>, бизнес-объект должен реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс и BindingList\`преобразует 1 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> событий для <xref:System.ComponentModel.BindingList%601.ListChanged> события типа <xref:System.ComponentModel.ListChangedType.ItemChanged>.  
  
    > [!NOTE]
    >  Для изменения уведомлений для возникающих в привязке между связанным клиентом и данных вашей привязанного источника данных тип источника должен реализовывать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейса (предпочтительно), или можно задать *propertyName* `Changed` события для связанного типа, но не следует использовать оба.  
  
### <a name="interfaces-for-implementation-by-component-authors"></a>Интерфейсы для реализации авторами компонентов  
 Перечисленные ниже интерфейсы предназначены для использования модулем привязки данных в Windows Forms.  
  
-   <xref:System.Windows.Forms.IBindableComponent>интерфейс  
  
     Класс, реализующий этот интерфейс, является компонентом без элемента управления, который поддерживает привязку данных. Этот класс возвращает привязки данных и контекст привязки компонента с помощью <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> и <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> свойства этого интерфейса.  
  
    > [!NOTE]
    >  Если данный компонент наследуется от <xref:System.Windows.Forms.Control>, необходимо реализовать <xref:System.Windows.Forms.IBindableComponent> интерфейса.  
  
-   <xref:System.Windows.Forms.ICurrencyManagerProvider>интерфейс  
  
     Класс, реализующий <xref:System.Windows.Forms.ICurrencyManagerProvider> интерфейса — это компонент, который предоставляет собственный <xref:System.Windows.Forms.CurrencyManager> для управления привязками, связанными с данным конкретным компонентом. Доступ к пользовательскому <xref:System.Windows.Forms.CurrencyManager> обеспечивается <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> свойство.  
  
    > [!NOTE]
    >  Класс, наследуемый от <xref:System.Windows.Forms.Control> управляет привязками автоматически посредством его <xref:System.Windows.Forms.Control.BindingContext%2A> свойство, поэтому случаи, в которых необходимо реализовать <xref:System.Windows.Forms.ICurrencyManagerProvider> встречаются достаточно редко.  
  
## <a name="see-also"></a>См. также  
 [Привязка данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Привязка данных Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
