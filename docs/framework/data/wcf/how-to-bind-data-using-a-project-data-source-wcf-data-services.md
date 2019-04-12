---
title: Практическое руководство. Привязать данные с помощью источника данных проекта (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding, WCF Data Services
- WCF Data Services, data binding
ms.assetid: 2477af0a-676f-44f7-b73d-e66208785509
ms.openlocfilehash: e1111077a407dc32475976b15ff71170978e3184
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517074"
---
# <a name="how-to-bind-data-using-a-project-data-source-wcf-data-services"></a>Практическое руководство. Привязать данные с помощью источника данных проекта (службы данных WCF)

Можно создать источники данных, основанные на созданных объектов данных в клиентском приложении службы WCF Data Services. При добавлении ссылки на службу данных с помощью **Add Service Reference** диалоговое окно, источник данных проекта создается вместе с сформированных клиентских классов данных. Для каждого набора сущностей, предоставляемого службой данных, создается один источник данных. Можно создавать формы, отображающие данные из службы путем перетаскивания этих элементов источника данных из **источников данных** на окно конструктора. Эти элементы становятся элементами управления, привязанными к источнику данных. Во время выполнения, этот источник данных привязывается к экземпляру <xref:System.Data.Services.Client.DataServiceCollection%601> класс, который заполняется объектами, которые возвращаются запросом к службе данных. Дополнительные сведения см. в разделе [привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md).

 Примеры в этом разделе используют образец службы данных Northwind и автоматически сформированные клиентские классы службы данных. Эта служба и клиентские классы данных создаются при завершении [краткое руководство по службам данных WCF](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).

## <a name="use-a-project-data-source-in-a-wpf-window"></a>Использование источника данных проекта в окне WPF

1. В Visual Studio в проекте WPF, добавьте ссылку на службу данных Northwind. Дополнительные сведения см. в разделе [Как Добавьте ссылку на службу данных](../../../../docs/framework/data/wcf/how-to-add-a-data-service-reference-wcf-data-services.md).

2. В **источников данных** окне разверните `Customers` узел в **NorthwindEntities** источника данных проекта.

3. Нажмите кнопку **CustomerID** элемента, выберите **ComboBox** в списке и перетащите **CustomerID** элемент из **клиентов** узел конструктор.

     При этом в файле XAML для данного окна будут созданы следующие элементы объектов:

    -   Элемент <xref:System.Windows.Data.CollectionViewSource> с именем `customersViewSource`. Свойству <xref:System.Windows.FrameworkElement.DataContext%2A> элемента объекта верхнего уровня <xref:System.Windows.Controls.Grid> присваивается значение нового объекта <xref:System.Windows.Data.CollectionViewSource>.

    -   Привязанный к данным элемент <xref:System.Windows.Controls.ComboBox> с именем `CustomerID`.

    -   Объект <xref:System.Windows.Controls.Label>.

4. Перетащите **заказы** свойство навигации в конструктор.

     При этом в файле XAML для данного окна будут созданы следующие дополнительные элементы объектов:

    -   Второй элемент <xref:System.Windows.Data.CollectionViewSource> с именем `customersOrdersViewSource`, источником для которого является объект `customerViewSource`.

    -   Привязанный к данным элемент управления <xref:System.Windows.Controls.DataGrid> с именем `ordersDataGrid`.

5. (Необязательно) Перетащите дополнительные элементы из **клиентов** узел в конструктор.

6. Откройте кодовую страницу формы и добавьте следующие инструкции `using` (`Imports` в Visual Basic):

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersusingwpf)]

7. В разделяемый класс, определяющий форму, добавьте следующий код, который создает экземпляр объекта <xref:System.Data.Objects.ObjectContext> и определяет константу `customerID`.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdefinitionwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinitionWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdefinitionwpf)]

