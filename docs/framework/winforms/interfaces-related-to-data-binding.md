---
title: "Интерфейсы, относящиеся к связыванию данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "данные [Windows Forms], интерфейсы привязки данных"
  - "привязка данных, интерфейсы"
  - "IBindingList - интерфейс, связывание данных Windows Forms"
  - "IBindingListView - интерфейс"
  - "IDataErrorInfo - интерфейс, связывание данных Windows Forms"
  - "IEditableObject - интерфейс, связывание данных Windows Forms"
  - "IList - интерфейс, связывание данных Windows Forms"
  - "INotifyPropertyChanged - интерфейс"
  - "интерфейсы, связывание данных Windows Forms"
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Интерфейсы, относящиеся к связыванию данных
C помощью [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] можно создать несколько различных структур данных, удовлетворяющих требованиям привязки приложений и обрабатываемых данных.  Чтобы предоставлять или использовать данные в Windows Forms, может потребоваться создать собственные классы.  Эти объекты могут различаться уровнями функциональных возможностей и сложностью и обеспечивать как простую привязку данных, так и поддержку времени разработки, проверку ошибок, уведомление об изменениях или даже поддержку структурированного отката изменений, внесенных непосредственно в данные.  
  
## Потребители интерфейсов привязки данных  
 В следующих разделах описываются две группы объектов интерфейса.  В первую группу входят интерфейсы, которые реализованы на основе источников данных авторами источников данных.  Эти интерфейсы предназначены для использования потребителями источников данных, которые в большинстве случаев являются элементами управления или компонентами Windows Forms.  Вторая группа интерфейсов предназначена для использования авторами компонентов.  Авторы компонентов используют эти интерфейсы при создании компонентов, поддерживающих привязку данных, которая должна использоваться ядром привязки данных Windows Forms.  Эти интерфейсы можно реализовать в классах, связанных с формой, чтобы разрешить привязку данных; каждый вариант представляет класс, реализующий интерфейс, через который осуществляется взаимодействие с данными.  Преимущества этих функциональных возможностей уже поддерживаются средствами разработки данных в среде быстрой разработки приложений \(RAD\) [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
### Интерфейсы, предназначенные для реализации авторами источников данных  
 Перечисленные ниже интерфейсы предназначены для использования элементами управления Windows Forms.  
  
-   Интерфейс <xref:System.Collections.IList>  
  
     Интерфейс <xref:System.Collections.IList> можно реализовать в классе <xref:System.Array>, <xref:System.Collections.ArrayList> или <xref:System.Collections.CollectionBase>.  Эти классы представляют собой индексированные списки типа <xref:System.Object>.  В этих списках должны содержаться однородные типы, потому что первый элемент индекса определяет тип.  Список <xref:System.Collections.IList> доступен для связывания только во время выполнения.  
  
    > [!NOTE]
    >  Если требуется создать список бизнес\-объектов для привязки с элементами управления Windows Forms, следует использовать интерфейс <xref:System.ComponentModel.BindingList%601>.  <xref:System.ComponentModel.BindingList%601> представляет собой расширяемый класс, реализующий интерфейсы для двусторонней привязки данных Windows Forms.  
  
-   Интерфейс <xref:System.ComponentModel.IBindingList>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.IBindingList>, обеспечивает более высокий уровень возможностей привязки данных.  Реализация этого интерфейса предоставляет основные возможности сортировки и поддерживает уведомления об изменениях, касающихся элементов списка \(например, обновилось поле "Адрес" третьего элемента в списке заказчиков\) или связанных с самим списком \(например, увеличилось или уменьшилось количество элементов списка\).  Уведомления об изменениях становятся особенно важными, если планируется привязать к одним данным несколько элементов управления и необходимо распространить изменения данных, выполненные в одном элементе управления, на все другие связанные элементы управления.  
  
    > [!NOTE]
    >  Уведомления об изменениях включаются для интерфейса <xref:System.ComponentModel.IBindingList> посредством свойства <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A>. Если это свойство принимает значение `true`, инициируется событие <xref:System.ComponentModel.IBindingList.ListChanged>, которое означает, что изменен список или элемент списка.  
  
     Тип изменения описывается свойством <xref:System.ComponentModel.ListChangedType> параметра <xref:System.ComponentModel.ListChangedEventArgs>.  Поэтому при любом обновлении модели данных все зависимые представления, например другие элементы управления, привязанные к тем же данным, также будут обновлены.  Однако для того, чтобы список вызвал событие <xref:System.ComponentModel.IBindingList.ListChanged>, объекты списка должны будут уведомить список при изменении.  
  
    > [!NOTE]
    >  Класс <xref:System.ComponentModel.BindingList%601> предоставляет общую реализацию интерфейса <xref:System.ComponentModel.IBindingList>.  
  
-   Интерфейс <xref:System.ComponentModel.IBindingListView>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.IBindingListView>, предоставляет все возможности реализации интерфейса <xref:System.ComponentModel.IBindingList>, а также обеспечивает функции фильтрации и расширенной сортировки.  Эта реализация предлагает фильтрацию на основе строк и сортировку по нескольким столбцам, использующую пары свойств "дескриптор\-направление".  
  
-   Интерфейс <xref:System.ComponentModel.IEditableObject>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.IEditableObject>, позволяет объектам определять, являются ли изменения, произведенные в этих объектах, окончательными.  Благодаря этой реализации можно использовать методы <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, которые обеспечивают возможность отката изменений объекта.  Ниже представлено краткое объяснение работы методов <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>, а также описано их взаимодействие при обеспечении возможности отката изменений данных.  
  
    -   Метод <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> сигнализирует о начале изменения объекта.  Объект, реализующий этот интерфейс, должен сохранить все обновления, внесенные после вызова метода <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> таким образом, чтобы они могли быть отменены при вызове метода <xref:System.ComponentModel.IEditableObject.CancelEdit%2A>.  В Windows Forms, где используется привязка данных, можно вызывать метод <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> несколько раз в пределах одной транзакции изменения \(например, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A>\).  Реализации объекта <xref:System.ComponentModel.IEditableObject> должны отслеживать, был ли вызван метод <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, и игнорировать последующие вызовы метода <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.  Так как этот метод можно вызывать несколько раз, важно, чтобы последующие вызовы были безопасными; к примеру, повторные вызовы метода <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> не могут отменить внесенные обновления или изменить данные, которые были сохранены при первом вызове метода <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>.  
  
    -   Метод <xref:System.ComponentModel.IEditableObject.EndEdit%2A> записывает все изменения, внесенные после вызова метода <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, в основной объект, если он находится в режиме редактирования.  
  
    -   Метод <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> отменяет все изменения, внесенные в объект.  
  
     Дополнительные сведения о работе методов <xref:System.ComponentModel.IEditableObject.BeginEdit%2A>, <xref:System.ComponentModel.IEditableObject.EndEdit%2A> и <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> см. в разделе [Сохранение данных в наборах данных](../Topic/Save%20data%20back%20to%20the%20database.md).  
  
     Такое транзакционное представление функциональных возможностей данных используется элементом управления <xref:System.Windows.Forms.DataGridView>.  
  
-   Интерфейс <xref:System.ComponentModel.ICancelAddNew>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.ICancelAddNew>, обычно реализует интерфейс <xref:System.ComponentModel.IBindingList> и позволяет выполнить откат добавлений к источнику данных, сделанных с помощью метода <xref:System.ComponentModel.IBindingList.AddNew%2A>.  Если источник данных реализует интерфейс <xref:System.ComponentModel.IBindingList>, он также должен реализовать интерфейс <xref:System.ComponentModel.ICancelAddNew>.  
  
-   Интерфейс <xref:System.ComponentModel.IDataErrorInfo>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.IDataErrorInfo>, позволяет объектам предоставлять связанным элементам управления специализированные сведения об ошибках.  
  
    -   Свойство <xref:System.ComponentModel.IDataErrorInfo.Error%2A> возвращает общее сообщение об ошибке \(например, "Произошла ошибка"\).  
  
    -   Свойство <xref:System.ComponentModel.IDataErrorInfo.Item%2A> возвращает строку с конкретным сообщением об ошибке из столбца \(например, "Недопустимое значение в столбце `State` "\).  
  
-   Интерфейс <xref:System.Collections.IEnumerable>  
  
     Класс, реализующий интерфейс <xref:System.Collections.IEnumerable>, обычно используется в [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].  Для поддержки этого интерфейса в Windows Forms должен присутствовать компонент <xref:System.Windows.Forms.BindingSource>.  
  
    > [!NOTE]
    >  Компонент <xref:System.Windows.Forms.BindingSource> копирует все элементы <xref:System.Collections.IEnumerable> в отдельный список, предназначенный исключительно для привязки.  
  
-   Интерфейс <xref:System.ComponentModel.ITypedList>  
  
     Класс "Collections", реализующий интерфейс <xref:System.ComponentModel.ITypedList>, позволяет управлять порядком и набором свойств, доступных связанному элементу управления.  
  
    > [!NOTE]
    >  Если при реализации метода <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> массив <xref:System.ComponentModel.PropertyDescriptor> не является нулевым, последняя запись этого массива является дескриптором свойства, который описывает свойство списка, являющееся другим списком элементов.  
  
-   Интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor>, предоставляет динамические сведения о себе.  Этот интерфейс подобен интерфейсу <xref:System.ComponentModel.ITypedList>, однако он используется не для списков, а для объектов.  Данный интерфейс используется объектом <xref:System.Data.DataRowView> для применения схемы основных строк.  Простая реализация интерфейса <xref:System.ComponentModel.ICustomTypeDescriptor> предоставляется классом <xref:System.ComponentModel.CustomTypeDescriptor>.  
  
    > [!NOTE]
    >  Для поддержки привязки времени разработки для типов, реализующих интерфейс <xref:System.ComponentModel.ICustomTypeDescriptor>, эти типы должны также реализовать интерфейс <xref:System.ComponentModel.IComponent> и существовать в качестве экземпляра для формы.  
  
-   Интерфейс <xref:System.ComponentModel.IListSource>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.IListSource>, обеспечивает привязку на основе списка для объектов, не являющихся списками.  Метод <xref:System.ComponentModel.IListSource.GetList%2A> объекта <xref:System.ComponentModel.IListSource> используется, чтобы возвратить связываемый список из объекта, не наследующего от списка <xref:System.Collections.IList>.  Объект <xref:System.ComponentModel.IListSource> используется классом <xref:System.Data.DataSet>.  
  
-   Интерфейс <xref:System.ComponentModel.IRaiseItemChangedEvents>  
  
     Класс, реализующий интерфейс <xref:System.ComponentModel.IRaiseItemChangedEvents>, представляет собой связываемый список, который также реализует интерфейс <xref:System.ComponentModel.IBindingList>.  Этот интерфейс используется для определения, вызывает ли данный тип событие <xref:System.ComponentModel.IBindingList.ListChanged> типа <xref:System.ComponentModel.ListChangedType> посредством своего свойства <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A>.  
  
    > [!NOTE]
    >  Интерфейс <xref:System.ComponentModel.IRaiseItemChangedEvents> следует реализовать, только если источник данных обеспечивает описанное ранее преобразование свойства в список и взаимодействует с компонентом <xref:System.Windows.Forms.BindingSource>.  В противном случае, интерфейс <xref:System.Windows.Forms.BindingSource> также будет выполнять преобразование свойства в список, что приведет к снижению производительности.  
  
-   Интерфейс <xref:System.ComponentModel.ISupportInitialize>  
  
     Компонент, реализующий интерфейс <xref:System.ComponentModel.ISupportInitialize>, использует преимущества пакетной оптимизации для задания свойств и инициализации взаимозависимых свойств.  Интерфейс <xref:System.ComponentModel.ISupportInitialize> содержит два метода, перечисленных ниже.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> подает сигнал о начале инициализации объекта.  
  
    -   <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> подает сигнал об окончании инициализации объекта.  
  
-   Интерфейс <xref:System.ComponentModel.ISupportInitializeNotification>  
  
     Компонент, реализующий интерфейс <xref:System.ComponentModel.ISupportInitializeNotification>, также реализует интерфейс <xref:System.ComponentModel.ISupportInitialize>.  Этот интерфейс позволяет уведомлять другие компоненты <xref:System.ComponentModel.ISupportInitialize> о завершении инициализации.  Интерфейс <xref:System.ComponentModel.ISupportInitializeNotification> содержит два метода, перечисленных ниже.  
  
    -   Метод <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> возвращает `boolean` значение, указывающее, инициализирован ли компонент.  
  
    -   Событие <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> возникает при вызове метода <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>.  
  
-   Интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>  
  
     Класс, реализующий этот интерфейс, является типом, который вызывает событие при изменении значений его свойств.  Данный интерфейс может использоваться вместо вызова отдельного события изменения для каждого свойства элемента управления.  При использовании в классе <xref:System.ComponentModel.BindingList%601> бизнес\-объект должен реализовывать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>; при этом класс "BindingList\`1" будет преобразовывать события <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> в события <xref:System.ComponentModel.BindingList%601.ListChanged> типа <xref:System.ComponentModel.ListChangedType>.  
  
    > [!NOTE]
    >  Для уведомления об изменениях, возникающих в привязке между связанным клиентом и источником данных, связанный тип источника данных должен реализовывать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> \(рекомендуется\). Можно также предоставить для связанного типа события *propertyName*`Changed`, однако не следует выполнять обоих действий одновременно.  
  
### Интерфейсы, предназначенные для реализации авторами компонентов  
 Перечисленные ниже интерфейсы предназначены для использования ядром привязки данных Windows Forms.  
  
-   Интерфейс <xref:System.Windows.Forms.IBindableComponent>  
  
     Класс, реализующий этот интерфейс, представляет собой поддерживающий привязку данных компонент, который не является элементом управления.  Этот класс возвращает привязки данных и контекст привязки компонента посредством свойств <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> и <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> данного интерфейса.  
  
    > [!NOTE]
    >  Если данный компонент наследуется от элемента <xref:System.Windows.Forms.Control>, интерфейс <xref:System.Windows.Forms.IBindableComponent> реализовывать не требуется.  
  
-   Интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider>  
  
     Класс, реализующий интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider>, является компонентом, который предоставляет собственный класс <xref:System.Windows.Forms.CurrencyManager> для управления привязками, связанными с данным конкретным компонентом.  Доступ к пользовательскому классу <xref:System.Windows.Forms.CurrencyManager> предоставляется посредством свойства <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>.  
  
    > [!NOTE]
    >  Класс, который наследуется от элемента <xref:System.Windows.Forms.Control>, управляет привязками автоматически посредством своего свойства <xref:System.Windows.Forms.Control.BindingContext%2A>, поэтому реализовывать интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider> требуется лишь в редких случаях.  
  
## См. также  
 [Связывание данных и Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Практическое руководство. Создание элемента управления с простой привязкой в форме Windows Forms](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [Связывание элементов управления Windows Forms с данными](../../../docs/framework/winforms/windows-forms-data-binding.md)