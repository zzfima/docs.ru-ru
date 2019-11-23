---
title: Интерфейсы, относящиеся к привязке данных
ms.date: 03/30/2017
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
ms.openlocfilehash: 4e40f7ec1922cdf43e6a0b8f5734acaaeefbc514
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834593"
---
# <a name="interfaces-related-to-data-binding"></a>Интерфейсы, относящиеся к привязке данных

С помощью ADO.NET можно создать множество различных структур данных в соответствии с потребностями привязки приложения и данными, с которыми вы работаете. Можно создать собственные классы, которые предоставляют или используют данные в Windows Forms. Такие объекты могут предоставлять функциональные возможности и обеспечивать сложность различного уровня, такие как базовая привязка данных, поддержка на этапе разработки, проверка ошибок, уведомление об изменениях или даже поддержка структурированного отката изменений, внесенных в сами данные.

## <a name="consumers-of-data-binding-interfaces"></a>Потребители интерфейсов привязки данных

В следующих разделах описываются две группы объектов интерфейса. В первую группу входят интерфейсы, реализованные на основе источников данных авторами источников данных. Такие интерфейсы предназначены для использования потребителями источников данных, которыми в большинстве случаев являются элементы управления или компоненты Windows Forms. Ко второй группе относятся интерфейсы, используемые авторами компонентов. Авторы компонентов используют эти интерфейсы при создании компонента, поддерживающего привязку данных, которую должен применять модуль привязки данных Windows Forms. Данные интерфейсы можно реализовать внутри классов, связанных с вашей формой, чтобы обеспечить привязку данных. Каждый вариант представляет класс, реализующий интерфейс, позволяющий взаимодействовать с данными. Средства разработки данных для быстрой разработки приложений (RAD) в Visual Studio уже используют преимущества этой функции.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Интерфейсы для реализации авторами источников данных

Следующие интерфейсы предназначены для использования элементами управления Windows Forms.

- интерфейс <xref:System.Collections.IList>

  Классом, реализующим интерфейс <xref:System.Collections.IList>, может быть <xref:System.Array>, <xref:System.Collections.ArrayList>или <xref:System.Collections.CollectionBase>. Это индексированные списки элементов типа <xref:System.Object>. Эти списки должны содержать однородные типы, так как первый элемент индекса определяет тип. <xref:System.Collections.IList> будут доступны для привязки только во время выполнения.

  > [!NOTE]
  > Если необходимо создать список бизнес-объектов для привязки с Windows Forms, рекомендуется использовать <xref:System.ComponentModel.BindingList%601>. <xref:System.ComponentModel.BindingList%601> является расширяемым классом, реализующим основные интерфейсы, необходимые для двусторонней Windows Forms привязки данных.

- интерфейс <xref:System.ComponentModel.IBindingList>

  Класс, реализующий интерфейс <xref:System.ComponentModel.IBindingList>, обеспечивает более высокий уровень функциональности привязки данных. Благодаря данной реализации у вас есть основные возможности сортировки и уведомлений об изменении как при изменении элементов списка (например, третий элемент в списке заказчиков имеет изменения в поле адреса), так и при изменении самого списка (например, увеличение или уменьшение числа элементов в списке). Уведомление об изменении важно, если вы планируете использовать несколько элементов управления, привязанных к одним и тем же данным, и необходимо, чтобы изменения данных, сделанные в одном из элементов управления, распространялись в другие привязанные элементы управления.

  > [!NOTE]
  > Уведомление об изменении включено для интерфейса <xref:System.ComponentModel.IBindingList> через свойство <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A>, которое, когда `true`, вызывает событие <xref:System.ComponentModel.IBindingList.ListChanged>, указывающее на изменение списка или на изменение элемента в списке.

  Тип изменения описан свойством <xref:System.ComponentModel.ListChangedType> параметра <xref:System.ComponentModel.ListChangedEventArgs>. Следовательно, при любом обновлении модели данных все зависимые представления, например другие элементы управления, привязанные к тому же источнику данных, также будут обновлены. Однако объекты, содержащиеся в списке, должны уведомлять список при изменении, чтобы список мог вызвать событие <xref:System.ComponentModel.IBindingList.ListChanged>.

  > [!NOTE]
  > <xref:System.ComponentModel.BindingList%601> предоставляет универсальную реализацию интерфейса <xref:System.ComponentModel.IBindingList>.

- интерфейс <xref:System.ComponentModel.IBindingListView>

  Класс, реализующий интерфейс <xref:System.ComponentModel.IBindingListView>, предоставляет все функциональные возможности реализации <xref:System.ComponentModel.IBindingList>, а также функции фильтрации и расширенной сортировки. Такая реализация обеспечивает фильтрацию на основе строк и сортировку по нескольким столбцам с помощью пары "дескриптор свойства-направление".

