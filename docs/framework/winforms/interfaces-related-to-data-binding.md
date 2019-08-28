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
ms.openlocfilehash: 9f102b584d2ed0b5a9d2bbb0e7ce3f7871ec40b2
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046360"
---
# <a name="interfaces-related-to-data-binding"></a>Интерфейсы, относящиеся к привязке данных

С помощью ADO.NET можно создать множество различных структур данных в соответствии с потребностями привязки приложения и данными, с которыми вы работаете. Можно создать собственные классы, которые предоставляют или используют данные в Windows Forms. Такие объекты могут предоставлять функциональные возможности и обеспечивать сложность различного уровня, такие как базовая привязка данных, поддержка на этапе разработки, проверка ошибок, уведомление об изменениях или даже поддержка структурированного отката изменений, внесенных в сами данные.

## <a name="consumers-of-data-binding-interfaces"></a>Потребители интерфейсов привязки данных

Ниже описаны две группы объектов интерфейса. В первую группу входят интерфейсы, реализованные на основе источников данных авторами источников данных. Такие интерфейсы предназначены для использования потребителями источников данных, которыми в большинстве случаев являются элементы управления или компоненты Windows Forms. Ко второй группе относятся интерфейсы, используемые авторами компонентов. Авторы компонентов используют эти интерфейсы при создании компонента, поддерживающего привязку данных, которую должен применять модуль привязки данных Windows Forms. Данные интерфейсы можно реализовать внутри классов, связанных с вашей формой, чтобы обеспечить привязку данных. Каждый вариант представляет класс, реализующий интерфейс, позволяющий взаимодействовать с данными. Средства разработки данных для быстрой разработки приложений (RAD) в Visual Studio уже используют преимущества этой функции.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Интерфейсы для реализации авторами источников данных

Следующие интерфейсы предназначены для использования элементами управления Windows Forms.

- <xref:System.Collections.IList>взаимодействия

  Классом, реализующим <xref:System.Collections.IList> интерфейс <xref:System.Array>, может быть, <xref:System.Collections.ArrayList>или <xref:System.Collections.CollectionBase>. Это индексированные списки элементов типа <xref:System.Object>. Эти списки должны содержать однородные типы, так как первый элемент индекса определяет тип. <xref:System.Collections.IList>будет доступен для привязки только во время выполнения.

  > [!NOTE]
  > Если необходимо создать список бизнес-объектов для привязки с Windows Forms, рекомендуется использовать <xref:System.ComponentModel.BindingList%601>. <xref:System.ComponentModel.BindingList%601> — Это расширяемый класс, реализующий основные интерфейсы, необходимые для двусторонней Windows Forms привязки данных.

- <xref:System.ComponentModel.IBindingList>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.IBindingList> интерфейс, обеспечивает более высокий уровень функциональности привязки данных. Благодаря данной реализации у вас есть основные возможности сортировки и уведомлений об изменении как при изменении элементов списка (например, третий элемент в списке заказчиков имеет изменения в поле адреса), так и при изменении самого списка (например, увеличение или уменьшение числа элементов в списке). Уведомление об изменении важно, если вы планируете использовать несколько элементов управления, привязанных к одним и тем же данным, и необходимо, чтобы изменения данных, сделанные в одном из элементов управления, распространялись в другие привязанные элементы управления.

  > [!NOTE]
  > Уведомление <xref:System.ComponentModel.IBindingList> об изменении для интерфейса включается <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> через свойство, которое <xref:System.ComponentModel.IBindingList.ListChanged> , когда `true`, вызывает событие, указывающее на изменение списка или на изменение элемента в списке.

  Тип изменения описывается <xref:System.ComponentModel.ListChangedType> свойством <xref:System.ComponentModel.ListChangedEventArgs> параметра. Следовательно, при любом обновлении модели данных все зависимые представления, например другие элементы управления, привязанные к тому же источнику данных, также будут обновлены. Однако объекты, содержащиеся в списке, должны уведомлять список при изменении, чтобы список мог вызвать <xref:System.ComponentModel.IBindingList.ListChanged> событие.

  > [!NOTE]
  > Предоставляет универсальную реализацию <xref:System.ComponentModel.IBindingList>интерфейса. <xref:System.ComponentModel.BindingList%601>

- <xref:System.ComponentModel.IBindingListView>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.IBindingListView> интерфейс, предоставляет все функциональные возможности <xref:System.ComponentModel.IBindingList>реализации, а также функции фильтрации и расширенной сортировки. Такая реализация обеспечивает фильтрацию на основе строк и сортировку по нескольким столбцам с помощью пары "дескриптор свойства-направление".

