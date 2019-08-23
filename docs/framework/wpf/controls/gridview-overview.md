---
title: Общие сведения о GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 6da556296679de1161f609a7731c6fbf14e94730
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966472"
---
# <a name="gridview-overview"></a>Общие сведения о GridView
<xref:System.Windows.Controls.GridView>режим просмотра является одним из режимов представления для <xref:System.Windows.Controls.ListView> элемента управления. <xref:System.Windows.Controls.GridView> Класс и его вспомогательные классы позволяют пользователям просматривать коллекции элементов в таблице, которая обычно использует кнопки в качестве интерактивных заголовков столбцов. В <xref:System.Windows.Controls.GridView> этом разделе описывается класс и его использование.  

<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>Что такое представление GridView?  
 В <xref:System.Windows.Controls.GridView> режиме просмотра отображается список элементов данных путем привязки полей данных к столбцам и отображения заголовка столбца для поиска поля. Стиль по <xref:System.Windows.Controls.GridView> умолчанию реализует кнопки в виде заголовков столбцов. С помощью кнопок для заголовков столбцов можно реализовать важные возможности взаимодействия с пользователем. Например, пользователи могут щелкнуть заголовок столбца, чтобы отсортировать <xref:System.Windows.Controls.GridView> данные в соответствии с содержимым определенного столбца.  
  