8. В конструкторе выберите окно.

    > [!NOTE]
    > Убедитесь, что выбрано само окно, а не содержимое этого окна. Если окно выбрано, **имя** текстовое поле в верхней части **свойства** должно содержать имя окна.

9. В **свойства** выберите **события** кнопки.

10. Найти **Loaded** событий, а затем в раскрывающемся списке рядом с этим событием.

     Visual Studio открывает файл с фоновым кодом для окна и формирует обработчик события <xref:System.Windows.FrameworkElement.Loaded>.

11. Скопируйте и вставьте во вновь созданный обработчик события <xref:System.Windows.FrameworkElement.Loaded> следующий код.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf2.xaml.cs#customersordersdatabindingwpf)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingWpf](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf2.xaml.vb#customersordersdatabindingwpf)]

12. Этот код создает экземпляр <xref:System.Data.Services.Client.DataServiceCollection%601> для типа `Customers` на основе выполнения запроса LINQ, который возвращает интерфейс <xref:System.Collections.Generic.IEnumerable%601> объекта `Customers` вместе со связанными объектами `Orders` из службы данных Northwind и привязывает его к объекту `customersViewSource`.

## <a name="use-a-project-data-source-in-a-windows-form"></a>Использование источника данных проекта в форме Windows

1. В **источников данных** окне разверните **клиентов** узел в **NorthwindEntities** источника данных проекта.

2. Нажмите кнопку **CustomerID** элемента, выберите **ComboBox** в списке и перетащите **CustomerID** элемент из **клиентов** узел конструктор.

     Это приведет к созданию следующих элементов управления в форме:

    -   Экземпляр <xref:System.Windows.Forms.BindingSource> с именем `customersBindingSource`.

    -   Экземпляр <xref:System.Windows.Forms.BindingNavigator> с именем `customersBindingNavigator`. Этот элемент управления можно удалить, так как он не понадобится.

    -   Привязанный к данным элемент <xref:System.Windows.Forms.ComboBox> с именем `CustomerID`.

    -   Объект <xref:System.Windows.Forms.Label>.

3. Перетащите **заказы** в форму свойство навигации.

4. Это приведет к созданию элемента управления `ordersBindingSource` и присваиванию свойству <xref:System.Windows.Forms.BindingSource.DataSource%2A> этого элемента управления значения `customersBindingSource`, а свойству <xref:System.Windows.Forms.BindingSource.DataMember%2A> — значения `Customers`. Кроме того, в форме будет создан привязанный к данным элемент управления `ordersDataGridView` в сочетании с элементом управления меткой, имеющим соответствующий заголовок.

5. (Необязательно) Перетащите дополнительные элементы из **клиентов** узел в конструктор.

6. Откройте кодовую страницу формы и добавьте следующие инструкции `using` (`Imports` в Visual Basic):

     [!code-csharp[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersusing)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersUsing](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersusing)]

7. В разделяемый класс, определяющий форму, добавьте следующий код, который создает экземпляр объекта <xref:System.Data.Objects.ObjectContext> и определяет константу `customerID`.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdefinition)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdefinition)]

8. В конструкторе форм дважды щелкните форму.

     После этого будет открыта страница кода формы и создан метод обработчика события `Load` для этой формы.

9. Скопируйте и вставьте в обработчике события `Load` следующий код.

     [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabinding)]
     [!code-vb[Astoria Northwind Client#CustomersOrdersDataBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabinding)]

10. Этот код создает экземпляр <xref:System.Data.Services.Client.DataServiceCollection%601> для типа `Customers` на основе выполнения запроса <xref:System.Data.Services.Client.DataServiceQuery%601>, который возвращает интерфейс <xref:System.Collections.Generic.IEnumerable%601> объекта `Customers` из службы данных Northwind и привязывает его к объекту `customersBindingSource`.

## <a name="see-also"></a>См. также

- [Библиотека клиентов служб данных WCF](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [Практическое руководство. Привязка данных к элементам Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)
