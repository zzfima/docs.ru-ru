---
title: Привязка данных к элементам управления (службы данных WCF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- client applications, WCF Data Services
- WCF Data Services, client library
- data binding, WCF Data Services
ms.assetid: b32e1d49-c214-4cb1-867e-88fbb3d08c8d
ms.openlocfilehash: ab75380738064a001b12e79d1481d053622077ef
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569320"
---
# <a name="binding-data-to-controls-wcf-data-services"></a>Привязка данных к элементам управления (службы данных WCF)
С помощью WCF Data Services можно привязывать элементы управления, такие как `ComboBox` и `ListView`, к экземпляру класса <xref:System.Data.Services.Client.DataServiceCollection%601>. Эта коллекция, которая наследуется от класса <xref:System.Collections.ObjectModel.ObservableCollection%601>, содержит данные из канала Open Data Protocol (OData). Этот класс представляет коллекцию динамических данных, обеспечивающих выдачу уведомлений при добавлении и удалении элементов. При использовании экземпляра <xref:System.Data.Services.Client.DataServiceCollection%601> для привязки данных, WCF Data Services клиентские библиотеки обрабатывали эти события, чтобы гарантировать, что объекты, которые отписываются <xref:System.Data.Services.Client.DataServiceContext>, будут синхронизированы с данными в связанном элементе пользовательского интерфейса.  
  
 Класс <xref:System.Data.Services.Client.DataServiceCollection%601> реализует интерфейс <xref:System.Collections.Specialized.INotifyCollectionChanged> (не напрямую) для оповещения контекста о добавлении и удалении объектов в коллекции. Объекты типа службы данных, используемые с коллекцией <xref:System.Data.Services.Client.DataServiceCollection%601>, должны также реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged> для оповещения объекта <xref:System.Data.Services.Client.DataServiceCollection%601> об изменении свойств объектов в привязанной коллекции.  
  
> [!NOTE]
> При использовании диалогового окна **Добавление ссылки на службу** или средства [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) с параметром `/dataservicecollection` для создания классов клиентских служб данных созданные классы данных реализуют интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>. Дополнительные сведения см. [в разделе как вручную создавать классы службы данных клиента](how-to-manually-generate-client-data-service-classes-wcf-data-services.md).  
  
## <a name="creating-the-binding-collection"></a>Создание коллекции привязок  
 Создать новый экземпляр класса <xref:System.Data.Services.Client.DataServiceCollection%601> можно путем вызова одного из конструкторов класса, передав ему экземпляр <xref:System.Data.Services.Client.DataServiceContext> и необязательный объект <xref:System.Data.Services.Client.DataServiceQuery%601> или запрос LINQ, при выполнении которого возвращается экземпляр <xref:System.Collections.Generic.IEnumerable%601>. Этот <xref:System.Collections.Generic.IEnumerable%601> предоставляет источник объектов для коллекции привязок, материализованный из веб-канала OData. Дополнительные сведения см. в разделе [материализация объектов](object-materialization-wcf-data-services.md). По умолчанию изменения в привязанных объектах и элементах, вставляемых в коллекцию, автоматически отслеживаются контекстом <xref:System.Data.Services.Client.DataServiceContext>. Если необходимо вручную отвести эти изменения, вызовите один из методов конструктора, который принимает параметр `trackingMode` и укажите значение <xref:System.Data.Services.Client.TrackingMode.None>.  
  
 Следующий пример иллюстрирует создание экземпляра <xref:System.Data.Services.Client.DataServiceCollection%601> на основе переданного контекста <xref:System.Data.Services.Client.DataServiceContext> и объекта <xref:System.Data.Services.Client.DataServiceQuery%601>, который возвращает всех клиентов вместе со связанными с ними заказами.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders2.cs#customersorders2binding)]
 [!code-vb[Astoria Northwind Client#CustomersOrders2Binding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders2.vb#customersorders2binding)]  
  
## <a name="binding-data-to-windows-presentation-foundation-elements"></a>Привязка данных к элементам Windows Presentation Foundation  
 Поскольку класс <xref:System.Data.Services.Client.DataServiceCollection%601> является наследником класса <xref:System.Collections.ObjectModel.ObservableCollection%601>, привязывать объекты к компоненту или элементу управления в приложении Windows Presentation Foundation (WPF) можно так же, как и при использовании для привязки класса <xref:System.Collections.ObjectModel.ObservableCollection%601>. Дополнительные сведения см. в разделе [Привязка данных (Windows Presentation Foundation)](../../../desktop-wpf/data/data-binding-overview.md). Одним из способов привязки данных службы данных к элементам управления WPF является задание значения свойства `DataContext` элемента, равного экземпляру класса <xref:System.Data.Services.Client.DataServiceCollection%601>, который содержит результат выполнения запроса. В этом случае используйте свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> для задания источника объектов для элемента управления. Используйте свойство <xref:System.Windows.Controls.ItemsControl.DisplayMemberPath%2A> для задания отображаемого свойства привязанного объекта. Если элемент привязывается к связанному объекту, возвращаемому свойством навигации, включите путь в привязку, определенную для свойства <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Данный путь задается относительно корневого объекта, заданного свойством <xref:System.Windows.FrameworkElement.DataContext%2A> родительского элемента управления. В следующем примере задается свойство <xref:System.Windows.FrameworkElement.DataContext%2A> элемента <xref:System.Windows.Controls.StackPanel> для привязки родительского элемента управления к коллекции клиентских объектов <xref:System.Data.Services.Client.DataServiceCollection%601>.  
  
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#masterdetailbinding)]
 [!code-csharp[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf.xaml.cs#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml.vb#masterdetailbinding)]
 [!code-vb[Astoria Northwind Client#MasterDetailBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#masterdetailbinding)]  
  
 В следующем примере показано определение привязки XAML для дочерних элементов управления <xref:System.Windows.Controls.DataGrid> и <xref:System.Windows.Controls.ComboBox>:  
  
 [!code-xaml[Astoria Northwind Client#MasterDetailXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf.xaml#masterdetailxaml)]  
  
 Дополнительные сведения см. в разделе [инструкции. Привязка данных к Windows Presentation Foundation элементам](bind-data-to-wpf-elements-wcf-data-services.md).  
  
 Если сущность участвует в отношении «один ко многим» или «многие ко многим», свойство навигации отношения возвращает коллекцию связанных объектов. При использовании диалогового окна **Добавление ссылки на службу** или средства DataSvcUtil. exe для создания классов клиентских служб данных свойство навигации возвращает экземпляр <xref:System.Data.Services.Client.DataServiceCollection%601>. Это позволяет привязывать связанные объекты к элементу управления с поддержкой типовых сценариев привязки WPF, таких как шаблон привязки «основной-подробности» для связанных сущностей. В предыдущем примере XAML код XAML привязывает основную коллекцию <xref:System.Data.Services.Client.DataServiceCollection%601> к корневому элементу данных. Затем заказ <xref:System.Windows.Controls.DataGrid> привязывается к коллекции объектов Orders <xref:System.Data.Services.Client.DataServiceCollection%601>, возвращаемой для выбранного объекта Customers, который в свою очередь привязывается к корневому элементу данных объекта <xref:System.Windows.Window>.  
  
## <a name="binding-data-to-windows-forms-controls"></a>Привязка данных к элементам управления Windows Forms  
 Для привязки объектов к элементу управления Windows Form задайте значение свойства `DataSource` элемента управления, равное экземпляру класса <xref:System.Data.Services.Client.DataServiceCollection%601>, который содержит результат выполнения запроса.  
  
> [!NOTE]
> Привязка данных поддерживается только для элементов управления, прослушивающих события изменений путем реализации интерфейсов <xref:System.Collections.Specialized.INotifyCollectionChanged> и <xref:System.ComponentModel.INotifyPropertyChanged>. Если элемент управления не поддерживает этот тип уведомлений об изменениях, изменения в базовом объекте <xref:System.Data.Services.Client.DataServiceCollection%601> не отражаются в привязанном элементе управления.  
  
 В следующем примере показана привязка коллекции <xref:System.Data.Services.Client.DataServiceCollection%601> к элементу управления <xref:System.Windows.Forms.ComboBox>:  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorders.cs#customersordersdatabindingspecific)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDataBindingSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorders.vb#customersordersdatabindingspecific)]  
  
 При использовании диалогового окна **Добавление ссылки на службу** для создания классов клиентских служб данных также создается источник данных проекта, основанный на созданном <xref:System.Data.Services.Client.DataServiceContext>. С помощью этого источника данных можно создавать элементы пользовательского интерфейса или элементы управления, отображающие данные из службы данных, просто перетаскивая элементы из окна **Источники данных** в конструктор. Добавленные элементы становятся элементами пользовательского интерфейса приложения, привязанными к источнику данных. Дополнительные сведения см. [в разделе инструкции. Привязка данных с помощью источника данных проекта](how-to-bind-data-using-a-project-data-source-wcf-data-services.md).  
  
## <a name="binding-paged-data"></a>Привязка постраничных данных  
 Служба данных может быть настроена для ограничения объема запрашиваемых данных, возвращаемых в отдельном ответном сообщении. Дополнительные сведения см. [в разделе Настройка службы данных](configuring-the-data-service-wcf-data-services.md). Если служба данных использует подкачку страниц для возврата запрашиваемых данных, в каждом ответе содержится ссылка, используемая для возврата следующей страницы результатов. Дополнительные сведения см. в разделе [Загрузка отложенного содержимого](loading-deferred-content-wcf-data-services.md). В этом случае необходимо явно загружать страницы путем вызова метода <xref:System.Data.Services.Client.DataServiceCollection%601.Load%2A> объекта <xref:System.Data.Services.Client.DataServiceCollection%601>, передавая ему URI, полученный из свойства <xref:System.Data.Services.Client.DataServiceQueryContinuation.NextLinkUri%2A>, как показано в следующем примере.  
  
 [!code-csharp[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderswpf3.xaml.cs#bindpageddataspecific)]
 [!code-vb[Astoria Northwind Client#BindPagedDataSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderswpf3.xaml.vb#bindpageddataspecific)]  
  
 Связанные объекты загружаются аналогичным способом. Дополнительные сведения см. в разделе [инструкции. Привязка данных к Windows Presentation Foundation элементам](bind-data-to-wpf-elements-wcf-data-services.md).  
  
## <a name="customizing-data-binding-behaviors"></a>Настройка поведения привязки данных  
 Класс <xref:System.Data.Services.Client.DataServiceCollection%601> позволяет перехватывать события, возникающие при изменении коллекции, например при добавлении или удалении объекта, а также при модификации свойств объекта в коллекции. Имеется возможность модифицировать события привязки для переопределения поведения по умолчанию со следующими ограничениями.  
  
- В делегатах не выполняется никаких проверок.  
  
- При добавлении сущности автоматически добавляются связанные сущности.  
  
- При удалении сущности связанные сущности не удаляются.  
  
 При создании нового экземпляра <xref:System.Data.Services.Client.DataServiceCollection%601> имеется возможность указать следующие параметры, определяющие делегаты методов для обработки событий, возникающих при изменении привязанных объектов.  
  
- `entityChanged` — метод, вызываемый при изменении свойства привязанного объекта. Делегат <xref:System.Func%602> принимает объект <xref:System.Data.Services.Client.EntityChangedParams> и возвращает логическое значение, указывающее, должно ли по-прежнему применяться поведение по умолчанию, то есть вызов метода <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> контекста <xref:System.Data.Services.Client.DataServiceContext>.  
  
- `entityCollectionChanged` — метод, вызываемый при добавлении или удалении объекта из коллекции привязок. Делегат <xref:System.Func%602> принимает объект <xref:System.Data.Services.Client.EntityCollectionChangedParams> и возвращает логическое значение, указывающее, должно ли по-прежнему применяться поведение по умолчанию, то есть вызов метода <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> для действия <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Add> или метода <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> для действия <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove> применительно к контексту <xref:System.Data.Services.Client.DataServiceContext>.  
  
> [!NOTE]
> WCF Data Services не выполняет проверку пользовательских поведений, реализованных в этих делегатах.  
  
 В следующем примере задано специализированное действие <xref:System.Collections.Specialized.NotifyCollectionChangedAction.Remove>, вызывающее метод <xref:System.Data.Services.Client.DataServiceContext.DeleteLink%2A> и <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> для удаления сущностей `Orders_Details`, принадлежащих удаленной сущности `Orders`. Это специализированное действие выполняется, поскольку зависимые сущности не удаляются автоматически при удалении родительской сущности.  
  
 [!code-csharp[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customerorderscustom.xaml.cs#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom.xaml.vb#customersordersdeleterelated)]
 [!code-vb[Astoria Northwind Client#CustomersOrdersDeleteRelated](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customerorderscustom2.xaml.vb#customersordersdeleterelated)]  
  
 Дополнительные сведения см. [в разделе инструкции. Настройка поведения привязки данных](how-to-customize-data-binding-behaviors-wcf-data-services.md).  
  
 Поведение по умолчанию при удалении объекта из коллекции <xref:System.Data.Services.Client.DataServiceCollection%601> с помощью метода <xref:System.Collections.ObjectModel.Collection%601.Remove%2A> состоит в том, что объект также помечается как удаленный в контексте <xref:System.Data.Services.Client.DataServiceContext>. Для изменения этого поведения можно задать в параметре `entityCollectionChanged` делегат метода, который будет вызываться при возникновении события <xref:System.Collections.Specialized.INotifyCollectionChanged.CollectionChanged>.  
  
## <a name="data-binding-with-custom-client-data-classes"></a>Привязка данных с помощью специализированных клиентских классов данных  
 Для загрузки объектов в коллекцию <xref:System.Data.Services.Client.DataServiceCollection%601> эти объекты сами должны реализовывать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>. Клиентские классы службы данных, создаваемые при использовании диалогового окна **Добавление ссылки на службу** или средства [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) , реализуют этот интерфейс. При предоставлении собственных клиентских классов данных необходимо использовать другой тип коллекции для привязки данных. При изменении объектов необходимо обрабатывать события в элементах управления с привязанными данными для вызова следующих методов класса <xref:System.Data.Services.Client.DataServiceContext>.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> — при добавлении в коллекцию нового объекта.  
  
- <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A> — при удалении объекта из коллекции.  
  
- <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A> — при изменении свойства объекта в коллекции.  
  
- <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> — при добавлении объекта в коллекцию связанного объекта.  
  
- <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> — при добавлении объекта в коллекцию связанных объектов.  
  
 Дополнительные сведения см. [в разделе Обновление службы данных](updating-the-data-service-wcf-data-services.md).  
  
## <a name="see-also"></a>См. также:

- [Практическое руководство. Создание клиентских классов служб данных вручную](how-to-manually-generate-client-data-service-classes-wcf-data-services.md)
- [Практическое руководство. Добавление ссылки на службу данных](how-to-add-a-data-service-reference-wcf-data-services.md)
