---
title: "Как привязать данные с помощью источника данных проекта (службы данных WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "привязка данных, Службы WCF Data Services"
  - "Службы WCF Data Services, привязка данных"
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как привязать данные с помощью источника данных проекта (службы данных WCF Data Services)
Существует возможность создания источников данных на основе объектов данных, формируемых клиентским приложением [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  При добавлении ссылки на службу данных с использованием диалогового окна **Добавить ссылку на службу** наряду с созданными классами данных клиента создается источник данных проекта. Для каждого набора сущностей создается по одному источнику данных, доступ к которому предоставляет служба данных.  Формы для отображения данных службы данных можно создать путем перетаскивания этих элементов источника данных из окна **Источники данных** на окно конструктора.  Эти элементы становятся элементами управления, привязанными к источнику данных.  Во время выполнения источник данных привязывается к экземпляру класса <xref:System.Data.Services.Client.DataServiceCollection%601>, который заполняется объектами, возвращаемыми в ответ на запрос к службе данных.  Для получения дополнительной информации см. [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).  
  
 Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных.  Эта служба и клиентские классы данных создаются после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### Использование источника данных проекта в окне WPF  
  
1.  Добавьте в проект WPF ссылку на службу данных Northwind.  Для получения дополнительной информации см. [Как добавить ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).  
  
2.  Разверните в окне **Источники данных** узел `Customers` в источнике данных проекта **NorthwindEntities**.  
  
3.  Щелкните элемент **CustomerID**, выберите из списка элемент **ComboBox** и перетащите элемент **CustomerID** из узла **Customers** в конструктор.  
  
     При этом в файле XAML для данного окна будут созданы следующие элементы объектов:  
  
    -   Элемент <xref:System.Windows.Data.CollectionViewSource> с именем `customersViewSource`.  Свойству <xref:System.Windows.FrameworkElement.DataContext%2A> элемента объекта верхнего уровня <xref:System.Windows.Controls.Grid> присваивается значение нового объекта <xref:System.Windows.Data.CollectionViewSource>.  
  
    -   Привязанный к данным элемент <xref:System.Windows.Controls.ComboBox> с именем `CustomerID`.  
  
    -   Объект <xref:System.Windows.Controls.Label>.  
  
4.  Перетащите в окно конструктора навигационное свойство **Orders**.  
  
     При этом в файле XAML для данного окна будут созданы следующие дополнительные элементы объектов:  
  
    -   Второй элемент <xref:System.Windows.Data.CollectionViewSource> с именем `customersOrdersViewSource`, источником для которого является объект `customerViewSource`.  
  
    -   Привязанный к данным элемент управления <xref:System.Windows.Controls.DataGrid> с именем `ordersDataGrid`.  
  
5.  Перетащите дополнительные элементы из узла **Customers** в конструктор. \(Необязательно.\)  
  
6.  Откройте кодовую страницу формы и добавьте следующие инструкции `using` \(`Imports` в Visual Basic\):  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]  
  
7.  В разделяемый класс, определяющий форму, добавьте следующий код, который создает экземпляр объекта <xref:System.Data.Objects.ObjectContext> и определяет константу `customerID`.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]  
  
8.  В конструкторе выберите окно.  
  
    > [!NOTE]
    >  Убедитесь, что выбрано само окно, а не содержимое этого окна.  Если окно выбрано, текстовое поле **Имя** в верхней части окна **Свойства** должно содержать имя окна.  
  
9. В окне **Свойства** нажмите кнопку **События**.  
  
10. Найдите событие **Загружено**, затем дважды щелкните раскрывающийся список рядом с этим событием.  
  
     Visual Studio открывает файл с фоновым кодом для окна и формирует обработчик события <xref:System.Windows.FrameworkElement.Loaded>.  
  
11. Скопируйте и вставьте во вновь созданный обработчик события <xref:System.Windows.FrameworkElement.Loaded> следующий код.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]  
  
12. Этот код создает экземпляр <xref:System.Data.Services.Client.DataServiceCollection%601> для типа `Customers` на основе выполнения запроса LINQ, который возвращает интерфейс <xref:System.Collections.Generic.IEnumerable%601> объекта `Customers` вместе со связанными объектами `Orders` из службы данных Northwind и привязывает его к объекту `customersViewSource`.  
  
### Использование источника данных проекта в форме Windows  
  
1.  Разверните в окне **Источники данных** узел **Customers** в источнике данных проекта **NorthwindEntities**.  
  
2.  Щелкните элемент **CustomerID**, выберите из списка элемент **ComboBox** и перетащите элемент **CustomerID** из узла **Customers** в конструктор.  
  
     Это приведет к созданию следующих элементов управления в форме:  
  
    -   Экземпляр <xref:System.Windows.Forms.BindingSource> с именем `customersBindingSource`.  
  
    -   Экземпляр <xref:System.Windows.Forms.BindingNavigator> с именем `customersBindingNavigator`.  Этот элемент управления можно удалить, так как он не понадобится.  
  
    -   Привязанный к данным элемент <xref:System.Windows.Forms.ComboBox> с именем `CustomerID`.  
  
    -   Объект <xref:System.Windows.Forms.Label>.  
  
3.  Перетащите в форму навигационное свойство **Orders**.  
  
4.  Это приведет к созданию элемента управления `ordersBindingSource` и присваиванию свойству <xref:System.Windows.Forms.BindingSource.DataSource%2A> этого элемента управления значения `customersBindingSource`, а свойству <xref:System.Windows.Forms.BindingSource.DataMember%2A> — значения `Customers`.  Кроме того, в форме будет создан привязанный к данным элемент управления `ordersDataGridView` в сочетании с элементом управления меткой, имеющим соответствующий заголовок.  
  
5.  Перетащите дополнительные элементы из узла **Customers** в конструктор. \(Необязательно.\)  
  
6.  Откройте кодовую страницу формы и добавьте следующие инструкции `using` \(`Imports` в Visual Basic\):  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersusing)]  
  
7.  В разделяемый класс, определяющий форму, добавьте следующий код, который создает экземпляр объекта <xref:System.Data.Objects.ObjectContext> и определяет константу `customerID`.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdefinition)]  
  
8.  В конструкторе форм дважды щелкните форму.  
  
     После этого будет открыта страница кода формы и создан метод обработчика события `Load` для этой формы.  
  
9. Скопируйте и вставьте в обработчике события `Load` следующий код.  
  
     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerorders.vb#customersordersdatabinding)]  
  
10. Этот код создает экземпляр <xref:System.Data.Services.Client.DataServiceCollection%601> для типа `Customers` на основе выполнения запроса <xref:System.Data.Services.Client.DataServiceQuery%601>, который возвращает интерфейс <xref:System.Collections.Generic.IEnumerable%601> объекта `Customers` из службы данных Northwind и привязывает его к объекту `customersBindingSource`.  
  
## См. также  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Как привязать данные к элементам Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)