- <xref:System.ComponentModel.IEditableObject>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.IEditableObject> интерфейс, позволяет объекту управлять тем, когда изменения в этом объекте сделаны постоянными. Эта реализация <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>предоставляет методы, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , которые позволяют выполнять откат изменений, внесенных в объект. Ниже приведено краткое описание функционирования <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>методов, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , а также способов их работы в сочетании друг с другом, чтобы обеспечить возможность отката изменений, внесенных в данные:

  - <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> Метод сигнализирует о начале редактирования объекта. Объект, реализующий этот интерфейс, должен сохранять любые обновления после <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> вызова метода таким образом, чтобы обновления можно было отменять <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> при вызове метода. В Windows Forms привязки <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> данных можно вызывать несколько раз в рамках одной транзакции изменения ( <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>например <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A>,,). Реализации должны отследить, был ли <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> метод уже вызван <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, и пропустить последующие вызовы. <xref:System.ComponentModel.IEditableObject> Поскольку этот метод может вызываться несколько раз, важно, чтобы последующие вызовы этого метода были необратимыми; Это значит, что <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> последующие вызовы не могут уничтожить произведенные обновления или изменить данные, сохраненные при первом <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> вызове.

  - Метод помещает все изменения с момента <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> вызова в базовый объект, если объект находится в режиме редактирования. <xref:System.ComponentModel.IEditableObject.EndEdit%2A>

  - <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> Метод отклоняет все изменения, внесенные в объект.

  Дополнительные сведения о <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>работе методов, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> см. в разделе [Сохранение данных в базе данных](/visualstudio/data-tools/save-data-back-to-the-database).

  Это транзакционное представление функциональных возможностей данных используется <xref:System.Windows.Forms.DataGridView> элементом управления.

- <xref:System.ComponentModel.ICancelAddNew>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.ICancelAddNew> интерфейс, обычно <xref:System.ComponentModel.IBindingList> реализует интерфейс и позволяет выполнить откат добавления к источнику данных с помощью <xref:System.ComponentModel.IBindingList.AddNew%2A> метода. Если источник данных реализует <xref:System.ComponentModel.IBindingList> интерфейс, необходимо также <xref:System.ComponentModel.ICancelAddNew> реализовать интерфейс.

- <xref:System.ComponentModel.IDataErrorInfo>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.IDataErrorInfo> интерфейс, позволяет объектам предлагать пользовательские сведения об ошибке для привязанных элементов управления:

  - <xref:System.ComponentModel.IDataErrorInfo.Error%2A> Свойство возвращает общий текст сообщения об ошибке (например, "произошла ошибка").

  - Свойство возвращает строку с конкретным сообщением об ошибке из столбца (например, "значение `State` в столбце является недопустимым"). <xref:System.ComponentModel.IDataErrorInfo.Item%2A>

- <xref:System.Collections.IEnumerable>взаимодействия

  Класс, реализующий <xref:System.Collections.IEnumerable> интерфейс, обычно используется ASP.NET. Windows Forms поддержка этого интерфейса доступна только через <xref:System.Windows.Forms.BindingSource> компонент.

  > [!NOTE]
  > Компонент копирует все <xref:System.Collections.IEnumerable> элементы в отдельный список для целей привязки. <xref:System.Windows.Forms.BindingSource>

- <xref:System.ComponentModel.ITypedList>взаимодействия

  Класс коллекций, реализующий <xref:System.ComponentModel.ITypedList> интерфейс, предоставляет возможность управлять порядком и набором свойств, предоставляемых привязанному элементу управления.

  > [!NOTE]
  > При реализации <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> метода, <xref:System.ComponentModel.PropertyDescriptor> если массив не равен null, последняя запись в массиве будет дескриптором свойства, описывающим свойство списка, которое является другим списком элементов.

- <xref:System.ComponentModel.ICustomTypeDescriptor>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.ICustomTypeDescriptor> интерфейс, предоставляет динамические сведения о себе. Этот интерфейс аналогичен <xref:System.ComponentModel.ITypedList> , но используется для объектов, а не списков. Этот интерфейс используется <xref:System.Data.DataRowView> для проецирования схемы базовых строк. Простая реализация <xref:System.ComponentModel.ICustomTypeDescriptor> предоставляется <xref:System.ComponentModel.CustomTypeDescriptor> классом.

  > [!NOTE]
  > Для поддержки привязки времени разработки к типам, реализующим <xref:System.ComponentModel.ICustomTypeDescriptor>, тип должен также реализовывать <xref:System.ComponentModel.IComponent> и существовать как экземпляр в форме.

- <xref:System.ComponentModel.IListSource>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.IListSource> интерфейс, обеспечивает привязку на основе списка для объектов, не являющихся списками. Метод используется для возврата связываемого списка из объекта, который не наследует от <xref:System.Collections.IList>. <xref:System.ComponentModel.IListSource.GetList%2A> <xref:System.ComponentModel.IListSource> <xref:System.ComponentModel.IListSource>используется <xref:System.Data.DataSet> классом.

