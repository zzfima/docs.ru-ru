---
title: "Архитектура компонента BindingSource | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "BindingSource - компонент [Windows Forms], сведения о компоненте BindingSource"
  - "BindingSource - компонент, архитектура"
  - "привязка данных, BindingSource - компонент"
  - "Windows Forms, привязка данных"
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
caps.latest.revision: 23
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 23
---
# Архитектура компонента BindingSource
Компонент <xref:System.Windows.Forms.BindingSource> обеспечивает возможность универсальной привязки всех элементов управления Windows Forms к источникам данных.  
  
 Компонент <xref:System.Windows.Forms.BindingSource> упрощает процесс привязки элемента управления к источнику данных и обладает следующими преимуществами по сравнению с традиционной привязкой данных.  
  
-   Позволяет осуществлять привязку к бизнес\-объектам на этапе разработки.  
  
-   Включает функциональные возможности <xref:System.Windows.Forms.CurrencyManager> и предоставляет доступ к событиям <xref:System.Windows.Forms.CurrencyManager> на этапе разработки.  
  
-   Упрощает создание списка, поддерживающего интерфейс <xref:System.ComponentModel.IBindingList>, за счет создания уведомления об изменении списка для источников данных, которые изначально не поддерживали это уведомление.  
  
-   Обеспечивает точку расширения для метода <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=fullName>.  
  
-   Обеспечивает косвенное обращение элемента управления к источнику данных.  Такое обращение очень важно в тех случаях, когда источник данных может изменяться во время выполнения.  
  
-   Взаимодействует с другими элементами управления Windows Forms, связанными с данными, особенно с элементами управления <xref:System.Windows.Forms.BindingNavigator> и <xref:System.Windows.Forms.DataGridView>.  
  
 Именно благодаря всем этим преимуществам компонент <xref:System.Windows.Forms.BindingSource> является предпочтительным способом привязки элементов управления Windows Forms к источникам данных.  
  
## Возможности компонента BindingSource  
 Компонент <xref:System.Windows.Forms.BindingSource> предлагает ряд возможностей для привязки элементов управления к данным.  Благодаря этим возможностям реализация большинства сценариев привязки данных практически не требует написания кода.  
  
 Это достигается за счет предоставления компонентом <xref:System.Windows.Forms.BindingSource> соответствующего интерфейса для доступа к множеству различных видов источников данных.  Это означает, что для привязки к любому типу источника используется одна и та же процедура.  Например, можно вложить свойство <xref:System.Windows.Forms.BindingSource.DataSource%2A> в <xref:System.Data.DataSet> или в бизнес\-объект, при этом в обоих случаях для работы с источником данных используется один и тот же набор свойств, методов и событий.  
  
 Согласованный интерфейс, предоставляемый компонентом <xref:System.Windows.Forms.BindingSource>, способствует значительному упрощению процесса привязки данных к элементам управления.  Для тех типов источников данных, которые создают уведомление об изменениях, компонент <xref:System.Windows.Forms.BindingSource> обеспечивает автоматический обмен данными об изменениях между элементом управления и источником данных.  Для тех типов источников данных, которые не создают уведомлений об изменениях, предусмотрены события, позволяющие инициировать эти уведомления.  В следующем списке перечислены возможности, поддерживаемые компонентом <xref:System.Windows.Forms.BindingSource>.  
  
-   Косвенное обращение.  
  
-   Оперативное управление.  
  
-   Источник данных в виде списка.  
  
-   <xref:System.Windows.Forms.BindingSource> в виде <xref:System.ComponentModel.IBindingList>.  
  
-   Создание пользовательских элементов.  
  
-   Создание транзакционных элементов.  
  
-   Поддержка <xref:System.Collections.IEnumerable>.  
  
-   Поддержка на этапе разработки.  
  
-   Статические методы <xref:System.Windows.Forms.ListBindingHelper>.  
  
-   Сортировка и фильтрация с использованием интерфейса <xref:System.ComponentModel.IBindingListView>.  
  
-   Интеграция с конструктором служб <xref:System.Windows.Forms.BindingNavigator>.  
  
