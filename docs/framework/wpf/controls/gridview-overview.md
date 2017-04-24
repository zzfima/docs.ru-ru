---
title: "Общие сведения о GridView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "элементы управления, ListView"
  - "GridView - режим представления"
  - "ListView - элементы управления, GridView - режим представления"
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# Общие сведения о GridView
Режим представления <xref:System.Windows.Controls.GridView> является одним из режимов представления для элемента управления <xref:System.Windows.Controls.ListView>.  Класс <xref:System.Windows.Controls.GridView> и его вспомогательные классы используются для просмотра коллекций элементов в таблицах, в которых в качестве интерактивных заголовков столбцов обычно используются кнопки.  В этом разделе описывается класс <xref:System.Windows.Controls.GridView> и возможности его использования.  
  
   
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## Что такое представление GridView?  
 В режиме представления <xref:System.Windows.Controls.GridView> отображается список элементов данных посредством привязки полей данных к столбцам и отображения заголовка столбца для идентификации поля.  В применяемом по умолчанию стиле <xref:System.Windows.Controls.GridView> заголовки столбцов реализуются в виде кнопок.  Используя кнопки в качестве заголовков столбцов, можно реализовать важные возможности взаимодействия с пользователем. Например, пользователь может щелкнуть заголовок столбца для сортировки данных <xref:System.Windows.Controls.GridView> в соответствии с содержимым конкретного столбца.  
  