> [!NOTE]
> Элементы управления "кнопка <xref:System.Windows.Controls.GridView> ", используемые для заголовков <xref:System.Windows.Controls.Primitives.ButtonBase>столбцов, являются производными от.  
  
 На следующем рисунке показано <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView> представление содержимого.  
    
 ![Снимок экрана, на котором показано представление GridView содержимого ListView.](./media/gridview-overview/styled-listview-content.png)  
  
 <xref:System.Windows.Controls.GridView>столбцы представлены <xref:System.Windows.Controls.GridViewColumn> объектами, которые могут автоматически масштабироваться по содержимому. При необходимости можно явно задать <xref:System.Windows.Controls.GridViewColumn> определенную ширину. Можно изменить размеры столбцов, перетащив границу между заголовками столбцов. Также можно динамически добавлять, удалять, заменять и переупорядочивать столбцы, так как эта функция встроена в <xref:System.Windows.Controls.GridView>. <xref:System.Windows.Controls.GridView> Однако не может напрямую обновлять отображаемые данные.  
  
 В следующем примере показано <xref:System.Windows.Controls.GridView> , как определить, отображающий данные о сотрудниках. В этом примере <xref:System.Windows.Controls.ListView> `EmployeeInfoDataSource` определяет как <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>. Определения свойств для <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> привязки <xref:System.Windows.Controls.GridViewColumn> содержимого к `EmployeeInfoDataSource` категориям данных.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 На следующем рисунке показана таблица, которая создается в предыдущем примере. Элемент управления GridView отображает данные из объекта ItemsSource:
    
 ![Снимок экрана, на котором показан ListView с выходными данными GridView.](./media/gridview-overview/listview-gridview-output.jpg)  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>Макет и стиль GridView  
 Ячейки столбцов и заголовок столбца a <xref:System.Windows.Controls.GridViewColumn> имеют одинаковую ширину. По умолчанию ширина каждого столбца изменяется в соответствии с шириной содержимого. При необходимости можно установить фиксированную ширину столбца.  
  
 Связанные данные отображаются в горизонтальных строках. Например, на предыдущем рисунке фамилия, имя и идентификационный номер каждого сотрудника отображаются в виде набора, поскольку они отображаются в горизонтальной строке.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>Определение и применение стилей к столбцам в GridView  
 При определении поля <xref:System.Windows.Controls.GridViewColumn>данных для вывода в <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>используйте свойства, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>или <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> . <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> Свойство имеет приоритет над любым свойством шаблона.  
  
 Чтобы задать выравнивание содержимого в столбце <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>определите. Не используйте <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> свойства и <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> для <xref:System.Windows.Controls.ListView> содержимого, которое отображается с помощью <xref:System.Windows.Controls.GridView>.  
  
 Чтобы задать свойства шаблона и стиля для заголовков столбцов, <xref:System.Windows.Controls.GridView>используйте <xref:System.Windows.Controls.GridViewColumn>классы, <xref:System.Windows.Controls.GridViewColumnHeader> и. Дополнительные сведения см. в разделе [Общие сведения о стилях заголовков столбцов GridView и шаблонах](gridview-column-header-styles-and-templates-overview.md).  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>Добавление визуальных элементов в GridView  
 Чтобы добавить визуальные элементы, такие <xref:System.Windows.Controls.CheckBox> как <xref:System.Windows.Controls.Button> и элементы управления, <xref:System.Windows.Controls.GridView> в режим просмотра, используйте шаблоны или стили.  
  
 Если вы явно определили визуальный элемент как элемент данных, он может появиться только один раз в <xref:System.Windows.Controls.GridView>. Это ограничение существует, так как элемент может иметь только один родительский элемент и, таким образом, может появляться, только один раз в визуальном дереве.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>Применение стилей к строкам в GridView  
 Используйте классы <xref:System.Windows.Controls.GridViewHeaderRowPresenter> <xref:System.Windows.Controls.GridView>и для форматирования и вывода строк. <xref:System.Windows.Controls.GridViewRowPresenter> Пример стиля строк в <xref:System.Windows.Controls.GridView> режиме представления см. в разделе [стиль строки в ListView, который реализует GridView](how-to-style-a-row-in-a-listview-that-implements-a-gridview.md).  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>Проблемы выравнивания при использовании ItemContainerStyle  
 Чтобы предотвратить проблемы выравнивания между заголовками столбцов и ячейками, не задавайте свойство или укажите шаблон, который влияет на ширину элемента в <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>. Например <xref:System.Windows.FrameworkElement.Margin%2A> , не задавайте свойство или <xref:System.Windows.Controls.ControlTemplate> укажите, который добавляет <xref:System.Windows.Controls.CheckBox> в объект <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> , определенный для <xref:System.Windows.Controls.ListView> элемента управления. Вместо этого укажите свойства и шаблоны, влияющие на ширину столбца, непосредственно в классах <xref:System.Windows.Controls.GridView> , определяющих режим представления.  
  
 Например, <xref:System.Windows.Controls.CheckBox> чтобы добавить в строки в <xref:System.Windows.Controls.GridView> режиме <xref:System.Windows.Controls.CheckBox> просмотра <xref:System.Windows.DataTemplate>, добавьте в, а затем задайте <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> для <xref:System.Windows.DataTemplate>свойства значение.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>Взаимодействие пользователя с GridView  
 При использовании <xref:System.Windows.Controls.GridView> в приложении пользователи могут взаимодействовать с и изменять форматирование <xref:System.Windows.Controls.GridView>. Например, пользователи могут изменить порядок столбцов, изменить размер столбца, выделить элементы в таблице и прокрутить содержимое. Можно также определить обработчик событий, реагирующий на нажатие пользователем кнопки заголовка столбца. Обработчик событий может выполнять такие операции, как сортировка данных, отображаемых в, <xref:System.Windows.Controls.GridView> в соответствии с содержимым столбца.  
  
 В следующем списке более подробно рассматриваются возможности использования для взаимодействия с <xref:System.Windows.Controls.GridView> пользователем.  
  
- **Изменение порядка столбцов с помощью перетаскивания**  
  
     Пользователи могут изменять порядок столбцов в <xref:System.Windows.Controls.GridView> , нажимая левую кнопку мыши, находясь над заголовком столбца, а затем перетаскивая этот столбец в новую точку. Пока пользователь перетаскивает заголовок столбца, отображается плавающей версии заголовка, а также сплошная черная линия, показывающая место вставки столбца.  
  
     Если необходимо изменить стиль по умолчанию для плавающей версии заголовка, укажите <xref:System.Windows.Controls.ControlTemplate> <xref:System.Windows.Controls.GridViewColumnHeader> для типа, который активируется, когда <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> свойство имеет значение <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>. Дополнительные сведения см. в разделе [Как создать стиль для перетаскиваемого заголовка столбца GridView](how-to-create-a-style-for-a-dragged-gridview-column-header.md).  
  