- интерфейс <xref:System.ComponentModel.IEditableObject>

  Класс, реализующий интерфейс <xref:System.ComponentModel.IEditableObject>, позволяет объекту управлять тем, когда изменения в этом объекте сделаны постоянными. Эта реализация предоставляет вам методы <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, которые позволяют выполнять откат изменений, внесенных в объект. Ниже приведено краткое описание функционирования методов <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> и способов их работы в сочетании друг с другом, чтобы обеспечить возможность отката изменений, внесенных в данные:

  - Метод <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> сигнализирует о начале редактирования объекта. Объект, реализующий этот интерфейс, должен сохранять любые обновления после вызова метода <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> таким образом, чтобы обновления можно было отменять при вызове метода <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>. В Windows Forms привязки данных можно вызывать <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> несколько раз в рамках одной транзакции изменения (например, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>). Реализации <xref:System.ComponentModel.IEditableObject> должны отследить, было ли уже вызвано <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, и пропускать последующие вызовы <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>. Поскольку этот метод может вызываться несколько раз, важно, чтобы последующие вызовы этого метода были необратимыми; то есть последующие вызовы <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> не могут уничтожить произведенные обновления или изменить данные, сохраненные при первом вызове <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.

  - Метод <xref:System.ComponentModel.IEditableObject.EndEdit%2A> передает все изменения с момента вызова <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> в базовый объект, если объект находится в режиме редактирования.

  - Метод <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> отклоняет все изменения, внесенные в объект.

  Дополнительные сведения о том, как работают методы <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, см. [в разделе Сохранение данных обратно в базу данных](/visualstudio/data-tools/save-data-back-to-the-database).

  Это транзакционное представление функциональных возможностей данных используется элементом управления <xref:System.Windows.Forms.DataGridView>.

- интерфейс <xref:System.ComponentModel.ICancelAddNew>

  Класс, реализующий интерфейс <xref:System.ComponentModel.ICancelAddNew>, обычно реализует интерфейс <xref:System.ComponentModel.IBindingList> и позволяет выполнить откат добавления к источнику данных с помощью метода <xref:System.ComponentModel.IBindingList.AddNew%2A>. Если источник данных реализует интерфейс <xref:System.ComponentModel.IBindingList>, также необходимо реализовать интерфейс <xref:System.ComponentModel.ICancelAddNew>.

- интерфейс <xref:System.ComponentModel.IDataErrorInfo>

  Класс, реализующий интерфейс <xref:System.ComponentModel.IDataErrorInfo>, позволяет объектам предлагать пользовательские сведения об ошибке для привязанных элементов управления:

  - Свойство <xref:System.ComponentModel.IDataErrorInfo.Error%2A> возвращает общий текст сообщения об ошибке (например, "произошла ошибка").

  - Свойство <xref:System.ComponentModel.IDataErrorInfo.Item%2A> возвращает строку с конкретным сообщением об ошибке из столбца (например, "значение в столбце `State` является недопустимым").

- интерфейс <xref:System.Collections.IEnumerable>

  Класс, реализующий интерфейс <xref:System.Collections.IEnumerable>, обычно использует ASP.NET. Windows Forms поддержка этого интерфейса доступна только через компонент <xref:System.Windows.Forms.BindingSource>.

  > [!NOTE]
  > Компонент <xref:System.Windows.Forms.BindingSource> копирует все элементы <xref:System.Collections.IEnumerable> в отдельный список для целей привязки.

- интерфейс <xref:System.ComponentModel.ITypedList>

  Класс Collections, реализующий интерфейс <xref:System.ComponentModel.ITypedList>, предоставляет возможность управлять порядком и набором свойств, предоставляемых привязанному элементу управления.

  > [!NOTE]
  > При реализации метода <xref:System.ComponentModel.ITypedList.GetItemProperties%2A>, если массив <xref:System.ComponentModel.PropertyDescriptor> не равен null, последняя запись в массиве будет дескриптором свойства, описывающим свойство списка, которое является другим списком элементов.

- интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor>

  Класс, реализующий интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor>, предоставляет динамическую информацию о себе. Этот интерфейс похож на <xref:System.ComponentModel.ITypedList>, но используется для объектов, а не списков. Этот интерфейс используется <xref:System.Data.DataRowView> для проецирования схемы базовых строк. Простая реализация <xref:System.ComponentModel.ICustomTypeDescriptor> предоставляется классом <xref:System.ComponentModel.CustomTypeDescriptor>.

  > [!NOTE]
  > Для поддержки привязки времени разработки к типам, реализующим <xref:System.ComponentModel.ICustomTypeDescriptor>, тип должен также реализовывать <xref:System.ComponentModel.IComponent> и существовать как экземпляр в форме.