> [!NOTE]
>  Элементы управления «кнопка», которые используются в качестве заголовков столбцов <xref:System.Windows.Controls.GridView>, являются производными от <xref:System.Windows.Controls.Primitives.ButtonBase>.  
  
 На следующем рисунке показано представление <xref:System.Windows.Controls.GridView> содержимого <xref:System.Windows.Controls.ListView>.  
  
 **Представление GridView содержимого ListView**  
  
 ![Стилизированный ListView](../../../../docs/framework/wpf/controls/media/styledlistview.png "StyledListView")  
  
 Столбцы <xref:System.Windows.Controls.GridView> представлены объектами <xref:System.Windows.Controls.GridViewColumn>, размер которых может автоматически изменяться в соответствии с их содержимым.  При необходимости можно явно задать ширину объекта <xref:System.Windows.Controls.GridViewColumn>.  Можно изменить размеры столбцов, перетащив границу между заголовками столбцов.  Можно также динамически добавить, удалить, заменить и изменить порядок столбцов, так как эта функция встроена в класс <xref:System.Windows.Controls.GridView>.  Однако в классе <xref:System.Windows.Controls.GridView> не поддерживается непосредственное обновление отображаемых данных.  
  
 В следующем примере показано, как определить объект <xref:System.Windows.Controls.GridView>, в котором отображаются данные о сотрудниках.  В этом примере в объекте <xref:System.Windows.Controls.ListView> определяется `EmployeeInfoDataSource` как свойство <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>.  Определения свойств для <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> привязывают содержимое объектов <xref:System.Windows.Controls.GridViewColumn> к категориям данных `EmployeeInfoDataSource`.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показана таблица, которая создается в предыдущем примере.  
  
 **Объект GridView, в котором отображаются данные из ItemsSource**  
  
 ![ListView с выводом GridView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## Макет и стиль GridView  
 Ячейки и заголовок столбца <xref:System.Windows.Controls.GridViewColumn> имеют одинаковую ширину.  По умолчанию ширина каждого столбца изменяется в соответствии с шириной содержимого.  При необходимости можно установить фиксированную ширину столбца.  
  
 Связанные данные отображаются в горизонтальных строках.  Например, в предыдущем примере фамилия, имя и идентификационный номер каждого сотрудника отображаются в виде набора, поскольку они отображаются в горизонтальной строке.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### Определение и применение стилей к столбцам в GridView  
 При определении поля данных, отображаемого в <xref:System.Windows.Controls.GridViewColumn>, используйте свойства <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> или <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A>.  Свойство <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> имеет приоритет над любым из свойств шаблона.  
  
 Чтобы задать выравнивание содержимого в столбце <xref:System.Windows.Controls.GridView>, определите свойство <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>.  Не используйте свойства <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> для содержимого <xref:System.Windows.Controls.ListView>, которое отображается с помощью <xref:System.Windows.Controls.GridView>.  
  
 Чтобы указать свойства шаблонов и стилей для заголовков столбцов, используйте классы <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> и <xref:System.Windows.Controls.GridViewColumnHeader>.  Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### Добавление визуальных элементов в GridView  
 Чтобы добавить визуальные элементы, такие как элементы управления <xref:System.Windows.Controls.CheckBox> и <xref:System.Windows.Controls.Button>, в режиме представления <xref:System.Windows.Controls.GridView>, используйте шаблоны или стили.  
  
 Если явно определить визуальный элемент в качестве элемента данных, он может появляться в <xref:System.Windows.Controls.GridView> только один раз.  Это ограничение существует, так как элемент может иметь только один родительский элемент и, таким образом, может появляться только один раз в [визуальном дереве](GTMT).  
  
<a name="StylingRowsinaGridViewView"></a>   
### Применение стилей к строкам в GridView  
 Используйте классы <xref:System.Windows.Controls.GridViewRowPresenter> и <xref:System.Windows.Controls.GridViewHeaderRowPresenter> для форматирования и отображения строк <xref:System.Windows.Controls.GridView>.  Пример применения стилей к строкам в режиме представления <xref:System.Windows.Controls.GridView> см. в разделе [Задание стиля строки в ListView, который реализует GridView](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### Проблемы выравнивания при использовании ItemContainerStyle  
 Чтобы предотвратить проблемы выравнивания между заголовками столбцов и ячейками, не устанавливайте в свойстве <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> свойство или шаблон, влияющие на ширину элемента.  Например, не устанавливайте свойство <xref:System.Windows.FrameworkElement.Margin%2A> и не указывайте объект <xref:System.Windows.Controls.ControlTemplate>, который добавляет объект <xref:System.Windows.Controls.CheckBox> к свойству <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>, которое определено в элементе управления <xref:System.Windows.Controls.ListView>.  Вместо этого укажите свойства и шаблоны, которые влияют на ширину столбца, непосредственно в классах, определяющих режим представления <xref:System.Windows.Controls.GridView>.  
  
 Например, чтобы добавить объекты <xref:System.Windows.Controls.CheckBox> в строки в режиме представления <xref:System.Windows.Controls.GridView>, добавьте объект <xref:System.Windows.Controls.CheckBox> к объекту <xref:System.Windows.DataTemplate>, а затем задайте свойству <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> значение этого объекта <xref:System.Windows.DataTemplate>.  
  
<a name="InteractingwithaGridViewControl"></a>   
## Взаимодействие с пользователем с помощью GridView  
 При использовании класса <xref:System.Windows.Controls.GridView> в приложении пользователи могут взаимодействовать с объектом <xref:System.Windows.Controls.GridView> и изменять его форматирование.  Например, пользователи могут изменить порядок столбцов, изменить размер столбца, выделить элементы в таблице и прокрутить содержимое.  Можно также определить обработчик событий, реагирующий на нажатие пользователем кнопки заголовка столбца.  Обработчик событий может выполнять такие операции, как сортировка данных, отображающихся в <xref:System.Windows.Controls.GridView>, в соответствии с содержимым столбца.  
  
 В следующем списке более подробно рассматриваются возможности использования <xref:System.Windows.Controls.GridView> для взаимодействия с пользователем:  
  
-   **Изменение порядка столбцов с помощью перетаскивания.**  
  
     Пользователи могут изменить порядок столбцов в <xref:System.Windows.Controls.GridView> путем нажатия левой кнопки мыши на заголовке столбца и перетаскивания этого столбца на новое место.  Пока пользователь перетаскивает заголовок столбца, отображается плавающая версия заголовка, а также жирная черная линия, показывающая место вставки столбца.  
  
     Если требуется изменить стиль по умолчанию для плавающей версии заголовка, укажите объект <xref:System.Windows.Controls.ControlTemplate> для типа <xref:System.Windows.Controls.GridViewColumnHeader>, который инициируется при установке для свойства <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> значения <xref:System.Windows.Controls.GridViewColumnHeaderRole>.  Дополнительные сведения см. в разделе [Создание стиля для перетаскиваемого заголовка столбца GridView](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
-   **Изменение размера столбца по его содержимому.**  
  
     Пользователь может дважды щелкнуть границу справа от заголовка столбца, чтобы изменить размер столбца по размеру его содержимого.  
  
    > [!NOTE]
    >  Чтобы реализовать этот эффект, установите для свойства <xref:System.Windows.Controls.GridViewColumn.Width%2A> значение `Double.NaN`.  
  
-   **Выбор элементов строки.**  
  
     Пользователи могут выбрать один или несколько элементов в <xref:System.Windows.Controls.GridView>.  
  
     Сведения об изменении стиля <xref:System.Windows.Style> для выбранного элемента см. в разделе [Применение триггеров для определения стиля выбранных элементов в ListView](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
-   **Прокрутка для просмотра содержимого, изначально не отображаемого на экране.**  
  
     Если размер объекта <xref:System.Windows.Controls.GridView> недостаточен для отображения всех элементов, пользователь может использовать вертикальную и горизонтальную полосы прокрутки, которые предоставляются элементом управления <xref:System.Windows.Controls.ScrollViewer>.  Объект <xref:System.Windows.Controls.Primitives.ScrollBar> скрывается, если отображается все содержимое в соответствующем направлении.  При использовании полос прокрутки заголовки столбцов не прокручиваются по вертикали, но могут прокручиваться по горизонтали.  
  
-   **Взаимодействие со столбцами путем нажатия на кнопки заголовков столбцов.**  
  
     При нажатии пользователем на кнопку заголовка столбца можно отсортировать данные, которые отображаются в столбце, если указан алгоритм сортировки.  
  
     Можно обработать событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> для кнопок заголовков столбцов, чтобы обеспечить функциональные возможности алгоритма сортировки.  Чтобы обрабатывать событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> для одного заголовка столбца, задайте обработчик событий для <xref:System.Windows.Controls.GridViewColumnHeader>.  Чтобы задать обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> для всех заголовков столбцов задайте обработчик для элемента управления <xref:System.Windows.Controls.ListView>.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## Получение других настраиваемых представлений  
 Класс <xref:System.Windows.Controls.GridView>, производный от абстрактного класса <xref:System.Windows.Controls.ViewBase>, является только одним из возможных режимов представления класса <xref:System.Windows.Controls.ListView>.  Можно создать другие настраиваемые представления для <xref:System.Windows.Controls.ListView> посредством создания классов, производных от класса <xref:System.Windows.Controls.ViewBase>.  Пример настраиваемого режима представления см. в разделе [Создание пользовательского режима представления для ListView](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## Вспомогательные классы GridView  
 Следующие классы поддерживают режим представления <xref:System.Windows.Controls.GridView>.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## См. также  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Controls.GridViewColumn>   
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.ViewBase>   
 [Общие сведения об элементе управления ListView](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [Сортировка столбцов GridView при нажатии на заголовок](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [Практические руководства](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)