- **Изменение размера столбца по его содержимому**  
  
     Пользователям можно дважды щелкнуть границу справа от заголовка столбца, чтобы изменить размер столбца в соответствии с содержимым.  
  
    > [!NOTE]
    > Можно задать <xref:System.Windows.Controls.GridViewColumn.Width%2A> для `Double.NaN` свойства значение, чтобы получить такой же результат.  
  
- **Выбор элементов строк**  
  
     Пользователи могут выбрать один или несколько элементов в <xref:System.Windows.Controls.GridView>.  
  
     Если вы хотите изменить <xref:System.Windows.Style> элемент выбранного элемента, см. раздел [Использование триггеров для стиля выбранных элементов в ListView](how-to-use-triggers-to-style-selected-items-in-a-listview.md).  
  
- **Прокрутка для просмотра содержимого, изначально не отображаемого на экране**  
  
     Если размер <xref:System.Windows.Controls.GridView> объекта не достаточен для отображения всех элементов, пользователи могут прокручивать горизонтально или вертикально с помощью полос прокрутки, предоставляемых <xref:System.Windows.Controls.ScrollViewer> элементом управления. <xref:System.Windows.Controls.Primitives.ScrollBar> Скрывается, если все содержимое отображается в определенном направлении. При использовании полос прокрутки заголовки столбцов не прокручиваются по вертикали, но могут прокручиваться по горизонтали.  
  
- **Взаимодействие со столбцами путем нажатия кнопок заголовков столбцов**  
  
     При нажатии кнопки заголовка столбца можно отсортировать данные, которые отображаются в столбце, если указан алгоритм сортировки.  
  
     Можно выполнить обработку <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события для кнопок заголовков столбцов, чтобы обеспечить такие функциональные возможности, как алгоритм сортировки. Для обработки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> события в заголовке одного столбца установите обработчик <xref:System.Windows.Controls.GridViewColumnHeader>событий для. Чтобы задать обработчик событий, обрабатывающий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> событие для всех заголовков столбцов, установите обработчик <xref:System.Windows.Controls.ListView> для элемента управления.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>Получение других настраиваемых представлений  
 Класс, производный <xref:System.Windows.Controls.ViewBase> от абстрактного класса, является только одним из <xref:System.Windows.Controls.ListView> возможных режимов представления для класса. <xref:System.Windows.Controls.GridView> Можно создать другие пользовательские представления для <xref:System.Windows.Controls.ListView> , производя <xref:System.Windows.Controls.ViewBase> от класса. Пример настраиваемого режима представления см. в разделе [Создание пользовательского режима представления для ListView](how-to-create-a-custom-view-mode-for-a-listview.md).  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>Вспомогательные классы GridView  
 Следующие классы поддерживают <xref:System.Windows.Controls.GridView> режим представления.  
  
- <xref:System.Windows.Controls.GridViewColumn>  
  
- <xref:System.Windows.Controls.GridViewColumnHeader>  
  
- <xref:System.Windows.Controls.GridViewRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
- <xref:System.Windows.Controls.GridViewColumnCollection>  
  
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.ListViewItem>
- <xref:System.Windows.Controls.GridViewColumn>
- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewRowPresenter>
- <xref:System.Windows.Controls.GridViewHeaderRowPresenter>
- <xref:System.Windows.Controls.ViewBase>
- [Общие сведения об элементе управления ListView](listview-overview.md)
- [Сортировка столбцов GridView при нажатии на заголовок](how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Разделы практического руководства](listview-how-to-topics.md)