### Косвенное обращение  
 Компонент <xref:System.Windows.Forms.BindingSource> обеспечивает косвенное обращение элемента управления к источнику данных.  Элемент управления привязывается не напрямую к источнику данных, а к компоненту <xref:System.Windows.Forms.BindingSource>, а источник данных присоединяется к свойству <xref:System.Windows.Forms.BindingSource.DataSource%2A> компонента <xref:System.Windows.Forms.BindingSource>.  
  
 Такой уровень косвенного обращения позволяет изменять источники данных без сброса привязки элемента управления.  Это, в свою очередь, позволяет выполнять следующие действия.  
  
-   Присоединять компонент <xref:System.Windows.Forms.BindingSource> к различным источникам данных, сохраняя при этом текущие привязки элементов управления.  
  
-   Изменять элементы в источнике данных и уведомлять связанные элементы управления.  Дополнительные сведения см. в разделе [Практическое руководство. Отражение в элементе управления данных, которые обновились в источнике, с использованием компонента BindingSource в Windows Forms](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
-   Выполнять привязку к <xref:System.Type> вместо объекта в памяти.  Дополнительные сведения см. в разделе [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  После этого можно осуществить привязку к объекту во время выполнения.  
  
### Оперативное управление  
 Компонент <xref:System.Windows.Forms.BindingSource> использует интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider> для обработки процессов оперативного управления.  Кроме того, интерфейс <xref:System.Windows.Forms.ICurrencyManagerProvider> предоставляет доступ к средству управления текущей записью для компонента <xref:System.Windows.Forms.BindingSource>, а также к средству управления текущей записью для другого компонента <xref:System.Windows.Forms.BindingSource>, привязанного к тому же <xref:System.Windows.Forms.BindingSource.DataMember%2A>.  
  
 Компонент <xref:System.Windows.Forms.BindingSource> включает функциональные возможности <xref:System.Windows.Forms.CurrencyManager> и предоставляет стандартные свойства и события <xref:System.Windows.Forms.CurrencyManager>.  В следующей таблице представлены некоторые элементы, связанные с оперативным управлением.  
  
 Свойство <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Возвращает средство управления текущей записью, связанное с компонентом <xref:System.Windows.Forms.BindingSource>.  
  
 Метод <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Если существует другой компонент <xref:System.Windows.Forms.BindingSource>, связанный с определенным элементом данных, возвращает его средство управления текущей записью.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.Current%2A>  
 Возвращает текущий элемент источника данных.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.Position%2A>  
 Получает или задает текущую позицию в базовом списке.  
  
 Метод <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Применяет ожидающие изменения к базовому источнику данных.  
  
 Метод <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Отменяет текущую операцию редактирования.  
  
### Источник данных в виде списка  
 Компонент <xref:System.Windows.Forms.BindingSource> реализует интерфейсы <xref:System.ComponentModel.IBindingListView> и <xref:System.ComponentModel.ITypedList>.  Такая реализация позволяет использовать компонент <xref:System.Windows.Forms.BindingSource> в качестве источника данных без какого\-либо внешнего хранилища.  
  
 Если компонент <xref:System.Windows.Forms.BindingSource> вложен в источник данных, он представляет этот источник в виде списка.  
  
 Свойство <xref:System.Windows.Forms.BindingSource.DataSource%2A> может быть задано для нескольких источников данных.  Это могут быть типы, объекты и списки типов.  Полученный источник данных будет представлен в виде списка.  В следующей таблице показаны некоторые стандартные источники данных и оценка полученного списка.  
  
|Свойство DataSource|Результаты в списке|  
|-------------------------|-------------------------|  
|Пустая ссылка \(значение `Nothing` в Visual Basic\)|Пустой <xref:System.ComponentModel.IBindingList> объектов.  Добавление элемента присваивает списку тип этого элемента.|  
|Пустая ссылка \(значение `Nothing` в Visual Basic\) с набором <xref:System.Windows.Forms.BindingSource.DataMember%2A>|Не поддерживается; вызывает <xref:System.ArgumentException>.|  
|Тип, не являющийся списком, или объект типа "Т"|Пустой <xref:System.ComponentModel.IBindingList> типа "Т".|  
|Экземпляр массива|Список <xref:System.ComponentModel.IBindingList>, содержащий элементы массива.|  
|Экземпляр <xref:System.Collections.IEnumerable>|Список <xref:System.ComponentModel.IBindingList>, содержащий элементы <xref:System.Collections.IEnumerable>|  
|Экземпляр списка, содержащий тип "Т"|Экземпляр <xref:System.ComponentModel.IBindingList>, содержащий тип "Т".|  
  
 Кроме того, <xref:System.Windows.Forms.BindingSource.DataSource%2A> можно задать для других типов списков, например <xref:System.ComponentModel.IListSource> и <xref:System.ComponentModel.ITypedList>, и тогда <xref:System.Windows.Forms.BindingSource> будет обрабатывать их соответствующим образом.  В этом случае тип, содержащийся в списке, должен иметь конструктор по умолчанию.  
  
### BindingSource в виде IBindingList  
 Компонент <xref:System.Windows.Forms.BindingSource> предоставляет элементы для доступа к базовым данным и управлению ими в качестве <xref:System.ComponentModel.IBindingList>.  В приведенной ниже таблице описаны некоторые из этих элементов.  
  
|Элемент|Описание|  
|-------------|--------------|  
|Свойство <xref:System.Windows.Forms.BindingSource.List%2A>|Возвращает список с результатами вычислений значений свойств <xref:System.Windows.Forms.BindingSource.DataSource%2A> или <xref:System.Windows.Forms.BindingSource.DataMember%2A>.|  
|Метод <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Добавляет новый элемент в базовый список.  Применяется к источникам данных, которые реализуют интерфейс <xref:System.ComponentModel.IBindingList> и позволяют добавлять элементы \(т. е. источникам, для которых свойству <xref:System.Windows.Forms.BindingSource.AllowNew%2A> задано значение `true`\).|  
  
### Создание пользовательских элементов  
 Можно добавить собственную логику создания элементов путем обработки события <xref:System.Windows.Forms.BindingSource.AddingNew>.  Событие <xref:System.Windows.Forms.BindingSource.AddingNew> происходит перед добавлением нового объекта в <xref:System.Windows.Forms.BindingSource>.  Это событие вызывается после вызова метода <xref:System.Windows.Forms.BindingSource.AddNew%2A>, но прежде добавления нового объекта в базовый список.  Обработка этого события позволяет добавить поведение создания пользовательских элементов без наследования из класса <xref:System.Windows.Forms.BindingSource>.  Дополнительные сведения см. в разделе [Практическое руководство. Настройка дополнений к элементам с помощью элемента управления BindingSource в Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### Создание транзакционных элементов  
 Компонент <xref:System.Windows.Forms.BindingSource> реализует интерфейс <xref:System.ComponentModel.ICancelAddNew>, который позволяет создавать транзакционные элементы.  После того как новый элемент условно создан путем обращения к <xref:System.Windows.Forms.BindingSource.AddNew%2A>, его добавление можно подтвердить или отменить следующими способами.  
  
-   Метод <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> явным образом подтверждает отложенное добавление.  
  
-   Выполнение другой операции сбора, например вставки, удаления или перемещения, неявным образом подтверждает отложенное добавление.  
  
-   Метод <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A> отменяет отложенное добавление, если этот метод не был предварительно подтвержден.  
  
### Поддержка интерфейса IEnumerable  
 Компонент <xref:System.Windows.Forms.BindingSource> позволяет привязывать элементы управления к источникам данных <xref:System.Collections.IEnumerable>.  Это дает возможность выполнять привязку к таким источникам данных как <xref:System.Data.SqlClient.SqlDataReader?displayProperty=fullName>.  
  
 Если источник данных <xref:System.Collections.IEnumerable> назначен компоненту <xref:System.Windows.Forms.BindingSource>, компонент <xref:System.Windows.Forms.BindingSource> создает <xref:System.ComponentModel.IBindingList> и добавляет в этот список содержимое источника данных <xref:System.Collections.IEnumerable>.  
  
### Поддержка на этапе разработки  
 Некоторые типы объектов невозможно создать на этапе разработки. Это, например, объекты, созданные из класса фабрики, или объекты, возвращенные веб\-службой.  Иногда требуется привязывать элементы управления к таким типам объектов на стадии разработки несмотря на отсутствие в памяти каких\-либо объектов, к которым можно выполнить привязку.  Например, может потребоваться пометить заголовки столбцов элемента управления <xref:System.Windows.Forms.DataGridView> именами общих свойств пользовательского типа.  
  
 Для выполнения такого сценария предусмотрена поддержка компонентом <xref:System.Windows.Forms.BindingSource> привязки к <xref:System.Type>.  При назначении <xref:System.Type> свойству <xref:System.Windows.Forms.BindingSource.DataSource%2A> компонент <xref:System.Windows.Forms.BindingSource> создает пустой <xref:System.ComponentModel.BindingList%601> элементов <xref:System.Type>.  Любые элементы управления, которые в дальнейшем будут привязываться к компоненту <xref:System.Windows.Forms.BindingSource>, получат уведомление о присутствии свойств или схемы данного типа на этапе разработки или выполнения.  Дополнительные сведения см. в разделе [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### Статические методы ListBindingHelper  
 Типы <xref:System.Windows.Forms.BindingContext?displayProperty=fullName>, <xref:System.Windows.Forms.CurrencyManager?displayProperty=fullName> и <xref:System.Windows.Forms.BindingSource> используют одну и ту же логику для создания списка из пары `DataSource`\/`DataMember`.  Кроме того, эта общая логика открыта для использования авторами элементов управления и другими третьими лицами в следующих `static` методах.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
-   <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### Сортировка и фильтрация с использованием интерфейса IBindingListView  
 Компонент <xref:System.Windows.Forms.BindingSource> реализует интерфейс <xref:System.ComponentModel.IBindingListView>, который является расширением интерфейса <xref:System.ComponentModel.IBindingList>.  <xref:System.ComponentModel.IBindingList> предлагает сортировку по единственному столбцу, в то время как <xref:System.ComponentModel.IBindingListView> предлагает улучшенную сортировку и фильтрацию.  Интерфейс <xref:System.ComponentModel.IBindingListView> позволяет сортировать и фильтровать элементы в источнике данных, если этот источник также реализует один из этих интерфейсов.  Компонент <xref:System.Windows.Forms.BindingSource> не обеспечивает ссылочную реализацию этих элементов.  Вместо этого выполняется перенаправление вызовов в базовый список.  
  
 В следующей таблице описаны свойства, которые используются для сортировки и фильтрации.  
  
|Элемент|Описание|  
|-------------|--------------|  
|Свойство <xref:System.Windows.Forms.BindingSource.Filter%2A>|Если в качестве источника данных используется <xref:System.ComponentModel.IBindingListView>, получает или задает выражение, используемое для фильтрации отображаемых строк.|  
|Свойство <xref:System.Windows.Forms.BindingSource.Sort%2A>|Если в качестве источника данных используется <xref:System.ComponentModel.IBindingList>, Получает или задает имя используемого для сортировки столбца и порядок сортировки.<br /><br /> \-или\-<br /><br /> Если в качестве источника данных используется <xref:System.ComponentModel.IBindingListView> с поддержкой расширенной сортировки, возвращает имена нескольких используемых для сортировки столбцов и порядок сортировки.|  
  
### Интеграция с BindingNavigator  
 Компонент <xref:System.Windows.Forms.BindingSource> можно использовать для привязки к источнику данных любых элементов управления Windows Forms, однако элемент управления <xref:System.Windows.Forms.BindingNavigator> может работать только с компонентом <xref:System.Windows.Forms.BindingSource>.  Элемент управления <xref:System.Windows.Forms.BindingNavigator> предоставляет пользовательский интерфейс для управления текущими элементами компонента <xref:System.Windows.Forms.BindingSource>.  По умолчанию элемент управления <xref:System.Windows.Forms.BindingNavigator> предлагает кнопки, отвечающие методам навигации компонента <xref:System.Windows.Forms.BindingSource>.  Дополнительные сведения см. в разделе [Практическое руководство. Переход между данными с помощью элемента управления BindingNavigator в Windows Forms](../../../../docs/framework/winforms/controls/how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## См. также  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.BindingNavigator>   
 [Общие сведения о компоненте BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component-overview.md)   
 [Элемент управления BindingNavigator](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [Связывание элементов управления Windows Forms с данными](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Элементы управления для использования в формах Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)   
 [Практическое руководство. Связывание элемента управления с типом в Windows Forms](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)   
 [Практическое руководство. Отражение в элементе управления данных, которые обновились в источнике, с использованием компонента BindingSource в Windows Forms](../../../../docs/framework/winforms/controls/reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)