- интерфейс <xref:System.ComponentModel.IListSource>

  Класс, реализующий интерфейс <xref:System.ComponentModel.IListSource>, обеспечивает привязку на основе списка для объектов, не являющихся списками. Метод <xref:System.ComponentModel.IListSource.GetList%2A> <xref:System.ComponentModel.IListSource> используется для получения связываемого списка из объекта, который не наследуется от <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource> используется классом <xref:System.Data.DataSet>.

- интерфейс <xref:System.ComponentModel.IRaiseItemChangedEvents>

  Класс, реализующий интерфейс <xref:System.ComponentModel.IRaiseItemChangedEvents>, является связываемым списком, который также реализует интерфейс <xref:System.ComponentModel.IBindingList>. Этот интерфейс используется для указания того, что ваш тип вызывает <xref:System.ComponentModel.IBindingList.ListChanged> события типа <xref:System.ComponentModel.ListChangedType.ItemChanged> через его свойство <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>.

  > [!NOTE]
  > Необходимо реализовать <xref:System.ComponentModel.IRaiseItemChangedEvents>, если источник данных предоставляет свойство для перечисления событий, описанное ранее, и взаимодействует с компонентом <xref:System.Windows.Forms.BindingSource>. В противном случае <xref:System.Windows.Forms.BindingSource> также будет выполнять преобразование свойства в список событий, что приводит к снижению производительности.

- интерфейс <xref:System.ComponentModel.ISupportInitialize>

  Компонент, реализующий интерфейс <xref:System.ComponentModel.ISupportInitialize>, обладает преимуществами оптимизации пакетной обработки для настройки свойств и инициализации свойств, зависящих от совместной работы. <xref:System.ComponentModel.ISupportInitialize> содержит два метода:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> сигнализирует, что инициализация объекта запускается.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> сигнализирует, что инициализация объекта завершается.

- интерфейс <xref:System.ComponentModel.ISupportInitializeNotification>

  Компонент, реализующий интерфейс <xref:System.ComponentModel.ISupportInitializeNotification>, также реализует интерфейс <xref:System.ComponentModel.ISupportInitialize>. Этот интерфейс позволяет уведомлять другие <xref:System.ComponentModel.ISupportInitialize>ные компоненты о завершении инициализации. Интерфейс <xref:System.ComponentModel.ISupportInitializeNotification> содержит два члена:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> возвращает значение типа `boolean`, указывающее, инициализирован ли компонент.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> возникает при вызове <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>.

- интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>

  Класс, реализующий этот интерфейс, представляет собой тип, который вызывает событие при изменении любого значения его свойств. Этот интерфейс предназначен для замены шаблона, в рамках которого имеется отдельное событие изменения для каждого свойства элемента управления. При использовании в <xref:System.ComponentModel.BindingList%601>бизнес-объект должен реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>, а BindingList\`1 будет преобразовывать <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> события в <xref:System.ComponentModel.BindingList%601.ListChanged> событий типа <xref:System.ComponentModel.ListChangedType.ItemChanged>.

  > [!NOTE]
  > Чтобы уведомление об изменениях происходило в привязке между привязанным клиентом и источником данных, тип привязанного источника данных должен либо реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> (предпочтительно), либо указать *propertyName*`Changed` события для связанного типа, но не следует выполнять оба эти действия.

### <a name="interfaces-for-implementation-by-component-authors"></a>Интерфейсы для реализации авторами компонентов

Перечисленные ниже интерфейсы предназначены для использования модулем привязки данных в Windows Forms.

- интерфейс <xref:System.Windows.Forms.IBindableComponent>

  Класс, реализующий этот интерфейс, является компонентом без элемента управления, который поддерживает привязку данных. Этот класс возвращает привязки данных и контекст привязки компонента с помощью свойств <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> и <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> этого интерфейса.

  > [!NOTE]
  > Если компонент наследуется от <xref:System.Windows.Forms.Control>, не нужно реализовывать интерфейс <xref:System.Windows.Forms.IBindableComponent>.

- интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider>

  Класс, реализующий интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider>, является компонентом, предоставляющим собственные <xref:System.Windows.Forms.CurrencyManager> для управления привязками, связанными с этим конкретным компонентом. Доступ к пользовательскому <xref:System.Windows.Forms.CurrencyManager> предоставляется свойством <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>.

  > [!NOTE]
  > Класс, который наследует от <xref:System.Windows.Forms.Control>, автоматически управляет привязками через свойство <xref:System.Windows.Forms.Control.BindingContext%2A>, поэтому случаи, в которых необходимо реализовать <xref:System.Windows.Forms.ICurrencyManagerProvider>, довольно редки.

## <a name="see-also"></a>См. также:

- [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)
- [Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