- <xref:System.ComponentModel.IRaiseItemChangedEvents>взаимодействия

  Класс, реализующий <xref:System.ComponentModel.IRaiseItemChangedEvents> интерфейс, является связываемым списком, который также <xref:System.ComponentModel.IBindingList> реализует интерфейс. Этот интерфейс используется для указания, создает <xref:System.ComponentModel.IBindingList.ListChanged> ли ваш тип события типа <xref:System.ComponentModel.ListChangedType.ItemChanged> через его <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> свойство.

  > [!NOTE]
  > Следует реализовать, <xref:System.ComponentModel.IRaiseItemChangedEvents> если источник данных предоставляет свойство для перечисления событий, описанное ранее, и взаимодействует <xref:System.Windows.Forms.BindingSource> с компонентом. В противном случае будет также выполнено преобразование свойства в список событий, что привело к снижению производительности. <xref:System.Windows.Forms.BindingSource>

- <xref:System.ComponentModel.ISupportInitialize>взаимодействия

  Компонент, реализующий <xref:System.ComponentModel.ISupportInitialize> интерфейс, использует преимущества пакетной оптимизации для настройки свойств и инициализации свойств, зависящих от совместной работы. <xref:System.ComponentModel.ISupportInitialize> Содержит два метода:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A>сигнализирует, что инициализация объекта начинается.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>сигнализирует, что инициализация объекта завершена.

- <xref:System.ComponentModel.ISupportInitializeNotification>взаимодействия

  Компонент, реализующий <xref:System.ComponentModel.ISupportInitializeNotification> интерфейс, также <xref:System.ComponentModel.ISupportInitialize> реализует интерфейс. Этот интерфейс позволяет уведомлять другие <xref:System.ComponentModel.ISupportInitialize> компоненты о завершении инициализации. <xref:System.ComponentModel.ISupportInitializeNotification> Интерфейс содержит два члена:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A>`boolean` возвращает значение, указывающее, инициализирован ли компонент.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized>происходит при <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> вызове метода.

- <xref:System.ComponentModel.INotifyPropertyChanged>взаимодействия

  Класс, реализующий этот интерфейс, представляет собой тип, который вызывает событие при изменении любого значения его свойств. Этот интерфейс предназначен для замены шаблона, в рамках которого имеется отдельное событие изменения для каждого свойства элемента управления. <xref:System.ComponentModel.BindingList%601>При использовании в бизнес-объект должен <xref:System.ComponentModel.INotifyPropertyChanged> реализовать интерфейс, а BindingList\`1 преобразует <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> события в <xref:System.ComponentModel.BindingList%601.ListChanged> события типа <xref:System.ComponentModel.ListChangedType.ItemChanged>.

  > [!NOTE]
  > Чтобы уведомление об изменениях происходило в привязке между привязанным клиентом и источником данных, тип привязанного источника данных должен либо реализовать <xref:System.ComponentModel.INotifyPropertyChanged> интерфейс (предпочтительно), либо предоставить события *PropertyName* `Changed` для связанного типа. но не следует выполнять оба действия.

### <a name="interfaces-for-implementation-by-component-authors"></a>Интерфейсы для реализации авторами компонентов

Перечисленные ниже интерфейсы предназначены для использования модулем привязки данных в Windows Forms.

- <xref:System.Windows.Forms.IBindableComponent>взаимодействия

  Класс, реализующий этот интерфейс, является компонентом без элемента управления, который поддерживает привязку данных. Этот класс возвращает привязки данных и контекст привязки компонента с помощью <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> свойств и <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> этого интерфейса.

  > [!NOTE]
  > Если компонент наследуется от <xref:System.Windows.Forms.Control>, <xref:System.Windows.Forms.IBindableComponent> реализовывать интерфейс не требуется.

- <xref:System.Windows.Forms.ICurrencyManagerProvider>взаимодействия

  Класс, реализующий <xref:System.Windows.Forms.ICurrencyManagerProvider> интерфейс, является компонентом, предоставляющим собственный <xref:System.Windows.Forms.CurrencyManager> для управления привязками, связанными с этим конкретным компонентом. Доступ к настраиваемому <xref:System.Windows.Forms.CurrencyManager> параметру предоставляется <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> свойством.

  > [!NOTE]
  > Класс, который наследует от <xref:System.Windows.Forms.Control> управления привязками, автоматически управляется с помощью его <xref:System.Windows.Forms.Control.BindingContext%2A> свойства, поэтому случаи, в которых <xref:System.Windows.Forms.ICurrencyManagerProvider> необходимо реализовать, являются довольно редкими.

## <a name="see-also"></a>См. также

- [Привязка данных и Windows Forms](data-binding-and-windows-forms.md)
- [Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Привязка данных Windows Forms](windows-forms-data-binding.md)
